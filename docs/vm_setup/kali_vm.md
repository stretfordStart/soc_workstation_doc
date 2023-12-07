---
layout: default
title: Kali Linux VM
parent: VM Setup
nav_order: 2
---


# Kali Linux VMs

The Kali Linux Virtual Machine is a valuable tool for conducting basic security testing.

## Add Kali Linux

To acquire a Kali Linux VM, follow these steps:

1. Open the Terminal and navigate to the `/home/soc_user/soc_workstation/vms` directory.

2. Run the following command to download and set up the VM:

   ```bash
   vagrant up Kali
   ```

   This will initiate the provisioning process for the Kali Linux Virtual Machine.

3. Upon completion, a new Virtual Machine should be visible in VirtualBox.

picture

Please note that since the Kali VM is directly provided by the producer, there is no guarantee that the Virtual Machine will function flawlessly. It's advisable to refer to the official documentation or support channels for troubleshooting in case of any issues.
