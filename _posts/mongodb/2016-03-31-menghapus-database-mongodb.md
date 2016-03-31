---
layout: article
title: MongoDB - Menghapus Database
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
date: 2016-03-31T00:47:19+08:00
---

Artikel ini sambungan dari [Membuat Database di MongoDB](/membuat-database-mongodb/).

Untuk menghapus database dalam MongoDB gunakan perintah `db.dropDatabase()`.

## Contoh

Lihat database terlebih dahulu.

```
show dbs
databaseku  0.078GB
local       0.078GB
```
Untuk menghapus `databaseku` gunakan perintah dibawah ini

```
> use databaseku
switched to db databaseku
> db.dropDatabase()
{ "dropped" : "databaseku", "ok" : 1 }
```

{% include iklan-box.html %}
