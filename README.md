# Disclaimer

This EFI won’t work as it is. 

1. At least you have to change your `PlatformInfo`. 
 - Which is located in [`EFI/OC/config.plist`](https://github.com/walteweiss/Hackintosh-GA-Z87MX-D3H/blob/master/EFI/OC/config.plist), search for `PlatformInfo`. Look for keys: `MLB`, `ROM`, `SystemSerialNumber`, `SystemUUID`. 
 - It’s easy, more on that in [Dortania‘s guide](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html).
2. Maybe you have to check for other things, if you have different hardware, e.g. iGPU instead of dGPU. 

Don’t hesitate to ask if you have any questions.


# 2014 Haswell

- Guide Used: [OpenCore Desktop Guide](https://dortania.github.io/OpenCore-Desktop-Guide/)
- Installation Date: Mar 7, 2020

# Current Version

- Open Core: 0.8.3 `c9ba16f` released on Aug 1, 2022
- macOS Catalina, v.10.15.7 `19H2026` updated on Aug 03, 2022
- SMBIOS: iMac14,2

# Hardware

- MB [GA-Z87MX-D3H](Extra/Specification-GA-Z87MX-D3H.md) @ BIOS [F7 (of F7)](https://www.gigabyte.com/Motherboard/GA-Z87MX-D3H-rev-1x/support#support-dl-bios)
- CPU [Intel Core i7-4770](https://ark.intel.com/content/www/us/en/ark/products/75122/intel-core-i7-4770-processor-8m-cache-up-to-3-90-ghz.html) 4C/8T @ 3.4 GHz
- iGPU [Intel HD Graphics 4600](https://downloadcenter.intel.com/product/81496/Intel-HD-Graphics-4600)
- dGPU [Sapphire](https://www.sapphiretech.com/en/consumer/nitro-rx-580-4g-g5) [Radeon RX 580 4 GB](https://www.amd.com/en/products/graphics/radeon-rx-580)
- RAM 16 GB 1866 MHz DDR3
- Audio Codec Realtek **ALC892**
- Ethernet `00:00:00:00:00:00` **I217-V** from Intel 
- Wi-Fi + Bluetooth `00:00:00:00:00:00`  **BCM43602** 802.11ac


# [Kexts](./EFI/OC/Kexts/)

- AppleALC
- IntelMausi
- Lilu
- SMCProcessor
- SMCSuperIO
- VirtualSMC
- USBMap
- WhateverGreen

In alphabetical order. You have to load them differently, [the order matters](https://dortania.github.io/OpenCore-Install-Guide/config.plist/haswell.html#add-3). Search for `Kernel`, look for `Add` in [the config](./EFI/OC/config.plist). My order is: `Lilu`, `VirtualSMC`, `WhateverGreen`, then all the rest.

I compile them using [Lilu-and-Friends](https://github.com/corpnewt/Lilu-and-Friends). It’s easy, once you performed this at least once.

---

## SMBIOS Info

```
         Model: iMac14,2
      Board ID: Mac-2700000000000000
    FW Version: 141.0.0.0.0
 Hardware UUID: 00000000-0000-0000-0000-000000000000
 Serial Number: 000000000000
       Country:  D25 - Unknown
          Year:    N - 2014
          Week:    V - 50 (10.12.2014-16.12.2014)
          Line:  000 - 000 (copy 1)
         Model: 0000 - iMac14,2
   SystemModel: iMac (27-inch, Late 2013)
         Valid: Possibly
     System ID: 00000000-0000-0000-0000-000000000000
           ROM: 000000000000
           MLB: 00000000000000000
```

---

# BIOS Settings

## Home

- Home/Performance: Defaults
- Performance/Frequency: Defaults
- Performance/Memory: System Memory Multiplier is 18.66
- System: Defaults

## BIOS Features

All defaults

- OS Type: Windows 8 

**Disable:**

- Fast Boot


**Enable:**


## Peripherals

### Device Config

- Internal Graphics Memory Size: 64M
- DVMT Pre-Allocated (iGPU Memory): MAX
- EHCI Hand-off Enabled


# Recommended

**Disable:**

- Fast Boot
- VT-d (can be enabled if you set DisableIoMapper to YES)
- CSM
- Intel SGX
- Intel Platform Trust

**Enable:**

- VT-x
- Above 4G decoding
- Hyper-Threading
- Execute Disable Bit
- EHCI/XHCI Hand-off
- OS type: Windows 8.1/10 UEFI Mode
- DVMT Pre-Allocated (iGPU Memory): 64MB


## Not present in my BIOS

**Disable**

- Thunderbolt
- CFG Lock

**Enable**

- VT-x
- Above 4G decoding
- Hyper Threading
- Execute Disable Bit
