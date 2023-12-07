---
layout: default
title: Upload Box
parent: Workstation Setup
nav_order: 5
permalink: /docs/workstation_setup/upload_box
---

# Upload Box

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>

---

## Upload Box to Vagrant Cloud

Follow these steps to upload a Vagrant Box to Vagrant Cloud.

1. Go to [Vagrant Cloud](https://app.vagrantup.com) and login
2. Click "Dashboard" and then "New Vagrant Box" button
![Add New Box](../../assets/images/new_vagrant_box.png)
3. Enter name, visibility and description and click "Create box"
![Create New Box](../../assets/images/create_vagrant_box.png)
4. Enter a version (use [RubyGems versioning](https://guides.rubygems.org/patterns/#semantic-versioning))
5. Click "Add a provider", where you will be lead to a page where you can upload your box
6. Enter the provider (=virtualbox), and choose SHA256 as the Checksum type
7. Enter the SHA256 Checksum of the .box file
8. Use the Box architecture "unknown"
9. Upload the .box File
![Add Provider](../../assets/images/new_box_provider.png)
