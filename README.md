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

## Building linux 2.2 and 2.4 kernel bzImage with Debian 3 
* Used Debian 3 is wihout X11, because X11 start failed; Debian 3 uses gcc 2.95.4 and linux 2.2.20       
* Building Linux 2.2 and 2.4 need Debian 3, Debian 5 couldn't build Linux 2.2 and 2.4  
* Linux 2.6 can be built under Debian 5 and above
* Linux 2.2.13 kernel bzImage can be started successfully by doxbox-x + loadlin (not need dd, need set cpu type Pentium Pro or above)   
* (Linux 2.2.13 kernel bzImage can be started) also by bochs (not need dd) and old version qemu 0.12.5 (need dd)    
busybox dd if=bzImage-2.2.13.img of=a.img bs=1K count=1440 conv=notrunc  
* Linux 2.4.17 kernel bzImage couldn't be started with any emulators
* Linux 2.4.37 kernel bzImage can be started successfully by ubuntu qemu-system-i386  
```
如果说用redhat 9编译linux内核，用xubuntu 20的qemu-system-i386运行（apt install qemu-system-x86），
我目前试过只有linux-2.4.37可以成功启动（使用arch/i386/defconfig默认配置），
而其他诸如2.2.13和2.4.17都不成功，真撞大运，主要跑不起来也很难调试。
运行是-kernel bzImage，编译是make dep; make bzImage。似乎不能用vmlinux文件直接运行。
如果是MIPS的话我本人好像目前最旧能运行的版本是2.6.35

图形界面安装debian会提示是否安装图形环境和一些server组件，此外就不会提示了，所以debian装完后是没有gcc的，
那它是怎么光盘装gcc的呢？答案是直接用超管的终端（早期版本的debian是分开不一样的终端），
然后sudo apt-get install，然后它会提示你放入哪个序号的binary光盘，然后就可以装上去了

我发现安装debian可能不需要下载全部dvd镜像，可能只需要第一个就够了——它是每个镜像iso都会有所有字符开头的软件包，
我估计它是把常用的都塞到第一张iso中。例如debian 5需要5张dvdiso二进制，而源码的话是要另外的5张iso

我实际测试过，用debian 5.0.10（早期版本）应该是编译不了旧版Linux内核如linux-2.4和之前的版本，
它用的是gcc 4.3.2，linux 2.6.26。令我惊讶的是这debian从早期到现在的安装界面风格都非常相似。
所以可能需要用debian 3和debian 2.2试试，问题是这俩我都没办法安装X11（启动失败可能和显示驱动不对有关），
看来只能用字符界面试验了

我测试过可以，用vmware 15和debian 3（一张dvd光盘，必须指定硬盘为IDE接口，但装X11会运行失败）
可以编译linux-2.4.37的内核bzImage（未知能否用qemu运行），
环境是gcc 2.95.4，linux 2.2.20，只需要在装系统时安装C/C++套装，
以及光盘安装libncurses5-dev软件包（apt-get install会提示放光盘）即可编译成功

我测试过用db-x和loadlin也可以运行部分旧版本linux内核(2.2.13)，
前提是需要把db-x的cpu type设置为奔腾3或者奔腾Pro，
而且只能跑linux-2.2，其他linux-2.4的会解压失败或者卡住

我测试过我用debian 3编译的3个内核（没做任何配置修改的defconfig），
其中2.2.13的bzImage可以用bochs或者用db-x+loadlin运行，
而2.4.37的bzImage可以用qemu运行，
而2.4.17的bzImage则什么模拟器都运行不了它。
bochs的效果如下，
至于db-x loadlin和qemu-system-i386的效果我之前已经给了

我试过用linux 0.11的qemu（旧版0.12.5）也可以运行linux-2.2.13内核bzImage。
不过需要自己用dd命令（我是用busybox-w32）把bzImage刻录到1.44M a盘img文件
并且指定为-fda设备：qemu-img.exe create -f raw a.img 1.44M；
busybox dd if=bzImage-2.2.13.img of=a.img bs=1K count=1440 conv=notrunc；
qemu -L pc-bios -boot a -fda a.img -no-reboot -m 32 -k en-us 。
可能效果和bochs有稍微的区别，但也可以跑起来。
至于其他版本2.4.17和2.4.37的话，
都跑飞了，和bochs一样
目前来说qemu跑bzImage比较玄乎，例如较新的qemu可以-kernel运行2.4版部分较新的bzImage，
但2.2的bzImage跑不起来；但同时，那些跑不起来的bzImage，
有时候可以通过-fda参数（软盘A）来启动运行，但需要qemu比较旧，所以就很别扭
Linux 0.11 on qemu-12.5.i386_only_dd_2.2.13_good.7z

所以我怀疑（不确定）Linux 2.2和2.6是bochs和qemu的分水岭，
而2.4和2.6的区别则被很多人认为是Linux进入稳定版的分水岭（因为所谓Linux 3其实和Linux 2.6差别不大）。
不过我觉得linux 2.4版内核是最不能理解，仅有一些版本（如2.4.17）用bochs和qemu和各种手段都跑不起来，
也许我的做法有问题

我觉得Linux和GCC都有一个很显著的稳定版分水岭，
Linux的发行版通常只会是2.6和以后，ubuntu的gcc通常只会是4和以后。
只有很少情况会碰到旧版本，例如Debian 3可以编译2.2、2.4和以前的内核，
但Debian 5以后就不行，qemu也可能不支持2.2和以前的内核，只能用bochs或旧版的qemu
```
