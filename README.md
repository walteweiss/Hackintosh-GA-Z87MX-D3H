# 2014 Haswell

- Guide Used: [OpenCore Desktop Guide](https://dortania.github.io/OpenCore-Desktop-Guide/)
- Installation Date: Mar 7, 2020

# Current Version

- Open Core: v.0.5.9 (64396ae) released on Jun 1, 2020
- macOS Catalina, v.10.15.5 (19F101) updated on June 02, 2020
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

- AppleALC
- IntelMausiEthernet
- Lilu
- SMCProcessor
- SMCSuperIO
- VirtualSMC
- USBInjectAll
- WhateverGreen

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

## Recommended

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

## Real

**Disable:**


**Enable:**


## Not present in BIOS

**Disable**

- Thunderbolt
- CFG Lock

**Enable**

- VT-x
- Hyper Threading
- Execute Disable Bit
