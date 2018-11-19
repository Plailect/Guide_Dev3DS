---
title: "A9LH to B9S"
permalink: /a9lh-to-b9s.html
---

This page is for existing arm9loaderhax users to update their devices to boot9strap.
{: .notice--info}

All future releases of Luma3DS will only be made in the `.firm` format, which will only be compatible with boot9strap and sighax. This means that to continue receiving the latest updates of Luma3DS, you should use this page to update your installation.
{: .notice--info}

If you have a PIN enabled on Luma3DS, SafeB9SInstaller will give you an "OTP Crypto Fail" error unless you temporarily disable your PIN (you can re-enable the PIN after the update).
{: .notice--warning}

To use the [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme) links on this page, you will need a torrent client like [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--info}

#### What you need

Note that the following required file named `secret_sector_dev.bin` is the same one that was found in `safea9lhinstaller_v2_panda.zip` with the name `secret_sector.bin`. If you already have that file on your disk somewhere, you can use that one (renaming it) instead of downloading the one below.
{: .notice--info}

Note that `secret_sector_dev.bin` is needed to revert the arm9loaderhax exploit, which is why it is not needed for the installation of boot9strap on a stock console.
{: .notice--info}

* <i class="fa fa-magnet" aria-hidden="true" title="This is a magnet link. Use a torrent client to download the file."></i> - [`secret_sector_dev.bin`](magnet:?xt=urn:btih:54d19b7fd5387f7d46cff86edbbb58737880993c&dn=secret_sector_dev.bin&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce)
* The latest release of [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(the `.7z` file)*
* The latest release of [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* The latest release of [boot9strap](https://github.com/SciresM/boot9strap/releases/latest)
* The latest release of [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)

#### Instructions

##### Section I - Prep Work

1. Power off your device
1. Insert your SD card into your computer
1. Create a folder named `boot9strap` on the root of your SD card
1. Copy `boot.firm` from the Luma3DS `.7z` to the root of your SD card
1. Copy `GodMode9.firm` from the GodMode9 `.zip` to the `/luma/payloads/` folder on your SD card
1. Copy the `gm9` folder from the GodMode9 `.zip` to the root of your SD card
  + Delete any existing `.bin` payloads in this folder as they will not be compatible with boot9strap compatible Luma3DS versions
1. Copy `SafeB9SInstaller.bin` from the SafeB9SInstaller `.zip` to the `/luma/payloads/` folder on your SD card
1. Copy `boot9strap_dev.firm` and `boot9strap_dev.firm.sha` from the boot9strap `.zip` to the `/boot9strap/` folder on your SD card
1. Copy `secret_sector_dev.bin` to the `/boot9strap/` folder on your SD card
1. Reinsert your SD card into your device

##### Section II - Installing boot9strap

1. Boot your device while holding (Start) to launch the Luma3DS chainloader menu
1. Launch SafeB9SInstaller by pressing (A) on it
1. Wait for all safety checks to complete
1. When prompted, input the key combo given to install boot9strap
1. Once it has completed, your device will reboot automatically

##### Section III - Configuring Luma3DS

This section is only needed if you are prompted with the Luma3DS configuration menu after the reboot.
{: .notice--info}

1. In the Luma3DS configuration menu, use the (A) button and the D-Pad to turn on the following:    
  + **"Show NAND or user string in System Settings"**
1. Press (Start) to save and reboot

##### Section IV - CTRNAND Luma3DS

1. Reboot holding (Start) during boot to launch the Luma3DS chainloader menu
1. Launch GodMode9 by pressing (A)
1. If you are prompted to create an essential files backup, press (A) to do so, then press (A) to continue once it has completed
1. Navigate to `[0:] SDCARD` -> `luma` -> `payloads`
1. Press (X) on `SafeB9SInstaller.bin` to delete it
1. Press (A) to confirm
1. Press (B) to return to `[0:] SDCARD`
1. Press (Y) on `boot.firm` to copy it
1. Press (B) to return to the main menu
1. Navigate to `[1:] SYSNAND CTRNAND`
1. Press (Y) to paste a copy of `boot.firm`
1. Select "Copy path(s)"
1. Press (A) to unlock SysNAND (lvl1) writing, then input the key combo given
1. Press (X) on `arm9loaderhax.bin` to delete it
1. Press (A) to confirm
1. Press (B) to return to the main menu
1. Hold (R) and press (B) at the same time to eject your SD card
1. Remove your SD card from your device
1. Press (Start) to reboot your device with your SD card removed
  + Booting your device at least once with your SD card removed will allow you to configure the CTRNAND based Luma3DS installation
1. Use the (A) button and the D-Pad to turn on the following:    
  + **"Show NAND or user string in System Settings"**
1. Reinsert your SD card into your device
1. Press (Start) to save and reboot

___

You can now remove any arm9loaderhax related files from your SD card, such as `arm9loaderhax.bin` on the root of your SD card and the `files9` folder on your SD card.
{: .notice--info}

{% capture notice-6 %}   
You can now hold (Select) on boot to launch the Luma3DS configuration menu.    
You can now hold (Start) on boot to launch the Luma3DS chainloader menu (note that the Luma3DS chainloader menu is only displayed if there is more than one payload detected).
You can now hold (Start) + (Select) + (X) on boot to dump the ARM11 bootrom (`boot11.bin`), the ARM9 bootrom (`boot9.bin`), and your console unique OTP (`OTP.bin`) to the `/boot9strap/` folder on your SD card.
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>

{% capture notice-11 %}
**Updating your PANDA using a CSU is only safe for Luma3DS version 6.6 (commit 0b16d88) and above!**    
**Attempting to update your PANDA using a CSU on any lower Luma3DS version will overwrite your B9S installation!**
{% endcapture %}

<div class="notice--danger">{{ notice-11 | markdownify }}</div>
