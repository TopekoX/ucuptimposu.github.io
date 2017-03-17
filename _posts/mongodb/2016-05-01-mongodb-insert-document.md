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
  teaser: mongo.jpg
  thumb:
date: 2016-05-01T21:51:42+08:00
series: "Tutorial MongoDB"
---

{% include series.html %}

Ditutorial ini kita akan memasukan nilai/data kedalam document. [Buat database](http://localhost:4000/membuat-database-mongodb/) terlebih dulu, contoh nama database `sekolah`

Kita akan membuat sekaligus memasukan data ke collection `sekolah` menggunakan perintah `insert()` dengan nama collection 'siswa'.

```
> db.siswa.insert({
   "nama" : "Ucup Timposu",
   "alamat" : "Jl. Jones" ,
   "jenkel" : "laki-laki"  
   })
```

Pada contoh perintah di atas kita telah berhasil memasukan data ke dalam collection `siswa` yang ada di dalam database `sekolah`.
<!--  -->
Kita juga bisa memasukan data lebih dari 1 sekaligus.

```
> db.siswa.insert([
 {
   "nama" : "Kurniawan",
   "alamat" : "Jl. Maju Mundur",
   "jenkel" : "laki-laki"
 } ,
 {
   "nama" : "Danu Wirnoyo",
   "alamat" : "Ciracas, Jakarta",
   "jenkel" : "laki-laki"  
 },
 {
   "nama" : "Ade Sukarno",
   "alamat" : "Perumahan Asri Bekasi",
   "jenkel" : "laki-laki"
 },
 {
   "nama" : "Nanin",
   "alamat" : "Ciracas, Jakarta",
   "jenkel" : "Perempuan",
   "pendidikan" : [
                   {
                     "tingkat_pendidikan" : "Stata 1",
                     "gelar" : "Sarjana Hukum",
                     "tempat_pendidikan" : "Universitas Abal-Abal"
                   }
                 ]
  }])
```

{% include iklan-box.html %}
