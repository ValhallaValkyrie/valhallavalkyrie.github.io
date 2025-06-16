---
layout: post
title: Networking in the Land of Proxmox
date: 2025-06-16
categories: homelab
tags: proxmox hardware planning
---

---

## A mish-mash of software

Currently, my setup runs on different Operating Systems, spread out between devices, with different packaging methods, commands and supported features.  
Unfortunately it becomes a pain to remember where you did what, and try to recreate it everytime you change hosts.  
Moving to a "Universal" Standard, allows standardisation and familiarity.  

**My network looks a bit like this.**  

---

> 1. DietPi on the RaspberryPi  
> 2. Windows 11 the Gaming PC
> 3. unRAID on the Main "Server"  
> 4. TrueNAS on the 2nd "Server"
> 5. TrueNAS on the 3rd "Server"
> 6. Windows 11 on the Laptop
> 7. Debian on the VPS  

---

As you can see, there is no ecosystem, let alone **any** system, for any of it.  
Today **that** changes.  
After much research, and watching of YouTube Tutorials, I have decided to redo ***almost***  my entire setup, from the ground up, so to speak.  

---

## All New Hardware must follow the naming scheme outlined in a [previous post]({% post_url 2025-06-15-naming-scheme %})

### Compute Nodes

> - (Machinum) will run [Proxmox](https://www.proxmox.com/en/)  
> - (Malleus) will run Windows 11 (For Now)  
> - (Sanctorum) will run [DietPi](https://dietpi.com/) - Unchanged (For Now)  
> - (Excorium) will run Windows 11 - Unchanged
> - (Scriptorum) will run [Debian](https://www.debian.org/download) - Unchanged  

### Storage Nodes

> - (Lamenter) - [Proxmox Backup Server](https://www.proxmox.com/en/products/proxmox-backup-server/overview)  
> - (Consecrator) - [TrueNAS](https://www.truenas.com/) Network Storage  

## Goal?

The Main Goal was to reduce the footprint of the "Single Point Of Failure" and make everything as expandable and resilient as possible.  
All "Bulk" Storage, will be stored on the Network Attached Storage via NFS.  
All Containers and VM's will be backed up regularly to the Proxmox Backup Server, allowing for quick restores incase of failure, misconfiguration  or PEBKAC.  
