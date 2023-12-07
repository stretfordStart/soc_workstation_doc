---
layout: default
title: Analysis VMs
parent: VM Setup
nav_order: 1
---

# Analysis VMs

This Chapter describes how to get the Virtual Machines to perform Malware Analysis.
The Setup will download and configure a Windows Based FlareVM and an Ubuntu Linux based REMnux VM.

## Requirements

Please note that the Analysis VMs are meant to be run on the SOC Workstation that can be installed as described here.
The Requirements to run the VMs on another System are:

- Vagrant 2.4.0
- VirtualBox 7.0.12
- \>200 GB free Disk Space
- \>16 GB RAM

There also might some changes in the provided Vagrant files be needed. For example the Path to the host location of the shared folder.

## Get Analysis VMs

Open Tilix and navigate to the following location: `/home/soc_user/soc_workstation/vms`.
In this folder is a `Vagrantfile` located which adds REMnux and FlareVM Virtualmachines to Virtualbox. Run `vagrant up FlareVM REMnux` to add them.

{: .highlight}
If vagrant up is run the first time, the VMs are downloaded from the Vagrant Cloud, which takes a few minutes.
Once the Download is completed and the Hash values match, the virtual machines should start in VirtualBox:

picture

## Analysis Workflow

Before using the virtual machine environment to Analyse potential Malware, please visit the [Analysis Knowhow Page](../analysis_knowhow/analysis_knowhow.md).
[TestLink](/docs/analysis_knowhow)
