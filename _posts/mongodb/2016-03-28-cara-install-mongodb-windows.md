---
layout: article
title: MongoDB - Cara Install MongoDB di Windows
modified:
categories: mongodb
excerpt:
tags: [mongodb, database]
comments: true
ads: true
image:
  feature:
  teaser: mongo.jpg
  thumb:
date: 2016-03-28T20:36:26+08:00
series: "Tutorial MongoDB"
---

{% include series.html %}

{% include toc.html %}

## Download

Download MongoDB di [https://www.mongodb.org/](https://www.mongodb.org/)

**Catatan :** MongoDB 32-bit dibatasi kapasitasnya maksimal sekitar 2GB. Secara umum direkomendasikan untuk menggunakan versi 64 bit. Lihat [di sini](http://blog.mongodb.org/post/137788967/32-bit-limitations?_ga=1.163862907.539163629.1459176855) untuk informasi lebih lanjut.
{: .notice-info }

## Install

Install MongoDB seperti halnya aplikasi biasa, dan secara default akan tersimpan di `C:\Program and Files\mongodb`. Kita bisa mengubah lokasi installnya dengan memilih _custom_ pada saat instalasi. Asumsi MongoDB terinstall di  `C:\mongodb`, dan binary nya berada di folder `C:\mongodb\bin`.

## Setting MongoDB environment

MongoDB membutuhkan folder data untuk menyimpan database, __buatlah folder__ dengan nama dan lokasi `c:\data\db`

Daftarkan path folder "data" nya menggunakan `--dbpath` ke `mongod.exe` :

```
C:\mongodb\bin>mongod.exe --dbpath "C:\data"
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## Start Server MongoDB

Untuk menjalankan daemon/service MongoDB  jalankan peritah di bawah ini lewat **Command Prompt** :

```
C:\mongodb\bin\mongod.exe
```
Perintah diatas akan menjalankan server MongoDB silahkan ditunggu, dan biasanya jika muncul pop up **Security Alert dialog box**  nya Windows tinggal di allow saja.

## Connect ke MonggoDB

Untuk menghubungkan MonggoDB, buka **Command Prompt** baru lalu jalankan `mongo.exe`

```
C:\mongodb\bin>mongo.exe
connecting to: test
>
```
Jika muncul shell mongoDB seperti di atas berarti kita sudah berhasil terhubung ke server MongoDB dan udah siap pakai mengelola database di MongoDB.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


## Membuat Config File

Untuk menambahkan file konfigurasi MongoDB buat folder baru `c:\data\log` terlebih dahulu. Buat sebuah file konfigurasi dengan nama file `C:\mongodb\mongod.cfg` dan buka file tersebut kemudian masukan konfigurasi  `systemLog.path` dan `storage.dbPath`.

Isi file `mongodb.cfg`

```
systemLog:
    destination: file
    path: c:\data\log\mongod.log
storage:
    dbPath: c:\data\db
```

## Menambahkan Windows Service


Untuk menambahakan service Windows ikuti langkah dibawah ini.

Buka **Command Prompt** baru lalu jalankan perintah berikut:

```
C:\mongodb\bin\mongod.exe --config C:\mongodb\mongod.cfg --install
```

Start MongoDB Service

```
net start MongoDB
```

Stop MongoDB Service

```
net stop MongoDB
```

Hapus service MongoDB

```
C:\mongodb\bin\mongod.exe --remove
```

### Referensi

[https://docs.mongodb.org/](https://docs.mongodb.org/manual/tutorial/install-mongodb-on-windows/)
