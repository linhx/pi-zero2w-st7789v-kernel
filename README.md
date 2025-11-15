Follow this page to build the kernel https://www.raspberrypi.com/documentation/computers/linux_kernel.html#kernel

--- 

To patch existing OS:

1. Get current .config file inside the PI OS: `cp /boot/config-$(uname -r) .config`. Copy it to the Kernel source directory.
2. At the Step [`Build configuration`](https://www.raspberrypi.com/documentation/computers/linux_kernel.html#cross-compiled-build-configuration) in the guide, instead of running `make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- bcm2711_defconfig`, we run:

    1. For 64bit: `make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- olddefconfig`
    2. For 32bit: `make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- olddefconfig`

3. Just follow the guide for the next steps.

---

Worked in Ubuntu 24.04
```
bc/noble,now 1.07.1-3ubuntu4 amd64 [installed]
crossbuild-essential-arm64/noble,noble,now 12.10ubuntu1 all [installed]
crossbuild-essential-armhf/noble,noble,now 12.10ubuntu1 all [installed]
bison/noble,now 2:3.8.2+dfsg-1build2 amd64 [installed]
flex/noble,now 2.6.4-8.2build1 amd64 [installed]
libssl-dev/noble-updates,noble-security,now 3.0.13-0ubuntu3.6 amd64 [installed]
linux-headers-6.14.0-33-generic/noble-updates,noble-security,now 6.14.0-33.33~24.04.1 amd64 [installed,automatic]
linux-headers-6.14.0-35-generic/noble-updates,noble-security,now 6.14.0-35.35~24.04.1 amd64 [installed,automatic]
linux-headers-generic-hwe-24.04/noble-updates,noble-security,now 6.14.0-35.35~24.04.1 amd64 [installed,automatic]
```
