**Init**

Redox has a multi-staged init process, designed to allow for the loading of disk
drivers in a modular and configurable fashion. This is commonly referred to as
an init ramdisk.

**Ramdisk**
The ramdisk init has the job of loading the drivers required to access the root
filesystem and then transfer control to the userspace init. This is a filesystem
that is linked with the kernel and loaded by the bootloader as part of the
kernel image.

**Filesystem**
As seen above, the ramdisk init has the job of loading and starting the
filesystem init. By default, this will mean that a new init process will be
spawned that loads a new configuration file, now in the root filesystem at
`/etc/init.rc`.

Modifying this file allows for booting directly to the GUI. For example, we
could replace `login` with `orbital`.

[Go Back](index.md)
