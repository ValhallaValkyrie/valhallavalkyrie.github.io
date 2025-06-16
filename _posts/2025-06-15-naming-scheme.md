---
layout: post
title: Deciding on A Naming Scheme
date: 2025-06-15
categories: homelab
tags: planning hardware names identifiers
---

## Deciding on a Naming Scheme

Deciding on a naming scheme can be tough, because of all the different optons that there are.  
This [Website](https://namingschemes.com/Main_Page) has been a massive help on finding inspiration, even if indirectly. What I realised when searching through it, is that there's no meaning to most of it, atleast to me. That inspired me to make my own naming scheme, incorporating things that I would remember, and be attached to.

---

## The Scheme that I ended up *"creating"* is as follows

>All Physical Servers get named after an Inquistorial [Ordo](https://wh40k.lexicanum.com/wiki/Inquisition) (if a compute node) or [Chapter](https://wh40k.lexicanum.com/wiki/Chapter) (if a storage node), in Warhammer 40K, if possible linking to their intended purpose.  
If a GPU is attached or passed through the VM or Container gets a "G" prefix.  
All Virtual Machines are classified into Permanent and Testing classifications.  
Permanents are named with (Node)+(OS)+(Purpose)+VM  
Testings are named with (Node)+(OS)+(Purpose)+Testing+VM  
All Containers are classified into Categories, and sorted into Permanent and Testing.  
Permanents are named with (Node)+(Purpose)+CT  
Testings are named with (Node)+(Purpose)+Testing+CT
>
>
>## Storage Nodes - Chapters
>
> - [Lamenter](https://wh40k.lexicanum.com/wiki/Lamenters) - Proxmox Backup Server  
> - [Consecrator](https://wh40k.lexicanum.com/wiki/Consecrators) - TrueNAS Network Storage  
>
>## Compute Nodes - Ordo's
>
> - [Machinum](https://wh40k.lexicanum.com/wiki/Ordo_Machinum) - Proxmox Server
> - [Malleus](https://wh40k.lexicanum.com/wiki/Ordo_Malleus) - Gaming PC
> - [Excorium](https://wh40k.lexicanum.com/wiki/Ordo_Excorium) - Laptop  
> - [Sanctorum](https://wh40k.lexicanum.com/wiki/Ordo_Sanctorum) - RaspberryPi
> - [Scriptorum](https://wh40k.lexicanum.com/wiki/Ordo_Scriptorum) - VPS  
>
>## Virtual Machines  
>
> - G-Machinum-Win11-Gaming-VM  = Windows 11 Gaming VM with GPU Passthrough  
