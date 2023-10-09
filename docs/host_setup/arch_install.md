---
layout: default
title: Arch Installation
parent: Host Setup
nav_order: 2
---

# Arch Installation

## Preparation

### Set keyboard layout

Swiss German:
```
loadkeys de_CH-latin1
```

{: .highlight}
The symbols '-' & '\_' are located on the right side of the '0' button (+ Shift for '\_')

List available Layouts:
```
localectl list-keymaps
```

### Set up internet connection

To setup a WLAN connection run `iwctl` and connect to a network.
Run `station list` to list the available wlan interfaces:
```
		    Devices in Station Mode				
	----------------------------------------------------
	  Name 		State		    Scanning
	----------------------------------------------------
	  wlan0     disconnected	
```

Connect with a WLAN with this command: `station INTERFACE_NAME connect SSID WLAN_PASSWORD`.
Exit iwctl with `exit`.

Check if the connection works:
```
ping 8.8.8.8 -c 4
```

### Prepare archinstall

Check version:
```
archinstall -v
```

Tested version: 2.6.3, if you archinstall is older run this to update:
```
pacman -Sy archinstall
```

### Install git

```
pacman -Sy git
```

## Installation

Get configuration:
```
git clone https://github.com/stretfordStart/soc_workstation.git
```

Run archinstall with predefined configuration:
```
archinstall --config soc_workstation/user-configuration.json --creds soc_workstation/user-credentials.json
```

The following screen should appear:
![Archinstall Screen](../../assets/images/archinstall.png)

With the default config the follwing settings are set:

* English Language
* Swiss downlaod mirrors
* Swiss locales settings
* Disk configuration for a 512 GB NVME SSD
* Luks disk encryption
* Systemd-boot manager
* Active swap
* Hostname set to "soc_workstation"
* Root password set to "malware"
* User "soc_user" with password "malware" with sudo privileges
* No desktop environment and audio drivers installed
* Linux-hardenend kernel instead of default Linux kernel
* Additional packages: vim, git, virt-manager, eog, firefox, gdm, gnome-control-center, gnome-menus, gnome-settings-daemon, gnome-shell, gnome-shell-extensions, gnome-text-editor, gnome-tweaks, orca, xdg-desktop-portal-gnome, xdg-user-dirs-gtk, tilix, wget, nautilus
* Copy current network settings
* Timezone "Europe/Zurich"

Especially the disk configuration usually needs changes, for reasons of simplicity the best-effort partition layout is recommended.
Chose the disk where the operating system should be installed:
![Archinstall Disk Setup](../../assets/images/archinstall_disk.png)

Please note that you have to setup disk encryption again after chageing the disk configuration.

If you are happy with these settings you can proceed.

{: .warning}
If not manually declared otherwise, the entire disk gets wiped!

Choose "Install" to start the installation, this process can take up to 10 minutes, depending on your internet connection and hardware.
As soon as the installtion is completed, there is an option to chroot into the new system. As the post install steps are all done within the desktop environment, there is no need for this. Choose "No" and reboot the system and make sure to remove the installation media.
![Archinstall End Screen](../../assets/images/archinstall_end.png)
