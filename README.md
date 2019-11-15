# Y9000X-4K-hackintosh
# Clover + Open Core

*Clover* 支持10.14/10.15系统

*Open Core* 目前只有10.15系统能进去，而且声音没有正确驱动还需要完善

* *个人建议Clover+10.14系统使用，精力有限希望大家一起完善*

**配置** 4K/ i7 9750H/ 16G/ INTEL760p+PM981/ DW1820A

# 基于[programbw](https://github.com/programbw/y9000x)的EFI修改
# 按照[黑果小兵](https://blog.daliansky.net/DW1820A_BCM94350ZAE-driver-inserts-the-correct-posture.html)的DW1820A蓝牙教程添加驱动

在[programbw](https://github.com/programbw/y9000x)的EFI基础上

* 添加了**4k显示补丁，显存2048M，原生HiDPI显示**
* 去除了多余的驱动和patch
* 加入了DW1820a的device property驱动，可以支持apple watch自动解锁 
* 添加了屏蔽PM981的patch
* 添加了**Open Core引导**

# 更新
* 2019.11.16 去除了一些无用驱动，更新了新的USB定制文件
* 2019.11.15 open core漏掉了电源管理和airdropbcmfixup两个驱动，已经补上了
* 2019.11.15 更新了open core引导 clover变更了一些驱动
* 2019.11.14 更新了USB定制aml文件
* 2019.11.13 更新了屏蔽pm981的aml文件
* 2019.11.12 更新了一些图片




前期准备
---

**更换硬盘**

* pm981a无法安装黑苹果，我加了一个了intel的760p硬盘。由于有pm981存在，系统非常不稳定随时死机重启。必须拆下三星的这块硬盘或者屏蔽这块硬盘。本efi默认屏蔽这块硬盘且pm981在第一硬盘位，如果你选择直接拆下这块硬盘，请删除efi/clover/acpi/patched/SSDT-DNVMe.aml文件。

**更换网卡为dw1820a**

* 我按照[黑果小兵](https://blog.daliansky.net/DW1820A_BCM94350ZAE-driver-inserts-the-correct-posture.html)的教程对这块网卡做了屏蔽。

关闭intel VT

关闭secure boot

切换硬盘模式为 AHCI


工作
---

4k显示 背光 耳机 麦克风 摄像头

wifi 蓝牙 handoff airdrop

触控板全手势支持（Mojave系统下测试正常）

电源管理 USB接口正常

雷电接口可以正常接U盘

不工作
---

**Catalina下触控板可能会无法驱动**

**指纹**

**fn热键**

**扬声器**

* 音频尝试了自制Applealc驱动，扬声器节点为0x17，路径为0x02>0x17，均确认无误，编译的applealc正常驱动但是就是无声音。。

待测试
---

雷电转接hdmi，dp 和 VGA

