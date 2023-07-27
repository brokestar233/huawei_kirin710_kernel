# What's this?
Custom Kernel for kirin710

# how to use it?
You need an arm64 device running debian sid (raspberry is nice) also,you can chooice an android phone which rooted and that it have a chroot debian (sid)
in debian shell:
```shell
apt install device-tree-compiler build-essential clang bc git -y
git clone https://github.com/dirt2022/huawei_kirin710_kernel
cd huawei_kirin710_kernel
make merge_kirin710_defconfig
make -j$(nproc)
```

you will get an Image.gz <and some "ko" files (won't use these)>
use AIK-Linux : unpack KERNEL.IMG in your device's OTA package (update.app)
 run this:
 ```shell
 cp Image.gz ./split-img/KERNEL.img-kernel
 ./repackimg.sh
```

# attention
the kernel version is 4.9.148
Selinux for Permissive,(if you need an secure device,run : make menuconfig , and disable selinux_develop)
(if the option enabled,default for permissive and can't use enforcing mode)
without KernelSU (you need to flash magisk patched recovery_ramdisk to get root)

# how to flash it?
you need an firmware lower than 9.1.0.126
if you can find it but dc-phoneix says the file is not suitable for flash : please see this : http://wuyou.net/forum.php?mod=viewthread&tid=436686&extra= (simple chinese)
fastboot flash kernel image-new.img
