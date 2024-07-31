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

介绍Windows To Go技术

Windows  有一项相当吸引人的神奇功能——“Windows To Go”，它可以让你将 Windows 完整安装到U盘、移动硬盘等便携设备上，并且能随处在不同的电脑硬件上直接运行，让系统可以随身携带！简单说来，这功能就是制作“在U盘上运行的 Windows”，让你的Windows带着走！它不是神马精简版，也不是 WinPE，而是货真价实完完整整的 Windows 操作系统，和正常安装的没有任何区别。虽然U盘、移动硬盘的性能比一般的硬盘安装要差点，但它带来了史无前例的便携性。



目前支持从优盘运行的操作系统

Windows7、Windows 8、Windows8.1、Windows 10、Windows Server 2012、Windows Server 2012 R2

推荐使用Windows10 企业版，可以避免很多问题。



支持的优盘

至少16G容量优盘或移动硬盘，这里介绍了哪些优盘适合制作：https://bbs.luobotou.org/thread-10680-1-1.html

------------------------------------------------------------------------------



下面是制作Windows To Go的具体步骤：


一、准备工作


1.系统iso文件，如果之前没下载的话，推荐下载Win10。


2.虚拟光驱或解压软件（本机WIN8及以上系统不需要，WIN7系统推荐：使用魔方虚拟光驱）

3.制作程序WTG辅助工具



注意事项：

1.本程序与电脑管家不兼容，须卸载后再使用。

2.不建议在虚拟机环境下运行。

3.尽量不要将程序放在中文目录下。

4.不推荐安装Windows 7 系统，任何OEM版本和90天试用版都不推荐使用！（如果使用ESD文件，需要提前解密）

------------------------------------------------------------------------------


二、开始制作

1.将Win系统镜像加载至虚拟光驱   



方法一：

    Win8及以上系统，双击打开ISO文件即可加载。


  方法二：魔方虚拟光驱（适用于WIN7 XP系统）

    1)点击加载镜像

    


    2)选择下载的Win镜像文件


    


2.打开WTG辅助工具，单击“点此选择....文件”文字






选择虚拟光驱中sources文件夹中的install.wim





3.选择移动磁盘

如果优盘没有出现在列表中，可在右键菜单中选择手动选择





4.选择模式及高级选项。



一般情况不需要修改，具体作用可点击程序上的问号按钮查看。



注意：

  1)如果您的优盘在计算机中被识别为可移动磁盘，只能使用VHD、VHDX模式。

  2)如果您使用2015年MAC电脑，请勾选UEFI+GPT制作，如果您的优盘不支持此模式，请参照论坛相关教程制作。



5.点击创建按钮开始制作



再次确认所选择的优盘





耐心等待，大约需要几分钟或者几十分钟，与优盘速度有关，如果制作时间超过半小时，您的优盘很可能不适合制作Windows To Go。

等到弹出完成提示框。





完成！！！


------------------------------------------------------------------------------

三、重启电脑进入系统


1.重新启动电脑，设置优盘启动


如果您不知道如何设置优盘启动，请点击查看bios设置教程

（教程 https://bbs.luobotou.org/forum.php?mod=viewthread&tid=804&fromuid=1）




2.个性化设置

优盘启动后的个性化设置，如果您不熟悉，
可以参考：https://bbs.luobotou.org/thread-7670-1-1.html

------------------------------------------------------------------------------



如果您在制作过程中遇到问题，可先看看常见问题列表，如不能解决，可论坛发帖提问。

常见问题：https://bbs.luobotou.org/thread-1625-1-1.html



------------------------------------------------------------------------------


相关技巧教程：

·MAC启动

  1)viploser对于WTG的一些感悟 https://bbs.luobotou.org/thread-10933-1-1.html

  2)我的WTG经历 2015款rMBP在SD卡WTG的思路  https://bbs.luobotou.org/thread-10851-1-1.html

  3)15款MBP在SD卡WTG解决方案  https://bbs.luobotou.org/thread-10858-1-1.html

  4)15款MBP在U盘WTG解决方案  https://bbs.luobotou.org/thread-10901-1-1.html



·性能优化

  1)Windows to GO 系统速度优化

  2)UWF 写入过滤器 支持Win8.1

  3)使用PrimoCache为WTG系统加速




·系统


  1) 在通过Windows To Go安装Windows 8中启用应用商店

  2)激活win8系统

  3)Windows To Go屏蔽本机硬盘教程


·VHD虚拟硬盘相关

  1)更改VHD虚拟磁盘容量（VHD扩容）

  2)WTG VHD模式使用 BITLOCKER加密

  3)WTG VHD模式与WIN8PE 双系统

  4)Windows To Go系统 优盘对拷（VHD）
