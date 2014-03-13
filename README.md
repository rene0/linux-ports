CentOS 6.5 ports for FreeBSD
============================

Description
-----------

This repository contains both uptodate -c6 and the older -f10 ports. It is my
intention to bring the Linux emulation on FreeBSD up to scratch. As this
progresses I will fill this repo with more and more -c6 ports, all while
maintaining compatibility with the Fedora 10 ports we already have inside
of the ports infrastructure.

For further details read the corresponding
_Chapter 11.  Linux Binary Compatibility_
of the FreeBSD Handbook.

Installation
------------
You will need to make sure you have latest ports tree before you attempt to
install the ports listed here. I recommend using `subversion`, as this way you
will be able to easily revert changes that might have gone wrong. The FreeBSD
Handbook, in particular Chapters `5` and `Appendix A.5`, document how to get the
portstree with subversion.

Installing CentOS 6.5 ports
---------------------------
First you should uninstall linux-f10* ports and its dependencies. To make it easier,
you can use pkg(8) for that purpose:
```
    # pkg delete -f linux-f10-\*
    # pkg delete -f linux_base-f10
```

If you have not yet worked with Linux emulation, load the linux kernel module:
```
    # kldload linux
```
To make the change permanent, add the module to your `/etc/rc.conf` kld_list:
```
    # echo 'kld_list="linux" >> /etc/rc.conf
```

Proceed to change the compatibility level of the Linux kernel OS release by running
the following command: asdf
```
    # sysctl compat.linux.osrelease=2.6.18
```
To make the change permanent, add this sysctl(8) variable to /etc/sysctl.conf:
```
    # echo 'compat.linux.osrelease=2.6.18' >> /etc/sysctl.conf
```

Once these preliminaries are done, you will need to merge the linux-ports from
this repo  into your portstree in  `/usr/ports` (without moving the .git
subdirectory)  with the following command:

```
    git clone https://github.com/xmj/linux-ports.git
    rsync -av --exclude=.git/ linux-ports/ /usr/ports/
```


Now, install the actual linux base - `emulators/linux_base-c6`:
```
    # portmaster emulators/linux_base-c6
```

Congratulations, you can now chroot into `/compat/linux` and play around with
it.
```
    # chroot /compat/linux /bin/sh
```

Kernel modules
--------------

Many linux programs depend on linprocfs(5) or linsysfs(5), so it's advised to
load both. Once the modules are loaded, you can mount the respective
filesystems:

```
    # kldload linprocfs
    # mount -t linprocfs linprocfs /compat/linux/proc
    # kldload linsysfs
    # mount -t linsysfs linsysfs /compat/linux/sys
```
To make this change permanent, add these two lines to /etc/fstab:

```
    linprocfs      /compat/linux/proc     linprocfs         rw      0       0
    linsysfs       /compat/linux/sys      linsysfs         rw      0       0
```

and amend your `/etc/rc.conf` to include the modules:

```
    KLD_LIST="linux linsysfs linprocfs"
```

Configuring sound
-----------------

As I've received multiple reports of sound issues, here's how I setup sound with
ALSA (on FreeBSD and Linux):

First, install `audio/linux-c6-alsa-plugins-oss`:
```
    # portmaster audio/linux-c6-alsa-plugins-oss
```

Then, setup `/compat/linux/etc/alsa/pcm/pcm-oss.conf` to match your sound
configuration. The following configuration works for me with `snd_hda`, you may
have to adapt paths to /dev/dsp and /dev/mixer.

```
pcm.oss {
    type oss
    device /dev/dsp
    hint {
        description "Open Sound System"
    }
}

ctl.oss {
    type oss
    device /dev/mixer0
    hint {
        description "Open Sound System"
    }
}
```


Specific Skype requirements
---------------------------

If you've followed this guide from top to bottom, you by now have copied the
required ports into your tree, installed `linux_base-c6`, loaded kernel modules,
and adapted your sound configuration.

To install Skype, run

```
    # portmaster net-im/skype4
```


Specific Flash requirements
---------------------------

As with Skype, if you've followed this guide from top to bottom, you'll be all
set.

To install Flash, run
```
    # portmaster www/linux-c6-flashplugin11 www/nspluginwrapper
```
and follow the instructions displayed after install. You'll have to run this for
each user that is intended to run Flash:

```
    $ nspluginwrapper -v -a -i
```
or, if you are performing an upgrade,
```
    $ nspluginwrapper -v -a -u
```

Google Earth issues
-------------------

FreeBSD's Intel KMS drivers lack the Hardware Context required by `Mesa 9.2`.
This is a work in progress and will be added in due time. Meanwhile, we do lack
the Hardware Acceleration and Google Earth will be _painfully_ slow.

Note: I'm not sure if this applies to NVIDIA or ATI boards as well. I appreciate every
report to the contrary.
