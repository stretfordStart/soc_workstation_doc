---
layout: default
title: Pre Installation
nav_order: 1
parent: Host Setup
---

# Pre Installation Steps

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>

---

## Download Arch

Download the current version of Arch Linux [here](https://archlinux.org/download/).

## Create Install Media

Generate an installation medium using your preferred tool, such as [Rufus](https://rufus.ie/) or [balenaEtcher](https://etcher.balena.io/).

## Disable Secure Boot

Access your workstation's BIOS/UEFI settings and disable Secure Boot.

## Enable VT-x

Ensure that virtualization is enabled, as it will be required later. Adjust the VT-x setting within the BIOS/UEFI settings. This step is crucial for virtualization to function properly.

You are now prepared to initiate the Arch Linux installation by booting from the previously created installation medium.
