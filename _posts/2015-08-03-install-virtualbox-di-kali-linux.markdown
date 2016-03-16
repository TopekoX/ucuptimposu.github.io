---
author: ucup
comments: true
date: 2015-08-03 03:03:13+00:00
layout: article
slug: install-virtualbox-di-kali-linux
title: Install Virtualbox di Kali Linux
wordpress_id: 932
categories:
- Kali Linux
tags:
- Kali Linux
- Linux
- Virtualbox
---

Install Virtual Box di Kali Linux Gampang banget:

Download Virtualbox[ disini](https://www.virtualbox.org/wiki/Downloads) contoh Virtualbox 4.3 64 bit dengan nama _virtualbox-4.3_4.3.30-101610~Debian~wheezy_amd64.deb
_(sesuaikan dengan sistem kamu Kali Linux 64 bit atau 32 bit)



    root@kali:~# apt-get update
    root@kali:~# apt-get upgrade
    root@kali:~# apt-get dist-upgrade
    root@kali:~# apt-get install linux-headers-$(uname -r)
    root@kali:~# dpkg -i virtualbox-4.3_4.3.30-101610~Debian~wheezy_amd64.deb
    root@kali:~# apt-get -f install




Buka Di Menu_ Application > System Tool > Oracle VM Virtualbox_
