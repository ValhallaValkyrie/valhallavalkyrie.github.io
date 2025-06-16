---
layout: post
title: The True land of NAS
date: 2025-06-16
categories: nas
tags: truenas hardware nas homelab
---

## Networked Storage

The benefit of having a NAS, is that anything doesn't have to store everything.  
Instead, the "Compute" Nodes only have to worry about their local storage, while most of the bulk data can be sent to the NAS, reducing the required storage needs for the nodes, and allowing a separation of concerns.  

---

## Deciding on an OS

The options for NAS Software are many, with different levels of ease of use.

The main options are:
> [Unraid](https://unraid.net/)  
> [TrueNAS](https://www.truenas.com/truenas-community-edition/)  
> [OMV](https://www.openmediavault.org/)  
> DIY  

---

### Unraid

Brilliant OS, Amazing UI, Lots of Support and Resources Online, Allows for easy expansion of storage  
The only issue that I have is that it boots from a USB, meaning, if that USB fails, (Which it will) then your entire server will refuse to boot. Although the key restoring process isn't that difficult, it still adds an extra point of failure.

---

### TrueNAS

Enterprise-Grade Software. with a steep learning curve.  
Uses ZFS for storage, which allows for amazing protection of files and data.  
Follows the philosophy of, "Do A Single thing, and do it well".  
It can host services and VM's, using Docker and KVM.  
I want my NAS to be stupid, and only store files on the network.  
Leave the thinking to the compute nodes.  

---

### OMV

Not as userfriendly as Unraid, and not as advanced a feature-set as TrueNAS.  
Great for low-powered devices, or simple setups.  

---

### DIY

Taking a Linux Distro and installing a NFS and Samba Server.  
Allows for the most custom setup, but then you are maintaining another system.  
Who wants to find out that their network doesn't work because you've misconfigured something important on the "NAS"?  

---

### Decision

In the end, I decided on TrueNAS.  
It's got the most robust filesystem, unfortunately it doesn't allow easy expansion, but that's the price of performance.  
It boots from a drive, which removes the single point of common failure that plagues Unraid.  
Importantly, it;s free and easy to install, so if I break something, it should be easy to reinstall.

---
