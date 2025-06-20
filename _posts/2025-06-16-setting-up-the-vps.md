---
layout: post
title: Setting up Remote Monitoring on a VPS using  Pangolin and Newt (With added tailscale)
date: 2025-06-16
categories: network monitoring
tags: homelab network monitoring pangolin newt proxy
---

## Getting a VPS

I use [Hetzner Cloud](https://www.hetzner.com/cloud/) for my VPS's:

1. They're high quality
2. They have generous bandwith
3. Easy to use firewall system
4. Not too expensive
5. With lots of different plan choices, or even a dedicated machine if performance is needed

## VPS Setup

I prefer to use Debian for my VPS, because:

1. It's always supported
2. It's stable
3. It's decently lightweight
4. Doesn't try to do anything fancy
5. I know it

---

It might not be everyones first choice, but for something that you just want to turn on and work, it's perfect for my uses.  

## After getting the VPS installed

ssh in to the provided IP address

```sh
ssh username@ip-address
```

If you prefer a GUI, I would recommend [Putty](https://www.putty.org/), [Termius](https://termius.com/) or [Tabby](https://github.com/Eugeny/tabby).

Change default password

```sh
passwd
```

follow prompts

Then run

```sh
apt update && apt upgrade
```

```sh
reboot
```

ssh into the provided IP address again

Change hostname

```sh
nano /etc/hostname
```

Replace old hostname with new hostname, save, and exit

```sh
nano /etc/hosts
```

Replace old hostname with new hostname, save, and exit

Install docker using the provided [tutorial](https://docs.docker.com/engine/install/debian/#install-using-the-repository)  

Install [Pangolin](https://docs.fossorial.io/Getting%20Started/overview) using the provided [tutorial](https://docs.fossorial.io/Getting%20Started/quick-install)  
I prefer to do it in a dedicated 'docker-compose' directory.  
Create required directories  
The -p creates the entire path

```sh
mkdir -p docker-compose/pangolin
```

install [tailscale](https://tailscale.com/) with [instructions](https://tailscale.com/kb/1031/install-linux#debian)

run in terminal

```sh
tailscale up
```

Login to the tailscale network

I normally do a reboot at this point, just to make sure everything is loaded properly.  

Login to the Pangolin Domain that you specified earlier in the tutorial

Create an Admin Account, New site, and Configure Resources.  

I use the VPS as my external monitoring server, so I have a [Newt](https://docs.fossorial.io/Newt/install) instance running locally, that it creates a tunnel to.  

And Voila, a password protected external proxy, that can talk you all your internal devices, without doing any port forwarding.  

---
