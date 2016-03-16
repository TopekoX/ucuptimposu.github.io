---
author: ucup
comments: true
date: 2010-08-26 03:49:00+00:00
layout: article
slug: cara-install-driver-nvidia-di-linux
title: Cara Install Driver NVidia di Linux
wordpress_id: 275
categories:
- Tips & Trik
tags:
- Linux
---

Sebenarnya tutorial ini adalah bagi-bagi pengalaman, semalam saya abis install linux ternyata driver Nvidia nya gak ke detek. :( masalah lain komputer saya gak konek ke internet. Alabut langsung saja cabut ke warnet nyari Driver NVidianya. btw Tutorial ini berlaku untuk semua Distro. Pertama kunjungi situsnya [http://www.nvidia.com/Download/index.aspx?lang=en-us](http://www.nvidia.com/Download/index.aspx?lang=en-us) , Lalu pilih sesuai Tipe driver NVidia anda pada listbox yang ada, lalu ya.... langsung Download....

oke sekarang drivernya udah didownload sekarang menuju ke kompi linux anda.
Contoh nama file Drivernya NVIDIA-Linux-x86-256.44.run (sesuaikan dengan tipe driver anda)  simpan di sembarang direktori.

Kalo udah matiin service GDM nya caranya pertama login sebagai root su

root@topeko-desktop:~# /etc/init.d/gdm stop

Kalau anda pakai KDE ganti gdm dengan kdm
atau bisa juga pake

root@topeko-desktop:~# init 3

kalau sudah tinggal di install

root@topeko-desktop:~# sh NVIDIA-Linux-x86-256.44.run

lalu ikuti petunjuk yang ada....

kalau tiak nada yang error Alhamdulillah .. drivernya berhasi di install...
