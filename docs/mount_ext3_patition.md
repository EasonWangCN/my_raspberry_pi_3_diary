# Mount ext3 Patition to Windows or OSX

There are 2 patitions in the SD card: 

* a `boot` patition in FAT format, contain the kernal and some intial settings
* another ext3 patition carries the Linux file system

Sometimes we need to access the files in that ext3 patitions such as config network settings before SSH accessable. Windows and OSX have no built in ext3 support. We have to use some tools.

## Linux in VM

If you have Linux system installed in VM (Virtual Box or VMWare) it is easiler to mount external SD card into that virtual system. Check follow URL for steps:

http://superuser.com/questions/373463/how-to-access-an-sd-card-from-a-virtual-machine

## Windows

t.b.d.

## OSX

There are some Apps to help access ext patition in OSX, such as Paragon ExtFS for Mac. But it is not free.

I recomend to use the free usermode file system plug-in for OSX named "FUSE". MacFUSE、Fuse4X and OSXFuse is the 3 different implementations, but MacFUSE is already stop updating.

* Fuse4X: http://fuse4x.github.io/
* OSXFuse: https://osxfuse.github.io/

Both are OK. Download and install it. Becareful to mark `MacFUSE Compatibility Layer` option when installing.

fuse-ext2 is an ext family format implementation on FUSE. it is avilable in: https://sourceforge.net/projects/fuse-ext2/files/. Download and install it, then you can get ext3 patition auto-mounted after insert SD card.

The problems here is the auto-mount patition is readonly. There are some instructions to mount it as writeable: https://thewireframecommunity.com/node/174. But I have issues. After add the `rw+` options, the SD card cannot be mount successfully. But I found a strange steps to make it work:

1. Insert SD card with defualt options. both `boot` and another `Untitled` patition is available in the Finder, but `Untitled` is read-only.
2. Unplug the SD card.
3. Modify the `fuse-ext2.util` file to add `rw+` options.
4. Re-insert the SD card.
5. now only `boot` patition is available in the Finder, but don't worry, you can access another patition via terminal in `/Volumes/Untitled`

Will keep on further study.



