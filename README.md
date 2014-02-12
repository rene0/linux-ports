CentOS 6.5 ports for FreeBSD
============================

Description
-----------

This repository contains both uptodate -c6 and the older -f10 ports. It is my
intention to bring the Linux emulation on FreeBSD up to scratch. As this
progresses I will fill this repo with more and more -c6 ports, all while
maintaining compatibility with the Fedora 10 ports we already have inside
of the ports infrastructure.

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
    # pkg delete -f linux-f10-*
```
Before starting to install, be sure that you add both lines to /etc/make.conf:
```
    OVERRIDE_LINUX_BASE_PORTS=c6
    OVERRIDE_LINUX_NONBASE_PORTS=c6
```

Change the compatibility level of the Linux kernel OS release by running the
following command:
```
    # sysctl compat.linux.osrelease=2.6.18
```

Also add this sysctl(8) variable to /etc/sysctl.conf to make the change permanent:

    # echo 'compat.linux.osrelease=2.6.18' >> /etc/sysctl.conf

Specific Skype requirements
---------------------------

Note that it's necessary to have enabled LBC before you can install
`net-im/skype4` port. Read for further details the corresponding Chapter 11.
Linux Binary Compatibility of the FreeBSD Handbook.

As Skype depends on linprocfs(5), check if it can be loaded and mounted by running:

```
    # kldload linprocfs
    # mount -t linprocfs linproc /compat/linux/proc
```
If the mounting worked, add this line in /etc/fstab
```
    linproc       /compat/linux/proc      linprocfs       rw      0       0
```
You will need to merge the linux-ports into your /usr/ports - for me, something
like `cp -r linux-ports/* /usr/ports` worked.. Now you are ready to install
`net-im/skype4`.
```
    # portmaster net-im/skype4
```

If you want video calls support on a somewhat older FreeBSD system (before
`FreeBSD 10.0`) you should also replace linux_videodev2.h header from
`multimedia/linux_v4l2wrapper-kmod` port:
```
    # cd /usr/ports/multimedia/linux_v4l2wrapper-kmod
    # make patch
    # mv -i /sys/compat/linux/linux_videodev2.h{,.bak}
    # cp -i work/linux_v4l2/linux_videodev2.h /sys/compat/linux
```

Then rebuild/install the kernel. Again, this patch has already been applied for
`FreeBSD 10.0` and `CURRENT`.
