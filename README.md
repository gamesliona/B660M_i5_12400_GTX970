### Hackintosh Setup Intel i5-12400 + Nvidia GTX 970 on Monterey.

![Screenshot 2023-05-16 at 19 46 03](https://github.com/gamesliona/B660M_i5_12400_GTX970/assets/39834884/8258fd69-d40b-4710-82be-101916d31af2)

### PC Build Specifications:

- MB: Gigabyte B660M DS3H DDR4
- CPU: Intel i5 12400F
- GPU: MSI Nvidia GTX 970
- RAM: 32 GB Kingston 3200Mhz DDR4
- Storage: 1 TB Kingston M.2 SNV2S
- Bluetooth: BCM_4350C2 USB Dongle
- WIFI: TL-WN 723n USB Dongle
- LAN: Intel 2.5 Gb Ethernet
- Sound: Realtek ALC897

### What works and what doesn't:

| Service  | Status |
| ------------- | ------------- |
| Sleep/Wake  | Working ✅ |
| GTX 970 Graphics Acceleration | Working ✅ |
| Wi-Fi | Working through the Manufacter's Program, no native support. ⚠️ |
| Bluetooth | Working only with basic devices. Connecting to iPhone won't work. No Airdrop. |
| Speakers | Working ✅ |
| iMessage, Appstore | Working ✅ |
| Airdrop/Handoff | Not working ⛔ |
| DVI Monitor Port/Dual Monitors | Not working ⛔ |

#### BIOS Settings.
Content took from *serouin*.

Recommend you should `Load Optimized Default` first. Then save and restart and go to BIOS again.

### Tweaker:

* CPU Upgrade: **Gaming Profile** (I don't use the E-Core so I disabled it)

* Extreme Memory Profile: **Profile 1**

* Advanced CPU Settings:

  - Hyper-Threading Technology: **Enabled**

  - Intel Turbo Boost Technology: **Auto**

- Advanced Memory Setting:
    - Memory Enhancement Setting: **Enhanced Performance**

### Settings:

* Platform Power:

  - ErP: **Disable**

  - Power Loading: **Enabled**
  
* IO Ports:

  - Initial Display Output: **PCIe 1 Slot**

  - Above 4G Decoding: **Enabled**

  - Above 4G MMIO BIOS assignment: **Disabled**

  - Super IO Configuration → Serial Port: **Disabled** 

  - USB Configuration:
    - XHCI Hand-off → **Enabled**
    - Legacy USB Support → **Enabled**
    - USB Mass Storage Driver Support → **Enabled**
    - Port 60/64 Emulation → **Disabled**

  - Network Stack Configuration → Network Stack: **Disabled**
  
* Miscellaneous:

  - Intel Platform Trust Technology(PTT) → **Disabled**

  - Vt-d → **Disabled**

### Boot: 

  - CFG Lock: **Disabled**

  - Fast Boot: **Disable Link**

  - Windows 10 Features: **Windows 10**

  - CSM Support: **Disabled**

  - Secure Boot: **Disabled** (Secure Boot will be disabled by default, but good to check)

## NVIDIA & OCLP Setup:
Boot arguments required: 
- amfi_get_out_of_my_way=0x1
- ngfxcompat=1
- ngfxgl=1
- nvda_drv_vrl=1
EFI is setup for it: Nvidia Boot-args, Lowered SIP.

Install OCLP from: https://github.com/dortania/OpenCore-Legacy-Patcher/releases/tag/0.6.5. 
After install you can enable Beta Blur from Non-Metal Settings, looks a bit better.

(note: I have been experiencing multiple Kernel Panics due to the HDMI cable and second monitor. The errors were looking like: AppleKeyStore Operation Failed). Solution was either changing the cable or removing the second monitor.)

## Credits
* Apple
* OpenCore for making this possible
* serouin for his EFI build










