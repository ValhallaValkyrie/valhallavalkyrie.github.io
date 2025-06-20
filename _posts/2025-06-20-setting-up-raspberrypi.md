---
layout: post
title: The Little SBC that could.
date: 2025-06-20
categories: pi
tags: homelab pi raspberry setup
---

## Hardware

The SBC that I am using today is a Raspberry Pi 4 8GB Model. I used to run Raspbian OS Lite 64 bit on it, but the MicroSD card died on me a few too many times. This time, I have a 256GB SSD in an External USB enclosure.  

Let's hope this ends up going better!

___

### Installing DietPi

Installing DietPi is as easy as following the [Installation Instuctions](https://dietpi.com/docs/install/).

After flashing the drive, it's as simple as plugging it into the RPi, and connecting the power cable.

Once it has gone through it's first boot. Connect via ssh to it

Initial Credentials are:  
> login: root  
> password: dietpi  

Once you login ,DietPi will then update all it's packages for you.  

You will be asked to change the default password for the "root" and "dietpi" user accounts.  

You will be asked to change the default password for app installs.  

You will be asked whether you want to keep the UART port active. I don't need it, so I disabled it.  

By default, DietPi uses a RAMlog to reduce wear on the SD Card.  

After configuring, select install, and DietPi will finish the install process.  

A quick reboot later, and everything should be installed and ready.  

___

### Editing the Hostname

After reboot, edit the hostname file

```sh
nano /etc/hostname
```

edit the hosts file

```sh
nano /etc/hosts
```

Reboot again.

___

### Installing Tailscale

Install Tailscale with the [included](https://tailscale.com/kb/1031/install-linux) script.

Login to tailscale with

```sh
tailscale up
```

copy the URL, paste in web-browser, login to tailscale.  

___

Advertise Routes with a subnet router, this allows local access to your network via tailscale devices.  

First [enable IP Forwarding](https://tailscale.com/kb/1019/subnets#enable-ip-forwarding)

then run

```sh
sudo tailscale set --advertise-routes=192.168.3.0/24
```

In my case I am advertising the route to my local network, which is 192.168.3.0/24.

Enable the Subnet route in the [Admin Console](https://tailscale.com/kb/1019/subnets#enable-subnet-routes-from-the-admin-console).

___

## Installing Docker and Docker Compose

I'll be making use of the Dietpi Software Installer, access that using.

```sh
dietpi-software
```

Then Search Software, select Docker, and Docker Compose, and install.

After a little while, Docker and Docker Compose should be ready for use.

___

### Installing Newt and Pangolin

Install Newt using docker compose, and link to the Pangolin instance.

___

Enjoy your SBC!

___
