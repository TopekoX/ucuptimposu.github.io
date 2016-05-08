---
layout: article
title: MongoDB - Update Document
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
date: 2016-05-07T23:33:00+08:00
series: "Tutorial MongoDB"
---

{% include series.html %}

MongoDB dapat menggunakan perintah `update()` dan `save()` untuk memperbarui document.

**Info** : Pastikan pada struktur pada collection `capped` bernilai **false** agar collection bisa di update.
{: .notice-info}

# Update

Metode `update()` digunakan untuk memperbarui data yang ada di dalam document. Metode `update()` ini dibantu syntax `$set`.

Bentuk format syntax:

```
db.collection.update(
   <query>,
   <update>,
   {
     upsert: <boolean>,
     multi: <boolean>,
     writeConcern: <document>
   }
)
```

Contoh kita akan mengganti nama Ade Sukarno yang ada dalam collection menjadi Mamit Marjohan.

```
db.siswa.update(
  { "nama" : "Ade Sukarno" },
  {
      $set: {
          "nama" : "Mamit Marjohan"
          }
  }
)
```

Perintah di atas mengubah nama Ade Sukarno menjadi Mamit Marjohan, jika di SQL peritah tersebut kurang lebih seperti ini `UPDATE siswa SET nama = "Mamit Marjohan" WHERE nama="Ade Sukarno"`.

Lihat data yang sudah di ubah dengan `db.siswa.find().pretty()`.

```
{
	"_id" : ObjectId("572eebc63f5fc71c647fb4c7"),
	"nama" : "Kurniawan",
	"alamat" : "Jl. Maju Mundur",
	"jenkel" : "laki-laki"
}
{
	"_id" : ObjectId("572eebc63f5fc71c647fb4c8"),
	"nama" : "Danu Wirnoyo",
	"alamat" : "Ciracas, Jakarta",
	"jenkel" : "laki-laki"
}
{
	"_id" : ObjectId("572eebc63f5fc71c647fb4c9"),
	"nama" : "Mamit Marjohan",
	"alamat" : "Perumahan Asri Bekasi",
	"jenkel" : "laki-laki"
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
```
Secara default `update()` hanya akan mengupdate satu/single document. Untuk update multi document tambahkan parameter `multi` yang bernilai `true`.

Contoh :

```
db.siswa.update(
  { "jenkel" : "laki-laki" },
  { $set:
    { "jenkel" : "pria" }
  },
  { multi : true }
)
```


# Save

Metode `save()` digunakan untuk menggantikan nilai yang ada di dalam document

Contoh syntax :

```
db.collection.save(
   <document>,
   {
     writeConcern: <document>
   }
)
```

Contoh :

```
db.siswa.save(
  { "_id" : ObjectId("572eebc63f5fc71c647fb4c8"),  
  "nama": "Issenoro" ,
  "alamat" : "Bandung" ,
  "jenkel" : "pria"
  }
)
```

lihat isi collection:

```
{
	"_id" : ObjectId("572eebc63f5fc71c647fb4c7"),
	"nama" : "Kurniawan",
	"alamat" : "Jl. Maju Mundur",
	"jenkel" : "pria"
}
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
```

`save()` juga dapat menyimpan document baru selain menggunakan `insert()`, contoh :

```
db.siswa.save(
  {  "nama" : "Ferry Gunawan" ,
    "alamat" : "Banda Aceh",
    "jenkel" : "pria"
  }  
)
```

Penjelasan tentang `save()` bisa di explore lagi di [sini](https://docs.mongodb.com/manual/reference/method/db.collection.save/)

## Referensi

[docs.mongodb.com](https://docs.mongodb.com/manual/reference/method/db.collection.update/)
