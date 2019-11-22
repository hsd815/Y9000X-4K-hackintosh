# Y9000X-4K-hackintosh
---
---
个人建议OpenCore+10.15或者Clover+10.14系统使用，精力有限希望大家一起完善
# EFI信息
* 配置:4K/ i7 9750H/ 16G/ INTEL760p+PM981/ DW1820A
* Clover + Open Core
* 4k显示补丁，显存2048M，原生HiDPI显示
* 支持10.14/10.15系统
* 加入DW1820a的device property驱动，可以支持apple watch自动解锁 
* 加入屏蔽PM981补丁
# 更新
* 2019.11.21 更新了睡眠补丁，睡眠后键盘关闭，电源键正常闪烁。
* 2019.11.17 更新了第二版OC引导，现在10.14和10.15系统的**触控板都正常工作了**。除了声音和FN热键外其他基本正常。
* 2019.11.16 去除了一些无用驱动，更新了新的USB定制文件 [现在Open Core支持10.14系统了](https://github.com/hsd815/Y9000X-4K-hackintosh/)
* 2019.11.15 open core漏掉了电源管理和airdropbcmfixup两个驱动，已经补上了
* 2019.11.15 更新了open core引导 clover变更了一些驱动 **现在重心转移到opencore了，clover应该不会再更新了**
* 2019.11.14 更新了USB定制aml文件
* 2019.11.13 更新了屏蔽pm981的aml文件
* 2019.11.12 更新了一些图片
# 相关教程
* [OpenCore教程1](https://blog.xjn819.com/?p=543) [OpenCore教程2](https://blog.daliansky.net/OpenCore-BootLoader.html)
* [OpenCore补丁](https://github.com/daliansky/OC-little)
* [AppleALC声卡驱动定制教程](https://blog.daliansky.net/Use-AppleALC-sound-card-to-drive-the-correct-posture-of-AppleHDA.html)和[视频教程](https://www.bilibili.com/video/av49595490?from=search&seid=14028812718245345296)
* [hackintool教程](https://blog.daliansky.net/Intel-FB-Patcher-tutorial-and-insertion-pose.html)
* [USB定制教程](https://blog.daliansky.net/Intel-FB-Patcher-USB-Custom-Video.html)
* [DW1820A教程及驱动](https://blog.daliansky.net/DW1820A_BCM94350ZAE-driver-inserts-the-correct-posture.html)
# 前期准备
* **更换硬盘**：pm981a无法安装黑苹果，我加了一个了intel的760p硬盘。由于有pm981存在，系统非常不稳定随时死机重启。必须拆下三星的这块硬盘或者屏蔽这块硬盘。本efi默认屏蔽这块硬盘且pm981在第一硬盘位，如果你选择直接拆下这块硬盘，请删除efi/clover/acpi/patched/SSDT-DNVMe.aml文件。
* **更换网卡为DW1820a**：我按照[黑果小兵](https://blog.daliansky.net/DW1820A_BCM94350ZAE-driver-inserts-the-correct-posture.html)的教程对这块网卡做了屏蔽。
* 关闭intel VT-d
* 切换硬盘模式为 AHCI
* 关闭secure boot
# 工作
* 显示相关：4k显示 背光 硬件加速 睡眠
* 网络相关：wifi 蓝牙 handoff airdrop imessage(需要自己配置三码)
* 其他硬件：耳机 麦克风 摄像头 触控板全手势 电源管理 雷电接口转接U盘
# 不工作
* 网友报告CLover下10.15下触控板可能不驱动
* 扬声器
* 雷电接口转接HDMI
* FN热键
# 其他问题
* opencore如果使用启动磁盘功能选择默认启动磁盘进入系统有可能会丢失声音驱动和触控板驱动
* 如果加了驱动却不生效：终端输入`kextstat | grep -v com.apple`查看已加载驱动
* opencore设置了timeout时间为1秒，初次切换opencore时按`ESC`进入系统选择菜单，进入系统后再通过系统的`启动磁盘`功能选择默认启动磁盘
* 如果不是使用DW1820A这块网卡的话，先进BIOS关闭无线网卡，进入系统了再更换驱动

