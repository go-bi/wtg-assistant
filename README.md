<h1>Windows To Go Assistant</h1>
<h2>Description of Windows To Go(WTG)</h2>

"Windows To Go(WTG)" is a technology originally provided by Microsoft.
It allows you to fully install Windows on portable devices such as USB flash drives, portable hard drives, etc.,
 and can run directly on different computer hardware, so that the system can be carried with you!
It's not a WinPE, nor a simplified version, but a complete Windows operating system, which is almost the same
as a normal installation.

<h2>About Windows To Go Assistant(WTGA)</h2>
The Windows To Go Assistant(WTGA) provides a convenient and quick method to deploy Windows To Go on USB devices. Meanwhile, our community forum 
can provide effective technical support.

<h3>Motivation:  </h3>
Initially, there is no GUI tool to deploy WTG, the only way is to use Command Line until the the official WTG creation tool was built in the Enterprise edition of Windows.
The official tool is simpliy and stable enough, but it lacks some custom settings. Also, there are some portable devices that do not compatible with it.

<h2>Community Forum:</h2>
Luobotou IT Forum(Chinese) : https://bbs.luobotou.org/




一、常用选项卡

传统（推荐）：
传统方式是直接将install.wim中的文件解压到优盘上，与我们平时使用的系统差不多。

虚拟硬盘（仅Win10系统支持）：
VHD写入 是一种新方法，原理是建立一个vhd虚拟盘，将文件解压到vhd虚拟磁盘中。
然后通过引导程序，引导这个虚拟磁盘。此方式启动成功率较低，不推荐。

VHDX：VHDX(虚拟硬盘格式)，由微软推出Windows 8将支持VHDX文件，新的VHDX格式能支持64TB空间，是当前的VHD格式的2TB空间限制的32倍。
注意：vhdx仅限win8及以上系统、vhd写入方式仅限win7 及以上系统、xp系统只能用传统！
关于VHD模式更多信息请看：https://bbs.luobotou.org/thread-5964-1-1.html
关于三种模式性能上的区别，请看评测：传统、VHD、VHDX性能对比测试



不格式化：制作时不格式化磁盘，仅有非UEFI模式可用。

重新分区：
在启动出现问题的时候可以勾选，勾选后写入会删除移动磁盘所有分区！

UEFI+GPT：支持UEFI模式启动，详见https://bbs.luobotou.org/thread-5362-1-1.html

UEFI+MBR：可支持UEFI和传统双启动，详见：https://bbs.luobotou.org/thread-8986-1-1.html

禁用UASP：写入系统后桌面上将会出现DisableUASPHost.exe，运行后重启即可禁用UASP。
详见：WTGA 禁用UASP选项使用说明https://bbs.luobotou.org/forum.php?mod=viewthread&tid=16909&fromuid=1


.NET 3.5：在wtg系统中安装.net framework 3.5 。需要使用到win8系统镜像中的某些文件，如果单独提取install.wim则此功能不可用。

屏蔽本机硬盘：在WINDOWS TO GO系统启动后不加载本机硬盘，避免某些还原软件出错。注意：如果本机系统版本低于优盘系统版本，则不能使用此选项。制作完成后也可改注册表实现：https://bbs.luobotou.org/forum.php?mod=viewthread&tid=6778

Bitlocker：使用Bitlocker加密磁盘。

WIMBOOT（已淘汰）：使用WIMBOOT，使系统直接从WIM文件启动，减少占用空间，详见：https://bbs.luobotou.org/thread-8783-1-1.html。ESD文件需转换为WIM文件才能使用WIMBOOT

CompactOS（已淘汰）：一种压缩技术，可以节约磁盘空间，压缩率与WIMBOOT相当，但没有单独的WIM文件。


禁用WinRE：禁用Windows Recovery Environment.

无默认盘符：每次优盘插入后，不会自动分配盘符。（只对WTG系统所在分区有效）制作完成后也可通过命令行设置：https://bbs.luobotou.org/forum.php?mod=viewthread&tid=45312

NTFS-UEFI：支持从NTFS分区启动UEFI启动项，仅有部分电脑支持此功能。

跳过OOBE：跳过小娜设置界面，以Administrator直接登录，不影响驱动安装，此选项仅简体中文64位系统有效。

二、虚拟硬盘选项卡

虚拟硬盘文件名：vhd或vhdx文件的文件名。
虚拟硬盘磁盘大小：针对VHD(X)模式，创建的VHD磁盘大小。对于扩展式VHD，这是最大大小设定值。设定为0 ，则按照优盘实际容量自动调节。有关VHD模式更多信息，请看：https://bbs.luobotou.org/forum.php?mod=viewthread&tid=5964


虚拟硬盘分区表：虚拟硬盘内的分区表格式。

固定大小：创建的VHD文件 固定文件大小，不会随系统使用变化。不勾选默认为动态大小，会随着系统使用逐渐增大。

三、分区选项卡

可以自定义设置，WTG系统将会安装到第一分区。
