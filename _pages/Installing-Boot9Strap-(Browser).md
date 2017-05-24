---
title: "Installing boot9strap (Browser)" #
lang: en
permalink: /installing-boot9strap-(browser).html
---

To use the [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme) links on this page, you will need a torrent client like [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--info}

#### What you need

* The latest release of [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* The latest release of [boot9strap](https://github.com/SciresM/boot9strap/releases/latest)

#### Instructions

##### Section I - Prep Work

1. Power off your device
1. Insert your SD card into your computer
1. Create a folder named `boot9strap` on the root of your SD card
1. Copy `boot9strap_dev.firm` and `boot9strap_dev.firm.sha` from the boot9strap `.zip` to the `/boot9strap/` folder on your SD card
1. Copy `SafeB9SInstaller.dat` from the SafeB9SInstaller `.zip` to the root of your SD card
1. Reinsert your SD card into your device
1. Power on your device

##### Section II - Launching SafeB9SInstaller

1. Launch the browser and go to one of the following URL on your device
  + `https://dukesrg.github.io/?SafeB9SInstaller.dat`
  + If you get an error, [follow this troubleshooting guide](troubleshooting#ts_browser)
1. If the exploit was successful, you will have booted into SafeB9SInstaller

##### Section III - Installing boot9strap

1. Wait for all safety checks to complete
1. When prompted, input the key combo given to install boot9strap
1. Once it has completed, press (A) to reboot your device
1. Your device will boot into boot9strap, then shutdown automatically because it does not yet have a payload to launch

___

Continue to [Finalizing Setup](finalizing-setup)
{: .notice--primary}
