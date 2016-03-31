---
layout: article
title: MongoDB - Menghapus Collection
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
date: 2016-03-31T19:57:12+08:00
---

Untuk menghapus/drop Collection menggunakan perintah `db.collectionName.drop()`

## Contoh

Cek terlebih dahulu

```
> use test
switched to db test
> show collections
collectionKu
latihanCollection
siswa
system.indexes
>
```
Contoh kita akan menghapus collection `latihanCollection`

```
> db.latihanCollection.drop()
true
```

Cek collection

```
> show collections
collectionKu
siswa
system.indexes
>
```

{% include iklan-box.html %}
