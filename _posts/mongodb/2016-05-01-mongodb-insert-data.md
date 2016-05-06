---
layout: article
title: MongoDB - Insert Data
modified:
categories: mongodb
excerpt:
tags: [mongodb , database]
comments: true
ads: true
image:
  feature:
  teaser:
  thumb:
date: 2016-05-01T21:51:42+08:00
---
Ditutorial ini kita akan memasukan nilai/data kedalam document. Buat database dulu contoh database `sekolah`

```
> use sekolah
switched to db sekolah
```

Kita akan membuat sekaligus memasukan data ke collection `sekolah` menggunakan perintah `insert()`

```
> db.sekolah.insert({
   "nama" : "Ucup Timposu",
   "alamat" : "Jl. Jones" ,
   "jenkel" : "laki-laki"  
   })
```

Pada contoh perintah di atas kita telah berhasil
