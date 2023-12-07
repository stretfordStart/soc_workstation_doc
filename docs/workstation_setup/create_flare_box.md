---
layout: default
title: Create FlareVM Box
parent: Workstation Setup
nav_order: 3
---

# Create FlareVM Box

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>

---

## Install Windows VM

You could potentially create a new Virtual Machine with a fresh ISO file, and create the FlareVM from Scratch, as described in the offical FlareVM GitHub [Repo](https://github.com/mandiant/flare-vm). But to speed the process up you can also use an existing Vagrant Box and add FlareVM Tools to it.
Navigate to `/home/soc_user/soc_workstation/vms/setup` there are already the needed files to create a new Base Vagrant Box, containing FlareVM.
When running `vagrant up FlareVM` a virtual machine with following settings gets created:

| Settings |
|:------------|
| Base Box: [gusztavvargadr/windows-server-2019-standard](https://app.vagrantup.com/gusztavvargadr/boxes/windows-server-2019-standard), set the Release Notes there for further information |
| 8GB RAM |
| 2 CPU Cores |
| A shared folder with /home/soc_user/Documents/share as base |
| Default NAT network interface for NIC1 |
| Isolated network "Analyis Network" for NIC2, with IP 10.0.0.4 and Gateway 10.0.0.3 |
| WinRM as communicator |
| flare_provision.ps1 as provisioning script |

For more details inspect the [Vagrantfile](https://github.com/stretfordStart/soc_workstation/blob/ad7ce2186f62ce61a45d1bbf7dcc4a703061ae25/vms/setup/Vagrantfile)

In order to further customize the VM a Provisioning PowerShell Script "flare_provision.ps1" is used.
The script completes following steps:

| Steps |
|:------------|
| Disable the need for pressing CTRL+ALT+DELETE on Logonscreen |
| Disable Password Complexity Checks |
| Add User flare with Password malware |
| Set Keyboardlayout and Timezone |
| Turn off Auto Proxy Settings |
| Install Firefox, 7Zip, Thunderbird and LibreOffice |
| Download FlareVM Install Script |

For more details inspect the actual [Script](https://github.com/stretfordStart/soc_workstation/blob/ad7ce2186f62ce61a45d1bbf7dcc4a703061ae25/vms/setup/flare_provision.ps1)

### Install Additional Software

The Provisioningscript is not flawless and some things still need to be configured manually.

### Flare Installation

The installation of the FlareVM Tools require several restarts which is why it is not done with the Provisioning Script.
But the necessary Script is downloaded and once the Provisioning is completed you can install it manually.
For the installation open PowerShell with elevated Priviledges and run the following Command:

```powershell
C:\Users\Vagrant\install.ps1 -password malware -noWait -noGui -noChecks -customConfig https://raw.githubusercontent.com/stretfordStart/soc_workstation/main/vms/setup/config.xml
```

After reaching the desired base box, the virtual machine needs to be shut down.

## Create Box

To create a Vagrant Box use this command:

``` bash
vagrant package --base flare --output flareVm.box
```

In this case "flare" is the name of the VM within VirtualBox and flareVM.box is the output file.
It takes about one hour to create the box.

## Upload to Vagrant Cloud

[See here](upload_box)

## Known Issues

### Keyboard Layout

The Keyboard Layout set in the Provisioning Script is not active.

Workaround: Manually select prefered Layout in Gnome Settings.

### Guest Additions

Usually the Guest Additions should be installed, if you are using the Vagrant Plugin vagrant-vbguest, as in this Case.
However after setting up the VM with Vagrant, some of the VB-Guest functionalities do not work.

Workaround: Download the VB-Guest ISO matching your VirtualBox Version here: <https://download.virtualbox.org/virtualbox/>
Share the ISO with the Sharedfolder or Attach it as a Disk to the VM.

### Deactivate CTRL+ALT+DELETE for Logon fails

The part of the Provisioning Script where the need for CTRL+ALT+DELETE on Logon get deactivated fails.

Workaround: Manually deactivate it:

- Open `secpol.msc`
- Navigate to Security Settings -> Local Policies -> Security Options
- Locate the policy named "Interactive logon: Do not require CTRL+ALT+DEL" in the list
- Select the "Enabled" option and click Apply, then click OK
