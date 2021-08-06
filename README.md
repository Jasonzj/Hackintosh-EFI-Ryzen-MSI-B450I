# Ryzen3700x & MSIB450I macOS BigSur OpenCore EFI

Geekbench 5: [CPU](https://browser.geekbench.com/v5/cpu/9190915) | [GPU](https://browser.geekbench.com/v5/compute/3195674)

## 配置清单

| 名称 | 品牌型号 | 备注 |
| --- | --- | --- |
| CPU | AMD3700X |  |
| 主板 | MSI B450ITX Gaming Plus AC |  |
| 散热器 | 恩杰海妖X52 |  |
| 内存 | 焰光戟 3600 8G * 2 |  |
| 硬盘 | 海康威视C2000pro 1T<br />西数 蓝盘 3T SATA6Gb/s 64MB | SSD + HDD |
| 机箱 | 恩杰 H210 |  |
| 电源 | 振华 LEADEX G 550 |  |
| 显卡 | XFX RX5700  |  |
| 无线网卡/蓝牙 | 博通 BCM94360CS2 | 需转接卡替换主板原有模块 M.2 Key E |

## 兼容情况

- [x] macOS 版本
    - [x] Big Sur 11.x
- [x] 睡眠/唤醒
- [x] 有线网卡
- [x] 无线网卡
- [x] 声卡
- [x] 蓝牙
    - [x] Airpods
    - [x] Trackpad 2
    - [x] Airdrop
    - [x] Handoff
- [x] 所有 USB 口

## EFI

- [OpenCore](https://github.com/acidanthera/OpenCorePkg) 0.7.2
- CPU by [AMD-Vanilla](https://github.com/AMD-OSX/AMD_Vanilla)
- ACPI
  - SSDT-EC-USBX-AMD.aml
- drivers
    - OpenHfsPlus.efi
    - OpenCanopy.efi
    - OpenRuntime.efi
- Kexts
    - [Lilu.kext](https://github.com/acidanthera/Lilu) 全家桶底层依赖
    - [VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC) 模拟SMC，传感器驱动依赖
    - [WhateverGreen.kext](https://github.com/acidanthera/WhateverGreen) 核显&显卡驱动
    - [AppleALC.kext](https://github.com/acidanthera/AppleALC) 声卡驱动
    - [RealtekRTL8111.kext](https://github.com/Mieze/RTL8111_driver_for_OS_X/) 有线网卡
    - [AMDRyzenCPUPowerManagement.kext](https://github.com/trulyspinach/SMCAMDProcessor) AMD电源管理
    - [SMCAMDProcessor.kext](https://github.com/trulyspinach/SMCAMDProcessor) AMD传感器
    - [AppleMCEReporterDisabler.kext](https://github.com/AMD-OSX/AMD_Vanilla/blob/opencore/Extra/AppleMCEReporterDisabler.kext.zip) 用于关闭 AppleMCERReport, AppleMCERReport会导致AMD CPU的内核崩溃
    - AMD-USB-Map.kext USB by [USB Map Guide](https://dortania.github.io/OpenCore-Post-Install/usb/)
    <!-- - [AirportBrcmFixup.kext](https://github.com/acidanthera/AirportBrcmFixup) 无线网卡
    - [BrcmFirmwareData.kext](https://github.com/acidanthera/BrcmPatchRAM) 蓝牙
    - [BrcmPatchRAM2.kext](https://github.com/acidanthera/BrcmPatchRAM) 蓝牙
    - [BrcmBluetoothInjector.kext](https://github.com/acidanthera/BrcmPatchRAM) 蓝牙 -->

## docker解决方案
- [homebrew-docker-virtualbox](https://github.com/sergeycherepanov/homebrew-docker-virtualbox)
## 教程
- [OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)
- [黑果小兵-精解OpenCore](https://blog.daliansky.net/OpenCore-BootLoader.html)
- [使用 OpenCore 引导黑苹果](https://blog.xjn819.com/post/opencore-guide.html)