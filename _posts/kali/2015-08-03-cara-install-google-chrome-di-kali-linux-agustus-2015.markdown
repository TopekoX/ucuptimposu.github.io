---
comments: true
date: 2015-08-03 05:04:43+00:00
layout: article
title: Cara Install Google Chrome di Kali Linux (Agustus 2015)
categories: kali
tags: [kali, linux]
ads: true
image:
  feature: 
  teaser: kali_linux_wallpaper_by_lukazoid-d800c86.png
---

Untuk versi terbaru google chrome ada beberapa perubahan ketika menyeting user google crome, seperti di ketahui secara default user root tidak bisa membuka google chrome.

Setelah [mendownload google chrome stable](https://www.google.com/chrome/browser/desktop/index.html).. install dengan perintah


    
    dpkg -i google-chrome-stable_current_amd64.deb



setelah itu kita tambahkan user chrome


    
    useradd -m chrome



install paket pendukung


    
    apt-get -f install



untuk menjalankan google chrome ketik perintah<!-- more -->


    
    gksu -u chrome google-chrome



tadda google chrome pun berhasil terinstal kita tinggal mengubah di main menu(Aplications > Accessories  > Main menu) untuk memasang di menu kali.
Biar lebih jelas tonton videonya





## Update



Jika kita menggunakan user root dengan cara di atas maka sound output tidak bisa keluar, nah ini cara kedua untuk mengatasi hal tersebut




    
  * tambahkan baris dibawah ini di file ` google-chrome ` contoh lokasi di ` /opt/google/chrome/google-chrome ` buka dengan editor kesayangan anda lalu tambahkan baris dibawah ini lalu simpan filenya.

    
    --user-data-dir $HOME




    
  * Setelah disimpan ... buka chrome dengan perintah

    
    google-chrome %U --no-sandbox


Lihat Video dibawah ini




