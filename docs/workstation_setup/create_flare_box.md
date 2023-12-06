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

Table...

For more details inspect the [Vagrantfile](https://github.com/stretfordStart/soc_workstation/blob/ad7ce2186f62ce61a45d1bbf7dcc4a703061ae25/vms/setup/Vagrantfile)

In order to further customize the VM a Provisioning PowerShell Script "flare_provision.ps1" is used.
The script completes following steps:

steps...

For more details inspect the actual [Script](https://github.com/stretfordStart/soc_workstation/blob/ad7ce2186f62ce61a45d1bbf7dcc4a703061ae25/vms/setup/flare_provision.ps1)

### Install Additional Software

The Provisioningscript is not flawless and some things still need to be configured manually:

- VM Guest Tools
  - https://download.virtualbox.org/virtualbox/
  - Mount ISO or share via shared folder
- Flare Installation
  - copy from github + own config...

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

- Keyboard Layout --> set manually
- CTRL ALT Delete fails --> set manually
