---
layout: default
title: Analysis VMs
parent: VM Setup
navorder: 1
---

# Analysis VMs

Requirements

## Get Analysis VMs

Open Tilix and navigate to the following location: `/home/soc_user/soc_workstation/vms`.
In this folder is a `Vagrantfile` located which adds REMnux and FlareVM Virtualmachines to Virtualbox. Run `vagrant up` to add them.

{: .highlight}
If vagrant up is run the first time, the VMs are downloaded from the Vagrant Cloud, which takes a few minutes.

## Prepare VMs for Analysis

To Prepare the VMs for an Analysis assignment make sure that no internet connection from either of the VMs is available.
Run this to disconnect the default NAT interface:

```bash
vboxmanage modifyvm VMNAME --nic1 none
```
