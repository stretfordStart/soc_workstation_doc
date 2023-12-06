---
layout: default
title: Create REMnux Box
parent: Workstation Setup
nav_order: 5
---

# Create REMnux Box

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>

---

## Install REMnux VM

You could potentially import the official OVA File as statet in the official [Documentation](https://docs.remnux.org/install-distro/get-virtual-appliance).
After importing the VM however there would still some changes need to be made, such as installing updates and custom applications.
As with FlareVM you could just use the provided files from the `/home/soc_user/soc_workstation/vms/setup` folder to automatically setup a Virtual Machine with REMnux installed. In this case run `vagrant up REMnux` which creates a VM with the following settings:

| Settings |
|:------------|
| Base Box: [generic/ubuntu2004](https://app.vagrantup.com/generic/boxes/ubuntu2004) |
| 8GB RAM |
| 2 CPU Cores |
| VMSVGA Graphics Controller |
| A shared folder with /home/soc_user/Documents/share as base |
| Default NAT network interface for NIC1 |
| Isolated network "Analyis Network" for NIC2, with IP 10.0.0.3 |
| SSH as communicator |
| remnux_provision.sh as provisioning script |

For more details inspect the [Vagrantfile](https://github.com/stretfordStart/soc_workstation/blob/ad7ce2186f62ce61a45d1bbf7dcc4a703061ae25/vms/setup/Vagrantfile)

In order to further customize the VM a Provisioning Bash Script "remnux_provision.ps1" is used.
The script completes following steps:

| Steps |
|:------------|
| Install Gnome Desktop Environment |
| Add user "remnux" with password "malware" |
| Set Keyboardlayout and Timezone |
| Install REMnux |
| Add VSCode Plugins: EML Viewer, Prettier, JavaScript, Encode Decode |

For more details inspect the actual [Script](https://github.com/stretfordStart/soc_workstation/blob/ad7ce2186f62ce61a45d1bbf7dcc4a703061ae25/vms/setup/remnux_provision.ps1)

## Upload to Vagrant Cloud

[See here](upload_box.md)

## Known Issues

- Keyboard Layout
- Guest Additions
- REMnux installations breaks --> rerun
