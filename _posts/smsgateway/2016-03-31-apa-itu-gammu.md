---
layout: article
title: SMS Gateway - Apa itu Gammu?
modified:
categories: smsgateway
excerpt:
tags: [smsgateway, gammu]
comments: true
ads: true
image:
  feature:
  teaser:
  thumb:
date: 2016-03-31T21:15:16+08:00
---

[Gammu](http://wammu.eu/gammu/) adalah sebuah project aplikasi service serta nama dari sebuah aplikasi *command line utility*, yang digunakan untuk mengontrol fungsi telepon(pada umumnya handphone dan modemn). Gammu ditulis dengan bahasa C di kembangkan menggunakan [libGammu](http://wammu.eu/libgammu/) dan tentunya free opensource. Karena fungsi tersebut Gammu menjadi salah satu tool yang dapat mengembangkan aplikasi SMS Gateway.

Gammu dapat menjalankan berbagai akses berbagai fitur telepon. Gammu mendukung banyak jenis handphone bisa di cek di [Gammu Phone Databases](http://wammu.eu/phones/).

**Perhatian :** Menurut Pengalaman Saya, tidak semua merk atau jenis HP/modemn yang ada dalam Gammu Phone Database didukung secara penuh, kadang ada fitur yang tidak bisa dijalankan.
{: .notice-warning }

## Beberapa fitur Gammu :

* Call listing, initiating and handling
* SMS retrieval, backup and sending
* MMS retrieval
* Phonebook listing, export and import (also from standard formats such as vCard)
* Calendar and tasks listing, export and import (also from standard formats such as vCalendar or iCalendar)
* Retrieval of phone and network information
* Akses ke sistem file telepon (perhatikan bahwa beberapa ponsel bekerja juga sebagai perangkat penyimpanan USB dan mereka tidak dapat diakses melalui Gammu)

Untuk keterangan selengkapnya langsung aja ke [TKP Gammu](http://wammu.eu/gammu/).

## Bahan-bahan

Berikut bahan-bahan yang di perlukan untuk membangun server SMS Gateway dengan Gammu

* Komputer dengan OS Linux atau Windows
* HP atau modemn yang di support Gammu (di tutorial web ini saya menggunakan modemn Wavecom M1306B)
* SIM Card sama pulsanya
* Database (MySQL, MariaDB, PostgreSQL atau SQLite)

{% include iklan-box.html %}
