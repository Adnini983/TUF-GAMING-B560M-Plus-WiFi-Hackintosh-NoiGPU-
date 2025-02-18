# TUF-GAMING-B560M-Plus-WiFi-Hackintosh-NoiGPU-
应用于华硕 TUF GAMING B560M Plus WiFi的OpenCore 1.0.3的黑苹果引导 支持macOS Sequoia 

注意：
- 此EFI不含三码 实际使用时请自行使用[OCAT](https://github.com/ic005k/OCAuxiliaryTools)生成
- 此EFI屏蔽了核显且未定制核显补丁，如果你要使用Intel核显，请自行解决。
- 从macOS Sonoma开始，博通Wi-Fi网卡需要使用[OCLP-Mod](https://github.com/laobamac/OCLP-Mod/releases)打补丁才可使用。
- 从macOS Sequoia开始，Intel Wi-Fi网卡需要使用[OCLP-Mod](https://github.com/laobamac/OCLP-Mod/releases)打补丁才可使用。

![](Image.png)
### 配置清单
|类型|型号|规格|
|---|---|---|
|CPU|Intel Core i5-10400F|2.90 GHz|
|内存|金士顿 Fury KF432C16BB/8×2|3200 MHz(XMP)|
|SSD1|金士顿 NV2 NVMe|500 GB|
|SSD2|三星 860 EVO SATA|250 GB|
|显卡|AMD Radeon RX 580(2304SP)|4 GB|
|网卡|RealTek RTL8125|2.5 Gbps|
|Wi-Fi|Intel Wi-Fi 6 AX201|m.2|
|声卡|RealTek ALC897|立体声|
|操作系统|macOS Sequoia|15.1|
|BIOS|AMI UEFI(2023)|2001 x64|

#### 无法工作的部分
- 核显：测试的CPU没有核显功能 也没有定制核显输出补丁
- 蓝牙：需要蓝牙的自行更换AX200/AX210或博通Wi-Fi网卡，并使用OCLP-Mod打补丁。
- 隔空投送和接力：需要更换博通WI-FI网卡，并使用OCLP-Mod打补丁。
- iPhone 镜像：无解


#### 附注事项
- 此EFI需要关闭CFG Lock才能正常启动macOS，你需要在[这里](https://www.asus.com.cn/motherboards-components/motherboards/tuf-gaming/tuf-gaming-b560m-plus-wifi/helpdesk_bios?model2Name=TUF-GAMING-B560M-PLUS-WIFI)下载并更新2001版本的主板BIOS，并在Grub Shell里输入以下指令予以关闭：
```
setup_var 0x44 0x0
```
- 睡眠未测试，如果出现睡死问题，可使用终端强制关闭睡眠功能：
```
sudo pmset -a sleep 0
sudo pmset -a hibernatemode 0
sudo pmset -a disablesleep 1
```
- 此EFI理论可兼容**Catalina - Sonoma 13.x**系列老版本的macOS，但目前未做进一步测试。