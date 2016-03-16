---
author: ucup
comments: true
date: 2015-08-03 05:04:43+00:00
layout: article
slug: cara-install-google-chrome-di-kali-linux-agustus-2015
title: Cara Install Google Chrome di Kali Linux (Agustus 2015)
wordpress_id: 936
categories:
- Kali Linux
tags:
- Chrome
- Google
- Internet
- Kali
- Kali Linux
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




