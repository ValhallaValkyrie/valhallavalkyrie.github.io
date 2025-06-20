---
layout: post
title: Installing the Proxmox Ecosystem
date: 2025-06-16
categories: proxmox
tags: homelab proxmox installation
---

## Installing Proxmox

1. First, Get an ISO from [Proxmox](https://www.proxmox.com/en/products/proxmox-virtual-environment/overview)  
2. Burn it to a USB using [Etcher](https://etcher.balena.io/)
3. Boot from USB
4. Follow prompts, and select correct disk/s as boot devices  
5. When done installing, reboot system, and remove USB installer  
6. Connect to the systems web GUI, and run the [Proxmox VE Post Install Script](https://community-scripts.github.io/ProxmoxVE/scripts?id=post-pve-install)
7. Recommended to Answer Yes (y) to all options, unless needed
8. Reboot when script is finished
9. Make changes described in [this](https://www.reddit.com/r/Proxmox/comments/12gftf7/comment/jfkgcbp/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button) Reddit Post. These include commands like

```sh
systemctl disable --now pve-ha-lrm.service pve-ha-crm.service

```

and appending

```sh
Storage=volatile
ForwardToSyslog=no
```

to /etc/systemd/journald.conf  
This makes the system only log to RAM.  

## Installing Proxmox Backup Server

1. First, Get an ISO from [Proxmox](https://www.proxmox.com/en/products/proxmox-backup-server/overview)
2. Burn it to a USB using [Etcher](https://etcher.balena.io/)
3. Boot from USB
4. Follow prompts, and select correct disk/s as boot devices  
5. When done installing, reboot system, and remove USB installer  
6. Connect to the systems web GUI, and run the [Proxmox Backup Server Post Install Script](https://community-scripts.github.io/ProxmoxVE/scripts?id=post-pbs-install)
7. Recommended to Answer Yes (y) to all options, unless needed
8. Reboot when script is finished

___
