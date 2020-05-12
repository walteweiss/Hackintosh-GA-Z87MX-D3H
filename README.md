# Disclaimer

You can use this EFI on your own hardware, if it’s similar to what is below, but keep in mind, you have to [generate your own serial numbers](https://dortania.github.io/OpenCore-Desktop-Guide/post-install/iservices.html#generate-a-new-serial), since mine are all zeroed and won’t work. I have no idea whether my aml-files (aka DSDT) will work on your hardware, even if you have the very same motherboard with the very same BIOS version, so I’d recommend you to read it through as well, it’s quite easy.

# Logs

- [Issues](Extra/Log/Issues)
- [Updates/](Extra/Log/Updates)
 - [macOS Updates](Extra/Log/Updates/macOS/) 
 - [OC Updates](Extra/Log/Updates/OC/)

---

Guide used: [OpenCore Desktop Guide](https://dortania.github.io/OpenCore-Desktop-Guide/).

---

# 2014 Haswell

- Installation Date: Mar 7, 2020
- Open Core: v.0.5.8 (001340f) released on May 4, 2020
- macOS Catalina, v.10.15.4 (19E287)
- SMBIOS: iMac14,2

# Hardware

- MB [GA-Z87MX-D3H](Extra/Specification-GA-Z87MX-D3H.md) @ BIOS [F6 (of F7)](https://www.gigabyte.com/Motherboard/GA-Z87MX-D3H-rev-1x/support#support-dl-bios)
- CPU [Intel Core i7-4770](https://ark.intel.com/content/www/us/en/ark/products/75122/intel-core-i7-4770-processor-8m-cache-up-to-3-90-ghz.html) 4C/8T @ 3.4 GHz
- iGPU [Intel HD Graphics 4600](https://downloadcenter.intel.com/product/81496/Intel-HD-Graphics-4600)
- dGPU [Sapphire](https://www.sapphiretech.com/en/consumer/nitro-rx-580-4g-g5) [Radeon RX 580 4 GB](https://www.amd.com/en/products/graphics/radeon-rx-580)
- RAM 16 GB 1866 MHz DDR3
- Audio Codec Realtek ALC892
- Ethernet `00:00:00:00:00:00` **I217-V** from Intel 
- Wi-Fi + Bluetooth `00:00:00:00:00:00`  **BCM43602** 802.11ac


# Kexts

- AppleALC.kext
- IntelMausiEthernet.kext
- Lilu.kext
- SMCProcessor.kext
- SMCSuperIO.kext
- USBInjectAll.kext
- VirtualSMC.kext
- WhateverGreen.kext

---

## SMBIOS Info

```
         Model: iMac14,2
      Board ID: Mac-0000000000000000
    FW Version: 141.0.0.0.0
 Hardware UUID: 00000000-0000-0000-0000-000000000000
 Serial Number: 000000000000
       Country:  000 - Unknown
          Year:    N - 2014
          Week:    V - 50 (10.12.2014-16.12.2014)
          Line:  000 - 815 (copy 1)
         Model: 0000 - iMac14,2
   SystemModel: iMac (27-inch, Late 2013)
         Valid: Possibly
     System ID: 00000000-0000-0000-0000-000000000000
           ROM: 000000000000
           MLB: 00000000000000000
```

---

## BIOS Settings

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
- DVMT Pre-Allocated(iGPU Memory): 64MB


### Not present in BIOS

**Disable**

- Thunderbolt
- CFG Lock

**Enable**

- VT-x
- Hyper Threading
- Execute Disable Bit

I cannot get access to my BIOS due to some unknown bug, I have no idea what to do, so this section may be not entirely correct. I’ll update it when I’ll be able to login there.
