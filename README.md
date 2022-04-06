# prime-x570-pro-hackintosh

> 基于 OpenCore0.7.9 的 X570 主机黑苹果配置分享。

* 官方教程：https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html

![Overview](./Assets/overview.png)

## 电脑配置

* 主板：[华硕（ASUS）PRIME X570-PRO 主板](https://www.asus.com/Motherboards-Components/Motherboards/All-series/PRIME-X570-PRO/)
* CPU：AMD 锐龙9 5900X
* 显卡：[华硕（ASUS）TUF Gaming 3 AMD Radeon RX 5600XT](https://www.asus.com/Motherboards-Components/Graphics-Cards/All-series/TUF-3-RX5600XT-O6G-EVO-GAMING/)
* SSD：Toshiba Q200EX（480G）

BIOS：[Version 4204](https://www.asus.com/Motherboards-Components/Motherboards/All-series/PRIME-X570-PRO/HelpDesk_BIOS/)，更新于 `2022/03/07` 。

## 其他说明

平台信息请按照教程[PlatformInfo](https://dortania.github.io/OpenCore-Install-Guide/AMD/zen.html#platforminfo)，自行修改，建议使用 `iMacPro1,1` 。也就是下面这部分：

```
<key>PlatformInfo</key>
<dict>
  <key>Automatic</key>
  <true/>
  <key>CustomMemory</key>
  <false/>
  <key>Generic</key>
  <dict>
    <key>AdviseFeatures</key>
    <false/>
    <key>MLB</key>
    <string>M0000000000000001</string>
    <key>MaxBIOSVersion</key>
    <false/>
    <key>ProcessorType</key>
    <integer>0</integer>
    <key>ROM</key>
    <data>ESIzRFVm</data>
    <key>SpoofVendor</key>
    <true/>
    <key>SystemMemoryStatus</key>
    <string>Auto</string>
    <key>SystemProductName</key>
    <string>iMacPro1,1</string>
    <key>SystemSerialNumber</key>
    <string>W00000000001</string>
    <key>SystemUUID</key>
    <string>00000000-0000-0000-0000-000000000000</string>
  </dict>
  <key>UpdateDataHub</key>
  <true/>
  <key>UpdateNVRAM</key>
  <true/>
  <key>UpdateSMBIOS</key>
  <true/>
  <key>UpdateSMBIOSMode</key>
  <string>Create</string>
  <key>UseRawUuidEncoding</key>
  <false/>
</dict>
```

修改好后可以正常登录，同步。

![iCloud](./Assets/iCloud.png)

* 当前分支`monterey-5900x-0.7.9`使用的是 debug 版本的 opencore。后期完成调试将转换为release。
* 当前系统 `macOS Monterey 12.x`。
* 如果有内置硬盘被识别外置，请在`DeviceProperties`内的添加对应的`Device Path`，通过 hackintool 查看。我的 config 文件中添加了两个，作为示例。
* 如果CPU不同请参考[Kernel patches](https://github.com/AMD-OSX/AMD_Vanilla/tree/master)
* 如果你没有免驱 AMD 显卡，用的是 1070Ti，之前最高只支持 10xx 系列，只能安装 10.13.x，可参考我以前写的博文[AMD 黑苹果小记（Prime X570 Pro + Ryzen 3700X + 1070 Ti）](https://www.whidy.net/amd-hackintosh-note-with-asus-prime-x570-pro-ryzen-3700x-nvidia-1070ti)。

有其他问题可以提 issues，有空我会看看~
