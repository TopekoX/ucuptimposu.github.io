---
layout: article
title: MongoDB - Delete Document
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
date: 2016-05-08T23:29:43+08:00\
series: "Tutorial MongoDB"
---

{% include series.html %}

## Hapus 1 record

Untuk menghapus isi document menggunakan method `remove()`

Contoh :

```
db.siswa.remove({"nama" : "Kurniawan"})
```

Cek `db.siswa.find().pretty()`

```
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
{
	"_id" : ObjectId("572eebc63f5fc71c647fb4ca"),
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
}
{
	"_id" : ObjectId("572f09f23f5fc71c647fb4cb"),
	"nama" : "Ferry Gunawan",
	"alamat" : "Banda Aceh",
	"jenkel" : "pria"
}
```


## Hapus semua record

Untuk menghapus semua isi document :

```
db.siswa.remove()
```

{% include iklan-box.html %}
