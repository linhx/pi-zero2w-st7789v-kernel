Follow this page to build the kernel https://www.raspberrypi.com/documentation/computers/linux_kernel.html#kernel

--- 

To patch existing OS:

1. Get current .config file inside the PI OS: `cp /boot/config-$(uname -r) .config`. Copy it to the Kernel source directory.
2. At the Step [`Build configuration`](https://www.raspberrypi.com/documentation/computers/linux_kernel.html#cross-compiled-build-configuration) in the guide, instead of running `make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- bcm2711_defconfig`, we run:
   2.1. For 64bit: `make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- olddefconfig`
   2.2. For 32bit: `make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- olddefconfig`
3. Just follow the guide for the next steps.
