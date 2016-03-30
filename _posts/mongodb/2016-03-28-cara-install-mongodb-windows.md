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
---

{% include toc.html %}

## Download

Download MongoDB di [https://www.mongodb.org/](https://www.mongodb.org/)

**Catatan :** MongoDB 32-bit dibatasi kapasitasnya maksimal sekitar 2GB. Secara umum direkomendasikan untuk menggunakan versi 64 bit. Lihat [di sini](http://blog.mongodb.org/post/137788967/32-bit-limitations?_ga=1.163862907.539163629.1459176855) untuk informasi lebih lanjut.
{: .notice-info }

## Install 

Install MongoDB seperti halnya aplikasi biasa, dan secara default akan tersimpan di `C:\Program and Files\mongodb`. Kita bisa mengubah lokasi installnya dengan memilih _custom_ pada saat instalasi. Asumsi MongoDB terinstall di  `C:\mongodb`, dan binary nya berada di folder `C:\mongodb\bin`.

## Setting PATH

Agar mongodb bisa dengan mudah kita pakai sebaiknya kita daftarkan PATH nya melalui _klik kanan My Computer > properties > Advanced system setting > Environment Variables_ tambahkan lokasi folder `C:\mongodb\bin` di _System variable_  di bagian `Path`.

## Setting Server

Asumsi MongoDB terinstall di  `C:\mongodb`.
Buka Command Prompt _Start > ketik "CMD"_.
MongoDB membutuhkan folder data untuk menyimpan database, __buatlah folder__ dengan nama dan lokasi `c:\data\db`
Jalankan daemon/service server MongoDB dengan perintah

```
C:\mongodb\bin>mongod.exe --dbpath "C:\data"
```


## Setting Client

Untuk client bisa pakai komputer yang sama dengan server atau komputer lain dengan jaringan yang sama, jalanka perintah `mongo`.

```
C:\mongodb\bin>mongo.exe
connecting to: test
>
```
Jika muncul shell mongoDB seperti di atas berarti kita sudah berhasil terhubung ke server MongoDB dan udah siap pakai mengelola database di MongoDB.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## Menambahkan Windows Service

Untuk menambahakan service Windows ikuti langkah berikut.

```
C:\mongodb\bin> mongod --config C:\mongodb\mongo.config --install
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
C:\mongodb\bin>mongod --remove
```

### Referensi

[https://docs.mongodb.org/manual/tutorial/install-mongodb-on-windows/](https://docs.mongodb.org/manual/tutorial/install-mongodb-on-windows/)
