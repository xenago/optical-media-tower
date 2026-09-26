# optical-media-tower

Documentation on building a [hybrid DAS optical media tower rig build](res/exterior_3.jpg).

## Goal

A chassis with an internal PC that can directly read [multiple optical drives](res/exterior_1.jpg), but which can also connect to an external PC to expose all those drives over USB, JBOD/DAS-style.
This would be a one-stop shop for all my CD/DVD/BD/UHD disc burning/ripping/copying/testing needs.

Objectively, such a setup is rarely needed but if you are someone like me with thousands of optical discs this kind of thing is almost a must-have. A cheaper alternative would be to use a handful of refurb laptop drives with USB adapters, like the LG BU40N or Chinese cross-flashed Pioneers.

## PC Parts

Most of these parts should be relatively interchangeable with a bit of common sense. For example, even though the new empty Copystars cases are now hard to find, it is still quite easy to get random CD duplicators on eBay which should be possible to use similarly after some gutting. And instead of [individual powered USB-SATA adapters](interior_2.jpg) things like SATA port expanders could theoretically be used. Note that compatibility with optical drives is mixed in some models because that use-case is dwindling in popularity.

| Part | Price | Notes |
| --- | --- | --- |
| [Copystars TW-5](https://www.amazon.ca/dp/B00FPFPR4Y) | 154.32 CAD | "Copystars Duplicator case for Build Blu-ray-CD-DVD-duplicator Tower + Power Supply (5 Bay)". Out of stock |
| [JetKVM ethernet KVM/IPMI device](https://www.ikoolcore.com/products/jetkvm?variant=51115329388831) | 103.00 USD | Since this is the only device of its kind with native 12V DC power control for mini PCs |
| [JetKVM DC Power Control Extension](https://www.ikoolcore.com/products/dc-power-control-extension-for-jetkvm?variant=51333765398815) | 20.00 USD | Allows [powering on/off the mini PC remotely](res/screen_jetkvm_dc_power_control.png) |
| [wo-we H5 Mini PC](https://www.amazon.ca/dp/B0F9FBTXS2): Intel N150 (Twin Lake, 4C4T), 16GB DDR4 RAM, 512GB NVMe M.2 SSD, Dual HDMI, 2.5G RJ45 | 247.47 CAD | Main reason I picked was for the RAM/USB/HDMI configuration. Out of stock; original listing I actually bought from was swapped out for something different, hate Amazon fraud! |
| [90mm Nylon Magnetic Dust Filter](https://www.amazon.ca/dp/B0D128GN6F) | 14.68 CAD | For rear case intake, had leftovers from this pack |
| [Cudy 5-Port Gigabit Ethernet Network Switch, USB-C Power Input, GS105U](https://www.amazon.ca/dp/B0DLNBKG9C) | 18.07 CAD | Includes USB-A to USB-C cable for power. A 2.5G switch instead would be ideal to max out the PC's network file transfer speed, but this is cheap and easy |
| [Haokiang 1ft RJ45 Ethernet Extension Cable Cat6 Network Patch Cable Male to Female](https://www.amazon.ca/dp/B07FXJGY91) | 13.55 CAD | |
| [Monoprice 115125 5-Pack, Slim Run Cat6A Ethernet Network Patch Cable, 1', Black](https://www.amazon.ca/dp/B01BGV2C7U) | 13.56 CAD | |
| [KCEVE 10Gbps USB-C Switch 4 USB 3.2 Gen 2 Ports between 2 computers](https://www.amazon.ca/dp/B0D5B4G381) | 59.99 CAD | Out of stock; original Amazon listing I actually bought from was swapped out for something different, hate Amazon fraud |
| [UGREEN 10Gbps USB-A male to USB-C female Adapter](https://www.amazon.ca/dp/B0CY1Y3TSQ) | 11.85 CAD | For connecting the USB switch to the mini PC USB-A port, had one left over from this pack |
| [Rosonway Powered USB Hub, 7 Ports USB 3.2 Gen 2 Data Hub 10Gbps, RSH-A107](https://www.amazon.ca/dp/B0BTNTZ4BW) | 61.85 CAD | Be careful since these ports can be individually disabled with the buttons |
| 5x [WAVLINK SATA III to 5Gbps USB 3.0 Type-A Hard Drive Cable, ST345A](https://www.amazon.ca/dp/B0CRTZ65T1) | 84.69 CAD | Version without power adapter |
| 4x 2-pack [QIANRENON SATA Male to DC Connectors, SATA to 5.5 \* 2.1 DC Male Cable](https://www.amazon.ca/dp/B09XHRFY6G) | 67.75 CAD | Sold in pairs. Using one for each drive, plus one for the USB hub, and one for the IPMI DC extension powering the KVM and mini PC |
| **Total** | **~920 CAD** | |

## Drives

Of course, any 5.25in drives can be used. These are the ones I picked to cover all my bases, purchased at different times so some are available and some aren't:

| Drive | Price | Notes |
| --- | --- | --- |
| [Pioneer BDR-S13C-X](https://www.ebay.ca/str/youculbb) | 475.00 USD | Legit original firmware. Off-the-books eBay deal |
| [ASUS BW-16D1HT](https://www.amazon.ca/dp/B00DWFPDJI) | 154.80 CAD | Reflashed with omnidrive firmware for use with redump for CDs and video games |
| [LG WH14NS40](https://www.amazon.ca/dp/B007VPGL5U) | 90.39 CAD | Reflashed with WH16NS58 scan-capable firmware |
| [Pioneer BDR-S11JX](https://www.ebay.ca/itm/358048263812) | 171.47 USD | Chinese rebuild/reflash |
| [Pioneer BDR-S11JX](https://www.ebay.ca/itm/397800006124) | 217.35 USD | Chinese rebuild/reflash |
| **Total** | **~1450 CAD** | 863.82 USD (~1.4 conversion rate in 2025) + 245.19 CAD |

**Drives + PC parts = ~2375 CAD / ~1700 USD**

## Connections

- Each drive has a WAVLINK SATA adapter, which uses a SATA Male to DC for power and is plugged into the USB hub for connectivity.
- The USB hub is plugged into the USB-C port on the USB switch.
- PC port 1 on the USB switch is to the [internal mini PC](res/screen_all_drives_appearing_in_mini_pc_os.png), port 2 is to the [external PC](res/screen_all_drives_plus_one_more_appearing_in_external_usb-c_pc.png).
- Network switch: USB power from the hub.

## Quirks

- [Double sided tape used all over.](res/interior_1.jpg)
- Cables for the SATA adapters are too long so they all had to be carefully wrapped and organized below the bottom disc reader to get out of the way.
- Case PSU has only female SATA power connectors which is one reason for the weird workarounds.
- Flipped rear fan to intake, added magnetic dust filter since the PSU is already exhausting air from inside.
- [Need to make sure the PSU is powered on before the USB is plugged into another source](res/exterior_2.jpg), or the drives won't initialize to the external source.
- Need to avoid pressing the switch while the drives are actually being used.
- Finicky USB hub due to power switches.
- Need to go into BIOS to set always booting up on power reconnection after loss.
- There exists some board that was originally intended to be used with these cases to very easily turn it into a USB JBOD, but that board is virtually impossible to find now. Here is the [2-port version](https://www.amazon.com/dp/B00CMX9BP8) for example, and the Addonics AD5HPMREU HPM-XU is a 5-port version which would be perfect for this use-case ([Lindy](https://int.lindy.com/cables-adapters-c1/i-o-c125/usb-3-0-esata-to-5-sata-port-multiplier-raid-adapter-p7315), [Amazon](https://www.amazon.com/LINDY-eSATA-Multiplier-Adapter-51158/dp/B00DU6X7G0)). Or Lycom UB-208RM.
