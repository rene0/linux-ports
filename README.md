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
    # pkg delete -f linux_base-f10
```
There will be some preparation needed before the actual install can start.
Be sure that you add both lines to /etc/make.conf:
```
    OVERRIDE_LINUX_BASE_PORTS=c6
    OVERRIDE_LINUX_NONBASE_PORTS=c6
```

Change the compatibility level of the Linux kernel OS release by running the
following command:
```
    # sysctl compat.linux.osrelease=2.6.18
```
To make the change permanent, add this sysctl(8) variable to /etc/sysctl.conf:
```
    # echo 'compat.linux.osrelease=2.6.18' >> /etc/sysctl.conf
```

Specific Skype requirements
---------------------------

Note that it's necessary to have enabled LBC before you can install
`net-im/skype4` port. Read for further details the corresponding Chapter 11.
Linux Binary Compatibility of the FreeBSD Handbook.

As Skype depends on linprocfs(5) and linsysfs(5), check if they can
be loaded and mounted by running:

```
    # kldload linprocfs
    # mount -t linprocfs linprocfs /compat/linux/proc
    # kldload linsysfs
    # mount -t linsysfs linsysfs /compat/linux/sys
```
To make this change permanent, add these two lines to /etc/fstab:
```
    linprocfs      /compat/linux/proc     linprocfs         rw      0       0
    linsysfs       /compat/linux/sys      linprocfs         rw      0       0
```
Once these preliminaries are done, You will need to merge the linux-ports into
your portstree in  `/usr/ports` - like so: `cp -r linux-ports/* /usr/ports`

Now you are ready to install `net-im/skype4`.
```
    # portmaster net-im/skype4
```
