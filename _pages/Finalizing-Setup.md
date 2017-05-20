---
title: "Finalizing Setup" #
lang: en
permalink: /finalizing-setup.html
---

To use the [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme) links on this page, you will need a torrent client like [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--info}

#### Overview of steps

{% capture notice-2 %}

The file `boot.firm` is what is launched by boot9strap itself after it finishes loading off of NAND, and can be any valid arm9 payload in the FIRM format. This file can be replaced at any time, although Luma3DS allows for the launch of other arm9 payloads in the FIRM format using the Luma3DS chainloader.
<br><br>
In this case, we use Luma3DS by [AuroraWright](https://github.com/AuroraWright/) to boot a patched SysNAND directly, allowing us to completely bypass the need for any kind of EmuNAND, vastly simplifying the usage of a hacked 3DS in addition to saving SD card space.
<br><br>
During this process, we also setup programs such as the following:    

+  **FBI** *(installs CIA formatted games and applications)*
+  **Themely** *(installs custom themes)*
+  **GodMode9** *(multipurpose tool which can do NAND and cartridge functions)*

{% endcapture %}

<div class="notice--info">{{ notice-2 | markdownify }}</div>

#### What you need

* The latest release of [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(the `.7z` file)*
* The latest release of [Themely](https://github.com/ErmanSayin/Themely/releases/latest) *(the `.cia` file)*
* The latest release of [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* The latest release of [FBI](https://github.com/Steveice10/FBI/releases/latest)

#### Instructions

##### Section I - Prep Work

1. Insert your SD card into your computer
1. Create a folder named `cias` on the root of your SD card if it does not already exist
1. Create a folder named `hblauncherloader` on the root of your SD card if it does not already exist
1. Copy `hblauncher_loader.cia` from the hblauncher_loader `.zip` to the `/cias/` folder on your SD card
1. Copy `lumaupdater.cia` from the Luma3DS Updater `.zip` to the `/cias/` folder on your SD card
1. Copy `FBI.cia` from the FBI `.zip` to the `/cias/` folder on your SD card
1. Copy `DSP1.cia` to the `/cias/` folder on your SD card
1. Copy `Themely.cia` to the `/cias/` folder on your SD card
1. Copy `boot.firm` from the Luma3DS `.7z` to the root of your SD card
1. Create a folder named `luma` on the root of your SD card
1. Create a folder named `payloads` in the `luma` folder on your SD card
1. Copy `GodMode9.firm` from the GodMode9 `.zip` to the `/luma/payloads/` folder on your SD card
1. Delete the 0.23.5 SystemUpdater folder from the root of your SD card
1. Extract the 0.25.3 SystemUpdater `.zip` to the root of your SD card
1. Reinsert your SD card into your device

##### Section II - Configuring Luma3DS

1. Boot your device to enter the Luma3DS configuration menu
  + If you get a black screen, [follow this troubleshooting guide](troubleshooting#ts_sys_b9s)
1. Use the (A) button and the D-Pad to turn on the following:    
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R"**
  + **"Show NAND or user string in System Settings"**
1. Press (Start) to save and reboot
  + If you get a black screen, just continue to the next section

##### Section III - Restoring the System

1. Using Dev Menu, navigate to the 0.25.3 SystemUpdater folder
1. Press (L + R + A) to install all CIAs
1. Navigate to the NATIVE_FIRM CIA
  + Old 3DS PANDA / SNAKE: `0004013800000002.cia`
  + New 3DS PANDA / SNAKE: `0004013820000002.cia`
1. Update your PANDA / SNAKE's FIRM by pressing (Start + Y) while highlighting the NATIVE_FIRM CIA
1. You can also update your PANDA / SNAKE using a CTR System Updater (CSU)
  + **This is only safe for Luma3DS version 6.6 (commit 0b16d88) and above!**
  + **Attempting to update your PANDA / SNAKE using a CSU on any lower Luma3DS version will BRICK your device!**

##### Section VI - CTRNAND Luma3DS

1. Reboot holding (Start) during boot to launch the Luma3DS chainloader menu
1. Launch GodMode9 by pressing (A)
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
1. Press (B) to return to the main menu
1. Hold (R) and press (B) at the same time to eject your SD card
1. Remove your SD card from your device
1. Press (Start) to reboot your device with your SD card removed
  + Booting your device at least once with your SD card removed will allow you to configure the CTRNAND based Luma3DS installation
1. Use the (A) button and the D-Pad to turn on the following:    
  + **"Show NAND or user string in System Settings"**
1. Reinsert your SD card into your device
1. Press (Start) to save and reboot

##### Section V - NAND Backup

1. Boot your device while holding (Start) to launch the Luma3DS chainloader menu
1. Launch GodMode9 by pressing (A)
1. Press (Home) to bring up the action menu
1. Select "More..."
1. Select "Backup NAND"
1. Press (A) to continue
1. Hold (R) and press (B) at the same time to eject your SD card
1. Insert your SD card into your computer
1. Copy `nand.bin` from the `/gm9out/` folder on your SD card to a safe location on your computer
  + Make backups in multiple locations (such as online file storage)
  + This backup will save you from a brick if anything goes wrong in the future
1. Delete `nand.bin` from the `/gm9out/` folder on your SD card after copying it
1. Reinsert your SD card into your device
1. Press (Start) to save and reboot

___

{% capture notice-11 %}
**Updating your PANDA / SNAKE using a CSU is only safe for Luma3DS version 6.6 (commit 0b16d88) and above!**    
**Attempting to update your PANDA / SNAKE using a CSU on any lower Luma3DS version will BRICK your device!**
{% endcapture %}

<div class="notice--danger">{{ notice-11 | markdownify }}</div>

Note that this guide does not have Luma3DS updater anymore due to its incompatibility with the name `boot.firm`. It will be re-added once it is updated to support Boot9Strap.
{: .notice--info}

{% capture notice-6 %}   
You will now boot Luma3DS CFW SysNAND by default.    
You can now hold (Select) on boot to launch the Luma3DS configuration menu.    
You can now hold (Start) on boot to launch the Luma3DS chainloader menu (note that the Luma3DS chainloader menu is only displayed if there is more than one payload detected).
You can now hold (Start) + (Select) + (X) on boot to dump the ARM11 bootrom (`boot11.bin`), the ARM9 bootrom (`boot9.bin`), and your console unique OTP (`OTP.bin`) to the `/boot9strap/` folder on your SD card.
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>

To use [NTR CFW](https://github.com/44670/BootNTR/), install [BootNTR Selector](https://gbatemp.net/threads/432911/).
{: .notice--info}

{% capture notice-7 %}
Remove any extra files and folders from the root of your SD card that are *not* in the following image:
<br><br>
![]({{ base_path }}/images/screenshots/final-file-layout.png)
{% endcapture %}

<div class="notice--info">{{ notice-7 | markdownify }}</div>

For information on using GodMode9's various features, check out the [GodMode9 Usage](godmode9-usage) page.
{: .notice--success}

For information on using Luma3DS's various features, check out [its wiki](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage).
{: .notice--success}

For information on installing custom themes, badges, and splash screens, check out [3dsthem.es](https://3dsthem.es/about.php).
{: .notice--success}
