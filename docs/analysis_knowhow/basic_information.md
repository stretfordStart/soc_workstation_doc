---
layout: default
title: Basic Information
parent: Analysis Knowhow
nav_order: 1
---

# Malware Analysis Best Practices

## Danger Warning

When handling dangerous files during malware analysis, it is crucial to understand the risks involved. Always use isolated environments and follow established security protocols. Ensure that you have the necessary expertise, and take appropriate precautions to prevent unintended consequences.

## Ensure there is no Internet Connection

To enhance security, ensure that your virtual machine has no internet connection. You can achieve this by running the following command:

```bash
VBoxManage modifyvm YourVMName --nic1 none
```

Verify the absence of internet connectivity by attempting to ping external addresses, such as 8.8.8.8, from within the virtual machine. Additionally, check if you could ping the host machine to confirm the isolation.

## Sharing Files with the Workstation

When sharing files with the workstation, consider the following options:

- USB Sticks: Use USB sticks to transfer files between the analysis environment and the workstation. Ensure that the USB stick is free from any sensitive information and malware.

- File-sharing Services: While using file-sharing services, exercise caution not to upload actual malware. If needed, use encrypted zip files for additional security.

## Sharing Files with the VM

Utilize VirtualBox's Shared Folder feature to conveniently share files between the host and virtual machines.
With the provided VMs it should be configured that the folder `/home/soc_user/Documents/share` is shared across all machines:
picture...

## Reporting

Document your findings and analysis results thoroughly to support incident response efforts. A comprehensive report should include:

- Summary: Provide a concise summary of the malware's behavior and characteristics.
- Artifacts: Include any artifacts or indicators of compromise (IoCs) discovered during the analysis.
- Mitigations: Suggest potential mitigations or actions to address the identified security risks.

## Cleanup

It is advisable not to reuse analysis virtual machines. After completing the analysis, perform thorough cleanup procedures to eliminate any traces of the malware and ensure a clean environment for future analyses.

Consider the following cleanup steps:

- Snapshot Revert: If you used virtual machine snapshots, revert to a clean snapshot taken before the analysis.
- File Removal: Remove any files and artifacts related to the malware analysis from the virtual machine.
- Logs and Reports: Delete or securely archive logs and reports generated during the analysis to maintain confidentiality.
- Recreate VMs or entire Workstation

Always prioritize security and compliance when handling malware-related data and ensure that your analysis environment follows industry best practices.
