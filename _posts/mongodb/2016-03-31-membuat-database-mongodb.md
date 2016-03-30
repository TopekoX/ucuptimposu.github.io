---
layout: article
title: MongoDB - Membuat Database
modified:
categories: mongodb
excerpt:
tags: [database, mongodb]
comments: true
ads: true
image:
  feature:
  teaser: mongo.jpg
  thumb:
date: 2016-03-31T00:08:24+08:00
---

Untuk create/membuat database di MongoDB menggunakan perintah `use database_name`, perintah tersebut akan membuat database baru jika belum ada dan bila sudah ada database tersebut maka akan digunakan kembali.


<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## Syntax

Perintah dasar create database menggunakan perintah `use database_name` contoh kita akan membuat database dengan nama `databaseku`.

```
> use databaseku
switched to db databaseku
```

Untuk mengecek database saat ini yang digunakan, pakai perintah `db`:

```
> db
databaseku
```

Cek daftar database

```
>show dbs
local     0.078GB
```

Nama `databaseku`, database yang telah kita buat tidak terlihat, karena database kosong tidak akan ditampilkan. Untuk menampilkannya kita harus lakukan insert data terlebih dahulu agar databasenya terlihat.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>
