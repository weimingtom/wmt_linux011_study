# wmt_linux011_study
My linux-0.11 study, for 16bit 8086 machine.

# ref  

## Linux内核完全注释  
* search baidupan, Linux内核完全注释    
* https://github.com/yuan-xy/Linux-0.11  
* http://www.oldlinux.org  
* search baidupan, linux-0.11-devel-040809.zip
* 另一本类似的书叫：Linux 0.01内核分析与操作系统设计    

## Linux 0.01内核分析与操作系统设计  

## linux-0.11-lab  
* (dead) https://gitee.com/tinylab/linux-0.11-lab    
* https://github.com/zirandu/linux-0.11-lab  
* search baidupan, linux-0.11-lab-master.zip  
ubuntu1404 success  
rpd2017 compile failed  
* http://showdesk.io/2017-03-18-17-54-23-linux-0.11-lab-usage-00-06-42/
```
sudo apt install qemu-system-x86  
sudo apt install bochs bochs-sdl  
sudo apt install bochs-x   
make switch #switch to bochs  
make start #only for bochs  
make start-fd #not work  
make start-hd #with gcc and mkfs command  
```
* qemu monitor:
```
-monitor stdio  
Ctrl+Alt+2:  
(qemu) info block  
(qemu) change floppy0 rootfs/rootimage-0.11  
Ctrl+Alt+1  
```
* 我的研究
```
我研究一下，如果不考虑代码可能的差异，比较容易编译和运行linux 0.11的方法通过这个项目：
zirandu/linux-0.11-lab（出自tinylab），不过缺点是里面有些情况无法运行OS（可能是我没理解）。
运行方法是：
（1）apt install qemu-system-x86 bochs bochs-sdl（注意bochs需要sdl插件）
（2）make switch （切换到bochs）; make start（文件系统是第二个软驱，只支持bochs，不支持qemu）；
make start-hd（bochs和qemu都支持，文件系统是第一个硬盘）。
顺带一提，linux-0.11-lab可能有编译器问题，我用ubuntu14是正常的，
但用较新的rpd 2017会编译失败
```
* 文件系统  
```
总体来说linux 0.11的软盘根文件系统最好使用bochs（虽然后来有人搞出了支持qemu的根文件系统），
那么xv6呢？xv6的qemu是双IDE硬盘，第一个硬盘是OS镜像，第二个硬盘是根文件系统，
而且根文件系统是通过c程序生成的，比较容易修改。
linux 0.11把整个gcc（古老版本）打进去硬盘版的根文件系统中，
所以只能在qemu里头自己打代码然后编译了，不够方便
```

## K210-Linux0.11  
* https://github.com/lizhirui/K210-Linux0.11  
lizhirui_K210-Linux0.11-master.zip  
Linux0.11 with MMU for K210(RISC-V) Version  
* (todo) k210 version  

## 真正能在windows下编译的linux 0.11  
* search baidupan, linux-0.11.rar  
* mingw build     
* 能在windows环境下编译的Linux 0.11了,不是在Cygwin,也不是在虚拟机里,而是使用MinGW  
* oldlinux吧  
* VC6版见下，https://github.com/beride/linux0.11-1    

## linux0.11-1, 中文注释, VC  
* https://github.com/beride/linux0.11-1  

## 品读 Linux 0.11 核心代码  
* https://github.com/dibingfa/flash-linux0.11-talk  
* 你管这破玩意叫操作系统源码 — 像小说一样品读 Linux 0.11 核心代码  
* (old name) https://github.com/sunym1993/flash-linux0.11-talk  

## linux-0.11-quickstart-debug-bochs2.7  
* https://gitee.com/Camio1945/linux-0.11-quickstart-debug-bochs2.7  
```
转：
原仓库 flash-linux0.11-talk 中使用的是 Bochs-2.3.6，
这个版本的 Bochs 不支持 GUI 调试，所以我把它改成了 Bochs-2.7 ，
以方便使用 GUI 调试，其他代码一概未做改动。
```

## (TODO) linux 0.01, DrAcOnUx's web page  
* https://lwn.net/Articles/263562/  
* http://draconux.free.fr/os_dev/linux0.01_news.html  
* search work_linux_0.01  

## MinixFsImg  
* https://tieba.baidu.com/p/4371332592
* https://github.com/mumu3w/MinixFsImg

## OldLinuxSrc, 0.11 and 0.12    
* https://github.com/SFecho/OldLinuxSrc  
* https://github.com/yuan-xy/Linux-0.11  

## qemu.7z  

## redhat9 build linux-2.4.37, xubuntu 20 qemu run bzImage    
* search linux-2.4.37_redhat9_build_qemu_good.tar.gz  
* xubuntu 20.04 64bit qemu  
* sudo apt install qemu-system-x86  
* qemu-system-i368 -kernel bzImage  
```
如果说用redhat 9编译linux内核，用xubuntu 20的qemu-system-i386运行（apt install qemu-system-x86），
我目前试过只有linux-2.4.37可以成功启动（使用arch/i386/defconfig默认配置），而其他诸如2.2.13和2.4.17都不成功，
真撞大运，主要跑不起来也很难调试。运行是-kernel bzImage，编译是make dep; make bzImage。
似乎不能用vmlinux文件直接运行。如果是MIPS的话我本人好像目前最旧能运行的版本是2.6.35
linux-2.4.37_redhat9_build_qemu_good.tar.gz
```

## linux 2.2 ps2  
* https://github.com/jur/linux-2.2.1-ps2  

## 【硬核】自己开发操作系统的书籍和资料推荐，想开发操作系统？不知道从何入手？来看看我的书单吧！  
* https://www.bilibili.com/video/BV1wz4y1R7Sa  
