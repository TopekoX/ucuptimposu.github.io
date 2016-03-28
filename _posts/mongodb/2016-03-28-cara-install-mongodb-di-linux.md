---
layout: article
title: MongoDB - Cara Install MongoDB Di Linux
modified:
categories: mongodb
excerpt:
tags: []
comments: true
image:
  feature:
  teaser:
  thumb:
date: 2016-03-28T23:44:40+08:00
---

Pada tutorial kali ini kita akan belajar menginstall MongoDB di Linux.

{% include toc.html %}

Download MongoDB di [https://www.mongodb.org/](https://www.mongodb.org/)

**Catatan :** MongoDB 32-bit dibatasi kapasitasnya maksimal sekitar 2GB. Secara umum direkomendasikan untuk menggunakan versi 64 bit. Lihat [di sini](http://blog.mongodb.org/post/137788967/32-bit-limitations?_ga=1.163862907.539163629.1459176855) untuk informasi lebih lanjut.
{: .notice-info }

## Install

STEP 1 Download

```
curl -O https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-3.2.4.tgz
```

STEP 2 Extract

```
tar -zxvf mongodb-linux-x86_64-3.2.4.tgz
```

STEP 3 Pindahkan dan rename direktori ke folder `/opt` misalnya.

```
mv mongodb-linux-x86_64-3.2.4 /opt/mongodb
```

STEP 4 Binary MongoDB ada di direktori MongoDB `bin/`. Tambahkan lokasi folder tersebut ke `PATH`
       Tambahkan skrip dibawah ke dalam file `rc`di direktori home  ( `~/.bashrc` )

```
export PATH=<mongodb-install-directory>/bin:$PATH
```



<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## Setting Server

STEP 1: MongoDB membutuhkan direktori data untuk menyimpan database, buatlah direktori dengan nama dan lokasi `/data/db`

```
mkdir -p /data/db
```

STEP 2: Setting permission direktori mongoDB atau direktori data yang telah kita buat


STEP 3: Jalankan daemon/service server MongoDB dengan perintah

```
mongod
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## Setting Client

Untuk client bisa pakai komputer yang sama dengan server atau komputer lain dengan jaringan yang sama, jalankan peritah `mongo`.

```
mongo
connecting to: test
>
```
Jika muncul shell mongoDB seperti di atas berarti kita sudah berhasil terhubung ke server MongoDB dan udah siap pakai mengelola database di MongoDB.

### Referensi

[https://docs.mongodb.org/manual/tutorial/install-mongodb-on-linux/#install-mongodb-community-edition](https://docs.mongodb.org/manual/tutorial/install-mongodb-on-linux/#install-mongodb-community-edition)
