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

Create an installation medium with your prefered Tool such as [Rufus](https://rufus.ie/) or [balenaEtcher](https://etcher.balena.io/).

## Disable Secureboot

Navigate to your workstations BIOS / UEFI settings and disable Secure Boot.

## Enable VT-x

Later on virtualization will be needed, so make sure to enable it now, as this also needs to be adjusted within the BIOS / UEFI settings.
Now you should be ready to start the Linux Arch installation by booting from the previously created installation medium.
