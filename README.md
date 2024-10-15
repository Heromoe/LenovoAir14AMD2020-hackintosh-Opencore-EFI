# **联想小新Air14 2020锐龙版 黑苹果EFI**

在原项目 https://github.com/dh374374/Air14-2020-hackintosh-Opencore-EFI 的基础上稍微改了改+升级OC和kext，感谢  
### OpenCore版本：1.0.2

## 可用系统

除macOS 15外，近几代应该都可以使用。  
14的高版本可能出现无限重启卡OC的情况，原因不明。14.3正常

### 已经过测试：
### macOS 13 Ventura
### macOS 14 Sonoma

## **我的配件情况**

| 配件 | 型号 |
| --- | --- |
| CPU | AMD Ryzen 5 4600U |
| 内存 | 8G x 2 「板载」 |
| 显卡 | 核显 |
| 硬盘 | 镁光 2300 MTFDHBA512TDV (512GB) 「自己换的」 |
| 网卡 | 英特尔 Intel Wi-Fi 8265NGW 「自己换的」 |

## **安装前准备**

1. 原本搭载的螃蟹网卡无法驱动，必须自行更换网卡。建议更换博通网卡以支持AirDrop等功能，至少也要更换英特尔网卡（[兼容型号列表](https://openintelwireless.github.io/itlwm/Compat)）。
2. 如你用博通网卡，自行禁用EFI\OC文件夹下的配置文件config.plist的“AirportItlwm.kext"，"IntelBluetoothFirmware.kext"，"IntelBTPatcher.kext"。
3. 如你用英特尔网卡，注意本项目默认带的是macOS 14.0~14.3的驱动，想装其他版本系统 必须前往[itlwm驱动](https://github.com/OpenIntelWireless/itlwm)下载对应版本AirportItlwm.kext覆盖。
4. 部分批次的幸运儿（比如我）搭载三星PM981a硬盘会导致内核恐慌，无法使用必须自行更换硬盘。SATA任意品牌及NVME西数和闪迪全系列兼容性最佳，其他看[兼容性参考链接1](https://apple.sqlsec.com/1-%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86/1-2/#_2)，[兼容性参考链接2](https://macoshome.com/hackintosh/hcourse/2476.html)，[兼容性参考链接3](https://heipg.cn/tutorial/diy-hackintosh-2020.html)。如你更换了SATA协议的硬盘，自行禁用EFI\OC文件夹下的配置文件config.plist的“NVMeFix.kext”。
5. bios必须关闭安全启动 disable secure boot。
6. 安装之前把EFI\OC文件夹下的配置文件config.plist的“NootedRed.kext”禁用，安装好进桌面之后再开启。已做了个禁用的配置文件，改个名覆盖就行，但还是建议自己改。
7. 可以使用 [UMAF](https://github.com/DavidS95/Smokeless_UMAF) 增加显存（可选，不加也可用）。

## **存在的问题**

1. 由于AMD核显驱动问题，Chrome浏览器必须进设置→系统关闭图形加速，不然会卡的怀疑人生，Safari正常。需要等[NootedRed](https://github.com/ChefKissInc/NootedRed)解决。其他一些软件也可能出现兼容性问题。
2. VDA解码器不支持。
3. 无法自定义风扇转速。
4. 设置的关于页面，CPU型号可能识别成5500U（第三方工具正常）。

## 截图

原作者截图  
![image](https://raw.githubusercontent.com/dh374374/Air14-2020-hackintosh-Opencore-EFI/main/img/WX20231022-153038.png)
![image](https://raw.githubusercontent.com/dh374374/Air14-2020-hackintosh-Opencore-EFI/main/img/WX20231022-153136.png)

---  
一切正常且好用的话，就点个star吧~
---

## 致谢，参考了

https://github.com/longluuly/Ryzentosh-Acer-aspire-7-A715-42G-R6ZR-Opencore-EFI

https://github.com/PIut02/ROG-Zephyrus-G14-GA401-Hackintosh/blob/main/README_cn.md

---
(我为什么硬盘+网卡换这两个垃圾？日本DIY市场过于费拉不堪，网卡找不到二手博通的，全新SSD卖出天价。WD蓝盘500g人民币400，比这便宜的全是无缓+QLC，只能凑合凑合...)
