---
title: Home
layout: default
nav_order: 1
---

# SOC Workstation Documentation

This site contains the documentation for the GitHub project [SOC Workstation](https://github.com/stretfordStart/soc_workstation). The primary focus of the project is to automate the process of setting up a secure system for analyzing malware.

In summary, the Workstation uses Linux Arch as the host system and deploys multiple VMs for malware analysis and other SOC tasks.

The Workstation is designed to operate within a dedicated Analysis Network to ensure security. The virtual machines used for analysis purposes should be configured with an internal network to prevent potential malware from accessing the internet. To monitor network calls while maintaining a secure environment, InetSim is utilized on REMnux.

After running the installation process described here, the setup should resemble the following:

![Setup Overview](assets/images/setup_overview.png){:width=70% height=70%}
