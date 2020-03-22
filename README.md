# MPG-Z390-GAMING-EDGE-AC-EFI
A hackintosh EFI for MSI MPG Z390 GAMING EDGE AC (use opencore).

下载/Download见release 
### 请一定要先读完整个readme再下载安装！！

## 测试过的可用系统: MacOS 10.15

# 配置及情况
CPU: Intel core i7 9700k <br>
GPU: Intel UHD630 <br>
睡眠/Sleep: Yes <br>
Intel Ethernet Connection I219-V: Yes <br>
Intel(R) Wireless-AC 9462: 
- WIFI: NO
- Bluetooth: Yes (不用从Windows热启动) <br>

USB: 使用通用驱动，未定制 <br>
节能五项: Yes <br>
原生NVRAM: Yes <br>
Realtek ALC1220: Yes

# BIOS
- CFG Lock -> 禁止/Disable (高级模式 -> OC -> CPU模式: 改为专业模式 -> CPU特征 -> CFG锁定)
- Erp -> 允许/Enable
- CSM -> 禁止/Disabled
- XHCI Hand-off -> 允许/Enabled
- 安全启动/security boot -> 禁止/Disabled

# 注意
- 请将OC文件夹放在EFI分区的EFI文件夹内
- ## 请在使用前自行修改白果4码，建议机型iMac19,1。修改位置为: config.plist内的/PlatformInfo/Generic/ 注意这里所有的空白都需要填写。填写内容可使用clover configurator生成
- windows下添加引导项时请添加OC文件夹下的BOOTx64.efi而非OpenCore.efi

# 特别注意
强烈建议在安装前制作一个peU盘来以防万一，因为我在配置完OC后发现win10的bcd没了。如果使用黑果小兵最新的镜像安装的话，安装u盘自带了一个微pe。总之，不怕一万，就怕万一。<br>

我这个EFI完全是我自己参考xjn大神的博客配置的，并没有考虑其他任何硬件。所以不建议cpu，主板，显卡和我不一样的配置不修改EFI直接使用。<br>
## 并且因为我的电脑上有一块rtx2080，所以我在/NVRAM/Add/7C436110-AB2A-4BBB-A880-FE41995C9F82/boot-args下增加了-wegnoegpu,使用amd免驱卡的用户请删掉上述内容（这个位置就是opencore的开机启动选项设置）

此EFI包含intel无线网卡蓝牙部分的kext驱动。<br>

另: 使用黑果小兵的镜像安装时, 也别忘了将EFI替换成这个哟。

# 参考链接
[使用OpenCore引导黑苹果 -xjn](https://blog.xjn819.com/?p=543) <br>
[精解OpenCore -黑果小兵](https://blog.daliansky.net/OpenCore-BootLoader.html) <br>
[OpenCore 驱动 z390 主板原生 NVRAM -醉渔](https://blog.zuiyu1818.cn/posts/z390_NVRAM.html) <br>
[黑苹果关机不断电怎么解决？--5楼内容](http://bbs.pcbeta.com/viewthread-1793291-1-1.html) <br>
[intel蓝牙 -zxystd](https://github.com/zxystd/IntelBluetoothFirmware)

# 其他
Q: 为啥不配独立显卡? <br>
A: RTX2080无解

Q: 为啥不换网卡? <br>
A: 1.CNVI 2.[期待这个](https://github.com/zxystd/itlwm)
