# Y9000X-4K-hackintosh
**Y9000X 4K hackintosh 黑苹果 efi**

**配置** 4K/ i7 9750H/ 16G/ INTEL760p+PM981/ DW1820A

支持10.14/10.15系统

# 基于[programbw](https://github.com/programbw/y9000x)的EFI修改

在[programbw](https://github.com/programbw/y9000x)的EFI基础上

* 添加了4k显示补丁，显存2048M，原生HiDPI显示
* 去除了多余的驱动和patch
* 加入了DW1820a的device property驱动，可以支持apple watch自动解锁



前期准备
---

**更换硬盘**

* pm981a无法安装黑苹果，我加了一个了intel的760p硬盘。由于有pm981存在，系统非常不稳定随时死机重启。必须拆下三星的这块硬盘或者开机不挂载这块硬盘。若选择不挂载该硬盘可以参考[该文章](https://www.jianshu.com/p/38bc919f9138)，volume UUID可以从clover configurator获得。

**更换网卡为dw1820a**

关闭intel VT

关闭secure boot

切换硬盘模式为 AHCI


工作
---

4k显示 背光 耳机 麦克风 摄像头

wifi 蓝牙 handoff airdrop

触控板全手势支持 电源管理 USB接口正常

雷电接口可以正常接U盘

不工作
---

**指纹**

**fn热键**

**扬声器**

* 音频尝试了自制Applealc驱动，扬声器节点为0x17，路径为0x02>0x17，均确认无误，编译的applealc正常驱动但是就是无声音。。

待测试
---

雷电转接hdmi，dp 和 VGA

