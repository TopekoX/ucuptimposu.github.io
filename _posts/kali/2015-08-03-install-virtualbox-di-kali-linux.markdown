---
comments: true
date: 2015-08-03 03:03:13+00:00
layout: article
title: Cara Install Virtualbox di Kali Linux (Debian), Ubuntu
categories: kali
tags: [kali, linux, virtualbox]
ads: true
image:
  feature: 
  teaser: kali_linux_wallpaper_by_lukazoid-d800c86.png
---

Install Virtual Box di Kali Linux Gampang banget:

Download Virtualbox[ disini](https://www.virtualbox.org/wiki/Downloads) contoh Virtualbox 4.3 64 bit dengan nama *virtualbox-4.3_4.3.30-101610~Debian~wheezy_amd64.deb* (sesuaikan dengan sistem kalian Kali Linux 64 bit atau 32 bit)



    root@kali:~# apt-get update
    root@kali:~# apt-get upgrade
    root@kali:~# apt-get dist-upgrade
    root@kali:~# apt-get install linux-headers-$(uname -r)
    root@kali:~# dpkg -i virtualbox-4.3_4.3.30-101610~Debian~wheezy_amd64.deb
    root@kali:~# apt-get -f install




Buka Di Menu **Application > System Tool > Oracle VM Virtualbox**

## Catatan
> Cara di atas untuk menginstall VBox di Kali atau Debian untuk Ubuntu caranya sama tapi file yang harus didownload adalah VBox untuk ubuntu
