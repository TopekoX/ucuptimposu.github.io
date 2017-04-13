---
layout: article
title: Dualboot Fedora Dan Kali Linux
modified:
categories: kali
excerpt:
tags: [kali, fedora, dualboot]
comments: true
ads: true
image:
  feature:
  teaser: kali_linux_wallpaper_by_lukazoid-d800c86.png
  thumb:
date: 2017-04-12T21:30:00-04:00
---
Saya memiliki laptop jadul Lenovo Thinkpad dengan OS Fedora 24 di dalamnya yang saya sendiri sudah merasa nyaman sekali dengannya. Kemudian muncullah keinginan ~~poligami~~ OS dengan Kali Linux dengan satu atap rumah Lenovo dan mudah-mudahan mereka akur. Di tutorial ini kita akan melakukan dualboot Fedora 24 dengan Kali Linux 2016.2 dengan skenario HDD saya berkapasitas 250 GB dengan OS Fedora yang sudah terinstall terlebih dahulu yang menggunakan resource HDD 150 GB berarti tersisa 100 Free kapasitas di HDD, yang nantinya akan kita install Kali.

Download Kali Linux [disini](https://www.kali.org/downloads/), kemudian boot ke DVD atau Flashdisk.

1.  Restart  laptop tekan F12 dan masuk ke boot menu (masing-masing komputer berbeda) pilih media installasi DVD Rom atau USB.
2.  Pada boot group kali pilih Istall.
3.  Lakukan installasi Kali Linux seperti biasa yang perlu diperhatikan pada akhir sesi instalasi **Jangan Membuat Boot Loader** karena kita akan menggunakan boot loader Fedora pilih “Continue without boot loader”.
4.  Kembali ke Fedora jalankan command untuk update GRUB menu milik fedora dan menambahkan pada GRUB entry milik Kali Linux.

```shell
sudo grub2-mkconfig -o /boot/grub2/grub.cfg
```
Restart. Seharusnya boot menu milik Kali Linux sudah muncul.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

