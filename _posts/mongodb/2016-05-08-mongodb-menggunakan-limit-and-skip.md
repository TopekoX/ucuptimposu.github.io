---
layout: article
title: MongoDB - Menggunakan Limit & Skip
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
date: 2016-05-08T23:41:42+08:00
series : "Tutorial MongoDB"
---

{% include series.html %}

## Limit

Method `limit()` menerima argument number, yang mengembalikan jumlah document sesuai nilai number.

Contoh mengembalikan hasil 1 record

```
> db.siswa.find().pretty().limit(1)
{
	"_id" : ObjectId("572eebc63f5fc71c647fb4c8"),
	"nama" : "Issenoro",
	"alamat" : "Bandung",
	"jenkel" : "pria"
}
```

Contoh mengembalikan hasil 2 record

```
> db.siswa.find({"jenkel" : "pria"}).pretty().limit(2)
{
	"_id" : ObjectId("572eebc63f5fc71c647fb4c8"),
	"nama" : "Issenoro",
	"alamat" : "Bandung",
	"jenkel" : "pria"
}
{
	"_id" : ObjectId("572eebc63f5fc71c647fb4c9"),
	"nama" : "Mamit Marjohan",
	"alamat" : "Perumahan Asri Bekasi",
	"jenkel" : "pria"
}
```

## Skip

Method `skip()` pada dasarnya akan menerima argument number, dan akan meng-skip number document sesuai nilai parameternya

Contoh

```
> db.siswa.find({"jenkel" : "pria"}).pretty().limit(1).skip(1)
{
	"_id" : ObjectId("572eebc63f5fc71c647fb4c9"),
	"nama" : "Mamit Marjohan",
	"alamat" : "Perumahan Asri Bekasi",
	"jenkel" : "pria"
}
```

{% include iklan-box.html %}
