---
layout: default
title: Post Installation
parent: Host Setup
nav_order: 3
---

# Post Installation

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>

---

## Logon

If you have not changed the credentials, use the following to log in:

| User | Password |
|:-----:|:-----:|
| soc_user | malware |

## Run Postinstsall Script

Open the terminal application (Tilix) and run the following command:

``` bash
sh /home/soc_user/soc_workstation/init.sh
```

The script performs the following tasks:

* Set power settings
* Set keyboard layout to de_CH
* Set dark color scheme
* Place common applications in Dock
* Set Flat-Remix Theme and Tela-circle icon theme
* Set custom background
* Set keybinding for Flameshot (screenshot tool)
* Set keybinding "Super" + "T" for opening Tilix
* Open this website in Firefox

For more details or information on adjusting these settings, check out the [Workstation Setup]({% link /docs/workstation_setup/adjust_postinstall.md %}).
[Workstation Setup](/docs/workstation_setup/adjust_postinstall.md)
[Workstation Setup](../workstation_setup/adjust_postinstall.md)
[Workstation Setup](/docs/workstation_setup/adjust_postinstall)
[Workstation Setup](../workstation_setup/adjust_postinstall)
[Workstation Setup](adjust_postinstall)

After running it the desktop should look like this:
![Desktop Overview](../../assets/images/Desktop.png)

## Known Issues

### Power Settings

The power settings from the post-install script should disable any power-saving options, but the screen may still dim after a few minutes, as visible in the GNOME settings:
![Power Settings](../../assets/images/Powersettings.png)

You can manually deactivate these settings.

### WinRM Connection Issue

When using Vagrant to provision a Windows-based Virtual Machine in a later step, WinRM is used to run commands on the guest system. With the default setup, this step may yield an error because the connection will timeout.

The reason for this timeout is that WinRM uses MD4 for hashing, which is not supported by recent OpenSSL versions. A workaround for this issue can be found [here](https://github.com/hashicorp/vagrant/issues/13076#issuecomment-1439388860).

Basically you need to modify `/etc/ssl/openssl.cnf`.

Old config:

```shell
[provider_sect]
#default = default_sect
#legacy = legacy_sect
#
#[default_sect]
#activate = 1
#
#[legacy_sect]
#activate = 1
```

New config:

```shell
[provider_sect]
default = default_sect
legacy = legacy_sect

[default_sect]
activate = 1

[legacy_sect]
activate = 1
```
