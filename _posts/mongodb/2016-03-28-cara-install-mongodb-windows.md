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

Pada tutorial kali ini kita akan belajar menginstall MongoDB di Windows.

{% include toc.html %}

## Download

Download MongoDB di [https://www.mongodb.org/](https://www.mongodb.org/)

**Catatan :** MongoDB 32-bit dibatasi kapasitasnya maksimal sekitar 2GB. Secara umum direkomendasikan untuk menggunakan versi 64 bit. Lihat [di sini](http://blog.mongodb.org/post/137788967/32-bit-limitations?_ga=1.163862907.539163629.1459176855) untuk informasi lebih lanjut.
{: .notice-info }

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## Setting Server

Asumsi MongoDB terinstall di  `C:\mongodb`.

* Buka Command Prompt _Start > ketik "CMD"
* MongoDB membutuhkan folder data untuk menyimpan database, __buatlah folder__ dengan nama dan lokasi `c:\data\db`
* Jalankan daemon/service server MongoDB dengan perintah

    ```
      C:\mongodb\bin\mongod.exe
    ```
* Tambahkan PATH MongoDB

    ```
    C:\mongodb\bin>mongod.exe --dbpath "C:\mongodb\data"
    ```

## Setting Client

Untuk client bisa pakai komputer yang sama dengan server atau komputer lain dengan jaringan yang sama, jalanka perintah `mongo`.

```
D:\mongodb\bin>mongo.exe
connecting to: test
>
```
Jika muncul shell mongoDB seperti di atas berarti kita sudah berhasil terhubung ke server MongoDB dan udah siap pakai mengelola database di MongoDB.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## Menambahkan Windows Service

Untuk menambahakan service Windows ikuti langkah berikut.

```
d:\mongodb\bin> mongod --config D:\mongodb\mongo.config --install
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
d:\mongodb\bin>mongod --remove
```

### Referensi

[https://docs.mongodb.org/manual/tutorial/install-mongodb-on-windows/](https://docs.mongodb.org/manual/tutorial/install-mongodb-on-windows/)
