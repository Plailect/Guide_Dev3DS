---
title: "Updating B9S"
permalink: /updating-b9s.html
---

This page is for existing boot9strap users to update their installation of boot9strap to the latest version.
{: .notice--info}

Note that the recent major release of Luma3DS is *not* compatible with boot9strap version 1.0. It *requires* you to update your boot9strap installation to version 1.2 by following the instructions on this page.
{: .notice--warning}

{% capture notice-1 %}
There have been reports of a wave of bans being handed out to CFW users by Nintendo. To protect yourself, please do the following steps before starting this guide:

1. Go to System Settings, then "Internet Settings", then "SpotPass", then "Sending of System Information"
1. Disable the "Sending of System Information" option
1. Exit the System Settings
1. Go to your Friend's List (the Face Icon in the top row of your Home Menu)
  + If you receive an error and are kicked out of the menu, the Friend's List setting is already disabled
1. Go to the Friend's List settings, then "Friend Notification Settings", then "Show friends what you're playing"
1. Disable the "Show friends what you're playing" option
1. Exit your Friend's List

{% endcapture %}

<div class="notice--danger">{{ notice-1 | markdownify }}</div>

#### What you need

* The latest release of [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(the `.7z` file)*
* The latest release of [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* The latest release of [boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *(standard boot9strap; not the `devkit` file, not the `ntr` file)*
* The latest release of [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* The latest release of [the Homebrew Launcher](https://github.com/fincs/new-hbmenu/releases/latest)

#### Instructions

##### Section I - Prep Work

For all steps in this section, overwrite any existing files on your SD card.
{: .notice--info}

1. Power off your device
1. Insert your SD card into your computer
1. **Leave the old (v7.1) version of Luma3DS (`boot.firm`) as it is. You will update this later.**
1. Copy `boot.3dsx` to the root of your SD card
1. Create a folder named `boot9strap` on the root of your SD card
1. Copy `GodMode9.firm` from the GodMode9 `.zip` to the `/luma/payloads/` folder on your SD card
1. Copy the `gm9` folder from the GodMode9 `.zip` to the root of your SD card
1. Copy `SafeB9SInstaller.firm` from the SafeB9SInstaller `.zip` to the `/luma/payloads/` folder on your SD card
1. Copy `boot9strap.firm` and `boot9strap.firm.sha` from the boot9strap `.zip` to the `/boot9strap/` folder on your SD card
1. Reinsert your SD card into your device

##### Section II - Installing boot9strap

1. Reboot holding (Start) during boot to launch the Luma3DS chainloader menu
1. Launch SafeB9SInstaller by pressing (A)
1. Wait for all safety checks to complete
1. When prompted, input the key combo given to install boot9strap
1. Once it has completed, press (A) to reboot your device.
1. Power off your device
  + Note that you will receive the error `Unsupported launcher (argc = 0)` until you follow the rest of the instructions on this page

##### Section III - Updating Luma3DS

1. Insert your SD card into your computer
1. Delete the existing `boot.firm` from the root of your SD card
1. Copy `boot.firm` from the Luma3DS `.7z` to the root of your SD card
1. Reinsert your SD card into your device

##### Section IV - Configuring Luma3DS

1. Your device should have rebooted into the Luma3DS configuration menu
  + If you get a black screen, [follow this troubleshooting guide](troubleshooting#ts_sys_b9s)
1. Use the (A) button and the D-Pad to turn on the following:    
  + **"Show NAND or user string in System Settings"**
1. Press (Start) to save and reboot

##### Section V - CTRNAND Luma3DS

1. Reboot holding (Start) during boot to launch the Luma3DS chainloader menu
1. Launch GodMode9 by pressing (A)
1. If you are prompted to create an essential files backup, press (A) to do so, then press (A) to continue once it has completed
1. Navigate to `[0:] SDCARD` -> `luma` -> `payloads`
1. Press (X) on `SafeB9SInstaller.firm` to delete it
1. Press (A) to confirm
1. Press (B) to return to `[0:] SDCARD`
1. Press (Y) on `boot.firm` to copy it
1. Press (B) to return to the main menu
1. Navigate to `[1:] SYSNAND CTRNAND`
1. Press (Y) to paste a copy of `boot.firm`
1. Select "Copy path(s)"
1. Press (A) to unlock SysNAND (lvl1) writing, then input the key combo given
1. Press (X) on `arm9loaderhax.bin` to delete it
  + If you do not have this file, just proceed with the instructions
1. Press (A) to confirm
1. Press (B) to return to the main menu
1. Navigate to `[0:] SDCARD`
1. Press (Y) on the `luma` folder to copy it
  + If you have files or folders *other than* the ones from following an earlier version of this guide (`config.bin` and `payloads`) in your `luma` directory (such as LayeredFS files), you should instead just copy `config.bin` and `payloads` by marking them with the (L) trigger, then pressing (Y) to copy
1. Press (B) to return to the main menu
1. Navigate to `[1:] SYSNAND CTRNAND` -> `rw`
1. Press (X) on the existing `luma` folder to delete it
  + If you do not have this folder, just proceed with the instructions
1. Press (A) to confirm
1. Press (Y) to paste a copy of the `luma` folder from your SD card
  + If you only copied `config.bin` and `payloads` earlier, you will need to instead create the `luma` folder manually (hold the (R) trigger and pressing (Y) at the same time, give the name `luma`, then press (A) to confirm), then navigate to `luma`, then press (Y) to paste `config.bin` and `payloads`
1. Press (Start) to reboot

___

Note that the `.bak` files in the `/boot9strap/` folder on your SD card are only needed in the event of a failed boot9strap install. Once you have installed successfully, you can delete the entire `boot9strap` folder.
{: .notice--info}

You can now press (L) + (Down) + (Select) while the system is booted to open the Rosalina menu integrated into Luma3DS. For a full list of Rosalina features, please see the [Luma3DS v8.0 Release](https://github.com/AuroraWright/Luma3DS/releases/tag/v8.0)
{: .notice--info}