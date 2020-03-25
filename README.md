# MPG-Z390-GAMING-EDGE-AC-EFI
A hackintosh EFI for MSI MPG Z390 GAMING EDGE AC (use opencore).

下载见release/Download see release

## ___请一定要先读完整个readme再下载安装！！___

### 测试过的可用系统: 
1. MacOS 10.15.3
2. MacOS 10.15.4

# 配置及情况
CPU: Intel core i7 9700k  
GPU: Intel UHD630  
睡眠/Sleep: Yes  
Intel Ethernet Connection I219-V: Yes  
Intel(R) Wireless-AC 9462: 
- WIFI: NO
- Bluetooth: Yes (不需要从windows热启动)  

USB: 使用通用驱动，未定制  
节能五项: Yes  
原生NVRAM: Yes  
Realtek ALC1220: Yes

# BIOS
- CFG Lock -> 禁止/Disable (高级模式 -> OC -> OC操作模式: 改为专业 -> CPU特征 -> CFG锁定)
- ErP Ready -> 允许/Enable
- CSM -> 禁止/Disabled
- XHCI Hand-off -> 允许/Enabled
- 安全启动/security boot -> 禁止/Disabled
- 如果你也和我一样，有一张不能驱动的n卡插在主板上，那么请在切换系统时更改"设置第一显卡"。使用MacOS时用核显，选择IGD;使用win时用独显，选择PEG。如果你有更好的方法，请一定通过Issues告诉我，因为我这个方法挺麻烦的。 /捂脸笑

# 注意
- 请将OC文件夹放在EFI分区的EFI文件夹内
- ## 请在使用前自行修改白果4码，建议机型iMac19,1。修改位置为: config.plist内的/PlatformInfo/Generic/ 注意这里所有的空白都需要填写。填写内容可使用clover configurator生成
- windows下添加引导项时请添加OC文件夹下的BOOTx64.efi而非OpenCore.efi

# 特别注意
强烈建议在安装前制作一个peU盘来以防万一，因为我在配置完OC后发现win10的bcd没了。如果使用黑果小兵最新的镜像安装的话，安装u盘自带了一个微pe。总之，不怕一万，就怕万一。

我这个EFI完全是我自己参考xjn大神的博客配置的，并没有考虑其他任何硬件。所以不建议cpu，主板，显卡和我不一样的配置不修改EFI直接使用。  
## 并且因为我的电脑上有一块rtx2080，所以我在/NVRAM/Add/7C436110-AB2A-4BBB-A880-FE41995C9F82/boot-args下增加了-wegnoegpu,使用amd免驱卡的用户请删掉上述内容（这个位置就是opencore的开机启动选项设置）

### 此EFI默认不检测除MacOS外的任何系统的引导程序，也就是它不能引导windows。我也不建议用opencore引导windows。请使用bios自带的F11或者第三方引导程序rEFInd等切换系统。

此EFI包含intel无线网卡蓝牙部分的kext驱动。

另: 使用黑果小兵的镜像安装时, 也别忘了将EFI替换成这个哟。

# 参考链接
[使用OpenCore引导黑苹果 -xjn](https://blog.xjn819.com/?p=543)  
[精解OpenCore -黑果小兵](https://blog.daliansky.net/OpenCore-BootLoader.html)  
[OpenCore 驱动 z390 主板原生 NVRAM -醉渔](https://blog.zuiyu1818.cn/posts/z390_NVRAM.html)  
[黑苹果关机不断电怎么解决？--5楼内容](http://bbs.pcbeta.com/viewthread-1793291-1-1.html)  
[intel蓝牙 -zxystd](https://github.com/zxystd/IntelBluetoothFirmware)

# 其他
Q: 为啥不配独立显卡?  
A: RTX2080无解

Q: 为啥不换网卡?  
A: 1.CNVI 2.[期待这个](https://github.com/zxystd/itlwm)
