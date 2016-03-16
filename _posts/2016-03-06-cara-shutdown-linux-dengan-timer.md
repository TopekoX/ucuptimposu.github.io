---
layout: article
title: "Cara Shutdown Linux dengan Timer"
date: 2016-03-06 03:31:36 +0800
comments: true
categories: [Linux, Tips & Trik]
tags: [Linux, Tips]
ads: true
image:
  feature: 
  teaser: 
---

Ada banyak perintah untuk mematikan komputer linux, bisa `poweroff`, `halt`, `shutdown`. Untuk mematikan komputer linux dengan timer tertentu tinggal menambahkan waktu menit dibelakan perintah tersebut, format `shutdown +time`.

### Shutdown komputer dengan timer 5 menit

	shutdown +5

### Shutdown komputer dengan timer 10 menit ditambah pesan

	shutdown +10 "Bro komputernya mau mati 10 menit lagi"

output :

	Broadcast message from root@timposu (pts/0) (Sun Mar 6 03:40:30 2016): Bro komputernya mau mati 10 menit lagi


### Cara membatalkan

Kalau udah terlanjur dishutdown dengan timer maka kita juga bisa membatalkan kannya dengan perintah
	
	shutdown -c

> Catatan : harus dengan akses root
