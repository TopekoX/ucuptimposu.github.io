---
layout: article
title: MongoDB - Mengurutkan/Sort Document MongoDB
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
date: 2016-05-09T00:08:55+08:00
series : "Tutorial MongoDB"
---

{% include series.html %}

Mengurutkan data document yang akan ditampikan di MongoDB menggunakan method `short()`. Method `sort()`akan mengurutkan list di dalam document. `sort()`mempunyai nilai yang akan menjadi key untuk shorting order yaitu 1 untuk ascending dan -1 untuk descending.

Syntax :

```
db.COLLECTION_NAME.find().sort({KEY:1})
```

Contoh mengurutkan document berdasarkan nama secara terbalik / descending

```
db.siswa.find().sort({"nama": -1})
```

hasil

```
{ "_id" : ObjectId("572eebc63f5fc71c647fb4ca"), "nama" : "Nanin", "alamat" : "Ciracas, Jakarta", "jenkel" : "Perempuan", "pendidikan" : [ { "tingkat_pendidikan" : "Stata 1", "gelar" : "Sarjana Hukum", "tempat_pendidikan" : "Universitas Abal-Abal" } ] }
{ "_id" : ObjectId("572eebc63f5fc71c647fb4c9"), "nama" : "Mamit Marjohan", "alamat" : "Perumahan Asri Bekasi", "jenkel" : "pria" }
{ "_id" : ObjectId("572eebc63f5fc71c647fb4c8"), "nama" : "Issenoro", "alamat" : "Bandung", "jenkel" : "pria" }
{ "_id" : ObjectId("572f09f23f5fc71c647fb4cb"), "nama" : "Ferry Gunawan", "alamat" : "Banda Aceh", "jenkel" : "pria" }
```

{% include iklan-box.html %}

### Referensi

* [https://docs.mongodb.com/](https://docs.mongodb.com/manual/reference/method/cursor.sort/)
