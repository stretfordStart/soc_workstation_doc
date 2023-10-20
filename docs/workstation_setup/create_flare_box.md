---
layout: default
title: Create FlareVM Box
parent: Workstation Setup
navorder: 2
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

The steps how you can create a Windows VM and install the FlareVM tools are already well documented in the FlareVM GitHub [Repo](https://github.com/mandiant/flare-vm).
The quickest way to disable Windows Defender is to use this [script](https://github.com/jeremybeaume/tools/blob/master/disable-defender.ps1)

- ToDo: script to combine steps such as disabling defener, disable uac, set vagrant key

## Install Additional Software

- VM Guest Tools
- Vagrant Dependencies

After reaching the desired base box, the virtual machine needs to be shut down.

## Create Box

To create a box use this command:

``` bash
vagrant package --base flare --output flareVm.box
```

In this case "flare" is the name of the VM within VirtualBox and flareVM.box is the output file.
It takes about one hour to create the box.

## Upload to Vagrant Cloud

some steps.. --> move to seperate page, as it is used by Flare and REMnux
https://blog.ycshao.com/2017/09/16/how-to-upload-vagrant-box-to-vagrant-cloud/
