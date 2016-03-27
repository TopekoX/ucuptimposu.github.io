---
comments: true
date: 2015-08-02 08:33:40+00:00
layout: article
title: Setelah install Kali Linux
categories: kali
tags: [backtrack ,kali, linux]
ads: true
image:
  feature:
  teaser: kali_linux_wallpaper_by_lukazoid-d800c86.png
---

[Kali Linux ](https://www.kali.org/)adalah distro Linux yang di gunakan untuk tujuan untuk percobaan penetrasi (penetration testing) jadi fitur yang diunggulkan lebih ke fungsinya. Distro penerus [Backtack ](http://www.backtrack-linux.org/)ini bukannya kita tidak bisa menggunakan Kali Linux untuk office, multimedia dll.Hanya saja kita perlu melakukan sedikit konfigurasi.<!-- more -->

**1. Mengganti Repository resmi Kali Linux**

Edit file **/etc/apt/sources.list**, bukalah filenya.



    leafpad /etc/apt/sources.list



tambahkan kode berikut untuk Kali Linux 1.x.x



    ## Regular repositories
    deb http://http.kali.org/kali kali main non-free contrib
    deb http://security.kali.org/kali-security kali/updates main contrib non-free
    ## Source repositories
    deb-src http://http.kali.org/kali kali main non-free contrib
    deb-src http://security.kali.org/kali-security kali/updates main contrib non-free



Save.<!-- more -->

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

**2.Update, Upgrade, Dist-Upgrade**

Clean, update, upgrade and dist-upgrade



    apt-get clean && apt-get update && apt-get upgrade -y && apt-get dist-upgrade -y



**3. Perbaiki sound yang selalu mute di Kali Linux**

Ikuti langkah berikut untuk memperbaiki sound yang selalu mute di Kali Linux :



    apt-get install alsa-utils -y



Di GNOME Desktop (Desktop degault Kali Linux)





  * Klik kanan pada icon volume dan pilih Sound Preferences





  * Atau , kamu bisa juga pergi ke **Applications > System Tools > Preferences  > System Settings > Sound** .





  * Ubah **Output volume** menjadi **ON**.


<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

**4. Install Flash Player**



    apt-get install flashplugin-nonfree



dan kemudian ketikkan seperti ini:



    update-flashplugin-nonfree --install



**5. Archive Manager**

Salah satu Archive manager GUI adalah file roler :



    apt-get install unrar unace rar unrar p7zip zip unzip p7zip-full p7zip-rar file-roller -y



sekarang, archive managernya berda di  **Applications > Accessories > Archive Manager.**

**6. Install Filezilla FTP Client**



    apt-get install filezilla



** 7. Install Audacious**

Pengen pemutar musik yang simple, install aja audacious miripn tampilannya dengawinamp di windows



    apt-get install audacious
