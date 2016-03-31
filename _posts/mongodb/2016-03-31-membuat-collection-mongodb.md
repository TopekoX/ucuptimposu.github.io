---
layout: article
title: MongoDB - Membuat Collection
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
date: 2016-03-31T17:15:31+08:00
---

Untuk membuat/create Collection di MongoDB menggunakan perintah

```
db.createCollection(name, options)
```

`name` adalah nama collection dan `options` bersifat optinal adalah dokumen dan digunakan untuk mengisi/mengatur collection.

Adapun daftar field yang dapat digunakan pada `options`

| Field     |   Type    |
|---------|---------|
| capped	    | Boolean   |
| autoIndexID |	Boolean |
| size	     | number |
| max     | 	number  |


{% include iklan-box.html %}

## Contoh

Contoh kita akan menggunakan database `test`
Kita akan membuat collection tanpa option

```
> use test
switched to db test
> db
test
> db.createCollection("latihanCollection")
{ "ok" : 1 }
>
```

Cek  collection yang sudah kita buat

```
> show collections
latihanCollection
system.indexes
>
```

Sekarang kita akan membuat collection dengan option

```
> db.createCollection("collectionKu", {capped : true, autoIndexID : true, size : 1000, max : 10000})
{ "ok" : 1 }
>
```

MongoDB juga akan secara otomatis membuat collection ketika kita melakukan insert document

```
> db.siswa.insert({"nama" : "Ucup"})
WriteResult({ "nInserted" : 1 })
> show collections
collectionKu
latihanCollection
siswa
system.indexes
>
```

{% include iklan-box.html %}
