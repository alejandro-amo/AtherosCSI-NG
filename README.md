# AtherosCSI-NG

The Atheros CSI tool, pusblished by @xieyaxiongfly, is composed by: 
- [a modified kernel driver fot atheros card](https://github.com/xieyaxiongfly/Atheros-CSI-Tool) 
- [userspace tools](https://github.com/xieyaxiongfly/Atheros-CSI-Tool-UserSpace-APP)  

The modified kernel is distributed in the form of a complete set of kernel sources, more specifically 4.1.10 kernel sources, but this format poses several problems:

- you have to change a whole kernel only for the sake of a single driver
- your system gets stuck in a specific kernel version
- this breaks compatibility with newer versions of gnu/linux distros and the hardware support to newer computers
- this renders your system extremely vulnerable to several bugs that have been patched in the kernel since then 

So, we extracted and adapted the code that was truly added/modified from the kernel sources. This way we obtained a valid, compatible, flexible patch file that you can successfully apply on newer kernels so you don't have to sacrifice {bluetooth,wifi,ethernet,security,newer software} in order to be able to perform research with this intesting tool.  
And more important, you'll get rid of old, incompatible, unsecure kernels.
## Compatibility
Tested on ubuntu 16.04 original kernel sources
## Use
drop this file anywhere in your system, then, from the directory of your kernel sources:  
`cat path/to/this/patch/ath_csi.patch | patch -p1 --dry-run`  
if you get no rejects, you can patch:  
`cat path/to/this/patch/ath_csi.patch | patch -p1`  
and then you can configure, make and install or build kernel-package as usual.  
  
## Contact Info
alister.amo@eurecat.org
  
I hope this patch could serve more people. Enjoy!  
AA
