<p align="center">

<img src="https://i.loli.net/2020/01/06/6ZNseqdxyGVlwPb.png" width="300px" alt="logo">

</p>

<h1 align="center">macOS on Tongfang Laptops</h1>


<p align="center">
<img src="https://img.shields.io/badge/build-passing-brightgreen.svg"/> 

<img src="https://img.shields.io/badge/bootloader-OpenCore-lightgrey.svg"/> 

<img src="https://img.shields.io/badge/supported_macOS_version-10.15.x-9cf.svg"/>

<img src="https://img.shields.io/badge/built_by-Yume_Maruyama-ff69b4.svg"/> 
</p>

![QQ20200106-200142@2x.jpg](https://i.loli.net/2020/01/06/jHEMaG3wPbiKWc2.jpg)

<h3 align="center">
    <a href="https://github.com/kirainmoe/hasee-tongfang-macos/blob/oc-general/Changelog.md">Changelog</a> | <a href="https://github.com/kirainmoe/hasee-tongfang-macos/blob/oc-general/README.md">简体中文</a>
</h3>

This repo contains the OpenCore config for installing latest macOS on Tongfang (Tsinghua Tongfang) barebones-based 8th/9th generation platform laptops, like some Hasee, Mechrevo, OverPowered, Monster, Avell devices.

## Tutorial

- Download [Tongfang Hackintosh Utility](https://github.com/kirainmoe/tongfang-hackintosh-utility/releases) and customize the OpenCore config for your model
- Download a latest version of macOS from somewhere
- Use BalenaEtcher / Unibeast / etc. to make a installer flash
- Part your disk that you are going to install macOS (You should have a GUID partition table and a 200M+ ESP part)
- Copy `BOOT` and `OC` folder you gained in the first step
- Disable `Secure Boot`, `Launch CSM` and change to `UEFI Mode` in BIOS
- Boot from flash and install macOS
- After boot into the system, use [Tongfang Hackintosh Utility](https://github.com/kirainmoe/tongfang-hackintosh-utility/releases) (for macOS) to fix the sleep
- Enjoy your hackintosh build!

## Better Experience


[Tongfang Hackintosh Utility: all-in-one hackintosh toolbox](https://github.com/kirainmoe/project-starbeat/releases) 

[AUCC - keyboard light controller](https://github.com/rodgomesc/avell-unofficial-control-center) (Support ITE revision 0.03 only)


## Compatibility

### macOS version

The latest EFI config only supports **macOS Catalina 10.15.x**. Currently tested version is **10.15.3 (19D76)**.

### Models

> Notes: I was not sure that some models can work perfectly with this config. The models listed in the following table are those would be theoretically supported gussing by their barebone model.

#### Tips

- If you have 8th gen platform laptops, try one of { *GK5CN6X, GK5CN5X, GJ5CN6X, GI5CN5X* }.
-  If you have 9th gen platform laptops, try one of { *GK7CP6R, GK5CP6X* }.

Please use [Tongfang Hackintosh Utility](https://github.com/kirainmoe/project-starbeat/releases) to download / customize the OC config.


| Barebone | Models Theoretically Supported | Which model you should choose in Tongfang Hackintosh Utility | Generation
|-----|------|-----|------|
| GK5CN5X <br> GK5CN6X <br> GK5CN6Z <br> GK5CN5Z <br>GK7CN6S<br>GK7CN5S | Hasee Z7(m)-KP7/5(G)Z <br> Shinelon Yao 7000 II <br> Mechrevo Z2 Air <br>XMG Neo 15<br>OverPowered Gaming Laptop 15<br>MACHENIKE F117-B1/2 <br> Monster Abra A7 v10.1 <br>Overpowered 17+ laptop <br> EVOO 15.6" model laptops (LP4 / LP5) | GK5CN6X / GK5CN5X | 8th Generation |
| GJ5CN64 <br> GI5CN54 | Hasee Z7(m)-KP7/5GC/GA/EC<br>Avell A52-5 BS<br>CyberPower NB-408-109<br>Machenike T90 | GJ5CN64 <br> GI5CN54 | 8th Generation |
| GK7CP6R | Hasee Z7-CT7GK / Z7-CT7VA / Z7-CT7VH / G7-CT7VK<br>Illegear Rogue Laptop<br>XMG Core 17<br>Mechrevo X3<br>CyberPowerPC Tracer-III-17<br>Monster Tulpar T7 v19.3  | GK7CP6R | 9th Generation |
| GK5CP6X | Hasee Z7M-CT7GS <br> Mechrevo Z2 Air-G | GK5CP6X / GK5CP5X  | 9th Generation | 

## Device Specifications

| Component | Model | Comment |
|--|--|---|
| CPU | Intel Core(TM) i7-8750H (9750H)  | i5-8300H and i5-9300H are compatible |
| GPU | Intel UHD630 / Nvidia GTX 1050(Ti),1060, 1650, 1660Ti; RTX2060 | Nvidia GPU has no solution currently (and permanently). For more reason, please refer to [this.](https://github.com/kirainmoe/hasee-tongfang-macos/wiki/%E5%AE%89%E8%A3%85%E5%90%8E%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94#%E9%82%A3%E4%B8%BA%E4%BB%80%E4%B9%88%E7%8B%AC%E6%98%BE%E6%97%A0%E6%B3%95%E9%A9%B1%E5%8A%A8) |
| RAM | Micron Crucial 8GB+8GB | |
| NVMe | WD Black SN750 NVME SSD 500G | Samsung PM981/970EvoPlus were not supported by macOS | 
| SATA SSD | Phison SATA SSD 128G | | 
| Wireless | BCM94360CS2 | Intel wireless cards have no driver. |
| Ethernet | Realtek RTL8168H | |
| Audio | Realtek ALC269vc | |

## Working Functions

- Turbo boost and CPU frequency stage.
- Intel UHD Graphics 630
- Brightness control and Fn keys
- I2C HID Touchpad
- Realtek Ethernet
- Bluetooth (No Airdop if you are using Intel Bluetooth)
- Audio (Realtek ALC269vc, using AppleALC + layout-id 29)
- Battery status (using Clover hotpatch)
- USB 3.0 and Type-C
- Sleep
- Camera
- etc.

### What's partially working

- PS/2 Touchpad (Tongfang GI5CN54/GJ5CN64)

### What's not working

- Nvidia discrete GPU (used SSDT to disable it)
- Intel Wireless Card
- HDMI/mini DP (which is connected to DGPU directly)
- SD Card reader

## Contribute

Issues & Pull request are welcomed.

## License

`hasee-tongfang-macos` is [MARUYAMA](https://github.com/kirainmoe/hasee-tongfang-macos/blob/oc-general/LICENSE) Licensed. You can use the config for free under the Maruyama License.
