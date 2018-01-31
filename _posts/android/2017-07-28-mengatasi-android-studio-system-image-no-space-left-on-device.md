---
layout: article
title: Mengatasi Android Studio - System Image No Space Left on Device
modified:
categories: android
excerpt:
tags: [Android, Pemrograman Android, Android Studio, Java]
comments: true
ads: true
image:
  feature:
  teaser:
  thumb:
date: 2017-07-28T14:29:24+08:00
---

Jadi ketika saya menginstall Android Studio di Fedora 26 saya ada masalah ketika menginstall AVD untuk versi terbaru Android Nougat atau Android O, dengan pesan error *An error occurred while preparing SDK package Google Play Intel x86 Atom System Image: No space left on device.* Setelah saya mencari tau, ternyata kesalahannya ada pada temporary dari Android Studio untuk mendownload packagenya ada di direktori `/tmp` itu sudah penuh, maksimal 2GB, sedangkan untuk mendownload image diperlukan space yang lebih besar lagi belum lagi untuk proses uncompress nya.

**Pesan Error**

```
2017-07-28 09:31:48,438 [ 257414]   INFO - ectedPackagesStep$CustomLogger - To install: 
2017-07-28 09:31:48,438 [ 257414]   INFO - ectedPackagesStep$CustomLogger - - Google Play Intel x86 Atom System Image (system-images;android-26;google_apis_playstore;x86) 
2017-07-28 09:31:48,439 [ 257415]   INFO - ectedPackagesStep$CustomLogger -  
2017-07-28 09:31:48,447 [ 257423]   INFO - ectedPackagesStep$CustomLogger - Preparing "Install Google Play Intel x86 Atom System Image (revision: 4)". 
2017-07-28 09:31:48,466 [ 257442]   INFO - ectedPackagesStep$CustomLogger - Downloading https://dl.google.com/android/repository/sys-img/google_apis_playstore/x86-26_r04.zip 
2017-07-28 09:48:06,787 [1235763]   WARN - ectedPackagesStep$CustomLogger - An error occurred while preparing SDK package Google Play Intel x86 Atom System Image: No space left on device. 
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

### Solusi

Buat link direktori lokasi `/tmp/PackageOperation01` ke direktori lain yang diinginkan. Perhatikan nama direktori `PackageOperation01` bisa saja namanya berbeda misal `PackageOperation02` dsb, sesuai dengan nama direktori yang sudah dibuat oleh android studio di dalam `/tmp`.

Misal kita mau di linkan direktori temporary ke `~/Downloads/PackageOperation01`

```
mkdir ~/Downloads/PackageOperation01
sudo ln -s ~/Downloads/PackageOperation01 /tmp/PackageOperation01
```

Jalankan Android Studio.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

### Rerefensi

[http://www.redips.net/](http://www.redips.net/linux/android-studio-no-space-left-on-device/)


