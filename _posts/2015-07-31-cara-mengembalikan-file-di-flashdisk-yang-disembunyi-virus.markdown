---
author: ucup
comments: true
date: 2015-07-31 09:03:36+00:00
layout: article
slug: cara-mengembalikan-file-di-flashdisk-yang-disembunyi-virus
title: Cara Mengembalikan File di Flashdisk yang disembunyi virus?
wordpress_id: 905
categories:
- Tips & Trik
tags:
- Virus
- Windows
---

Sebenarnya virus cara ini udah umum... cara kerjanya flashdisk kita terinfeksi virus lewat komp. Windows terus menyembunyikan file yang ada dalam flashdisk tersebut atau menggandakan, mengganti file/folder tersebut dengan bentuk shortcut atau *.exe. Kalo pake Linux mah kamu gak usah pusing dengan virus ini karena file sistem Linux yang berbeda...hohohoho :D

caranya Gampang banget

**Cara pertama**<!-- more -->

Download antivirus [smadav ](http://www.smadav.net)  terus install , scan Flashdisk kamu terus pada tab file tersembunyi akan muncul file/folder yang hidden klik unhide all untuk memunculkan file tersebut.

**Cara kedua**

Buka command prompt (Start > ketik 'cmd') masuk ke lokasi drive flashdisk kamu contoh drive **f:\ **, maka kamu ketik "**f:**" di command prompt maka lokasi akan pindah ke drive **f:\  **lalu ketik perintah


    attrib -s -h *.* /s /d




Selesai :)
