---
layout: article
title: MongoDB - Query di MongoDB
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
date: 2016-05-07T18:29:30+08:00
series: "Tutorial MongoDB"
---

{% include series.html %}

Query dalam MongoDB seperti dalam SQL di RDBMS memiliki banyak variasi kita akan membahasnya di artikel ini secara bertahap.

{% include toc.html %}

## Find

Untuk menampilkan data dari collection MongoDB, kita menggunakan perintah dari method `find()`

Format :

```
db.NAMA_COLLECTION.find();
```

Contoh :

```
db.siswa.find();
```

Hasil :

```
{ "_id" : ObjectId("572dbe4c7bed90127e18394e"), "nama" : "Ucup Timposu", "alamat" : "jln. Jones", "jenkel" : "laki-laki" }
{ "_id" : ObjectId("572dc20b7bed90127e18394f"), "nama" : "Kurniawan", "alamat" : "Jl. Maju Mundur", "jenkel" : "laki-laki" }
{ "_id" : ObjectId("572df94f7bed90127e183952"), "nama" : "Danu Wirnoyo", "alamat" : "Ciracas, Jakarta", "jenkel" : "laki-laki" }
{ "_id" : ObjectId("572dc9c17bed90127e183950"), "nama" : "Ade Sukarno", "alamat" : "Perumahan Asri Bekasi", "jenkel" : "laki-laki" }
{ "_id" : ObjectId("572dc9c17bed90127e183951"), "nama" : "Nanin", "alamat" : "Ciracas, Jakarta", "jenkel" : "Perempuan", "pendidikan" : [ { "tingkat_pendidikan" : "Stata 1", "gelar" : "Sarjana Hukum", "nama_kampus" : "Universitas Abal-Abal" } ] }
```

Untuk menampilkan hasil yang rapi tambahkan method `pretty()`

```
db.siswa.find().pretty();
```

Hasil :

```
{
        "_id" : ObjectId("572dbe4c7bed90127e18394e"),
        "nama" : "Ucup Timposu",
        "alamat" : "jln. Jones",
        "jenkel" : "laki-laki"
}
{
        "_id" : ObjectId("572dc20b7bed90127e18394f"),
        "nama" : "Kurniawan",
        "alamat" : "Jl. Maju Mundur",
        "jenkel" : "laki-laki"
}
{
        "_id" : ObjectId("572df94f7bed90127e183952"),
        "nama" : "Danu Wirnoyo",
        "alamat" : "Ciracas, Jakarta",
        "jenkel" : "laki-laki"
}
{
        "_id" : ObjectId("572dc9c17bed90127e183950"),
        "nama" : "Ade Sukarno",
        "alamat" : "Perumahan Asri Bekasi",
        "jenkel" : "laki-laki"
}
{
        "_id" : ObjectId("572dc9c17bed90127e183951"),
        "nama" : "Nanin",
        "alamat" : "Ciracas, Jakarta",
        "jenkel" : "Perempuan",
        "pendidikan" : [
                {
                        "tingkat_pendidikan" : "Stata 1",
                        "gelar" : "Sarjana Hukum",
                        "nama_kampus" : "Universitas Abal-Abal"
                }
        ]
}
```

## Limit

Untuk menampilkan hanya 1 data, gunakan method `findOne()`

contoh :

```
db.siswa.findOne();
```
Hasil

```
{
        "_id" : ObjectId("572dbe4c7bed90127e18394e"),
        "nama" : "Ucup Timposu",
        "alamat" : "jln. Jones",
        "jenkel" : "laki-laki"
}
```

{% include iklan-box.html %}

## Menggunakan Where

| Kondisi	|     Perintah    	| Contoh Penggunaan	| Persamaan kalau di RDBMS |
| ----------|:---------------:|----------|-------------------------|
| Sama dengan	| {<key>:<value>} |	db.mycol.find({"nama":"Ucup Timposu"}).pretty()	| where nama = 'Ucup Timposu' |
| Lebih kecil	| {<key>:{$lt:<value>}} |	db.mycol.find({"nilai":{$lt:50}}).pretty() |	where nilai < 50 |
| Lebih kecil atau sama dengan |	{<key>:{$lte:<value>}}	| db.mycol.find({"nilai":{$lte:50}}).pretty() |	where nilai <= 50 |
| Lebih besar | 	{<key>:{$gt:<value>}}	| db.mycol.find({"nilai":{$gt:50}}).pretty() |	where nilai > 50 |
| Lebih besar atau sama dengan |	{<key>:{$gte:<value>}}	| db.mycol.find({"nilai":{$gte:50}}).pretty()	| where nilai >= 50 |
| Tidak sama |	{<key>:{$ne:<value>}} |	db.mycol.find({"nilai":{$ne:50}}).pretty()	 | where nilai != 50 |


Contoh :

```
db.siswa.find({nama:"Ade Sukarno"}).pretty()
```

Hasil

```
{
        "_id" : ObjectId("572dc9c17bed90127e183950"),
        "nama" : "Ade Sukarno",
        "alamat" : "Perumahan Asri Bekasi",
        "jenkel" : "laki-laki"
}
```

## Fungsi AND MongoDB

Untuk menjalankan fungsi `AND` dalam MongoDB, kita cukup menggunakan 2 kata kunci yang akan diproses dan dipisahkan tanda koma `,`.

Contoh:

```
db.siswa.find({"alamat" : "Jakarta" , "jenkel" : "laki-laki"});
```

Hasil

```
{
        "_id" : ObjectId("572df94f7bed90127e183952"),
        "nama" : "Danu Wirnoyo",
        "alamat" : "Jakarta",
        "jenkel" : "laki-laki"
}
```

## Fungsi OR MongoDB

Berbeda dengan fungsi AND yang menggunakan koma,fungsi OR menggunakan keyword `$or` seperti di bawah ini:

```
db.siswa.find(
   {
      $or: [
       {key1: value1}, {key2:value2}
      ]
   }
)
```

Contoh Penggunaan :

```
db.siswa.find({$or:[{ "nama" : "Ade Sukarno" },{"alamat" : "jln. Yang Hampa Tanpamu"}]}).pretty();
```

Hasil :

```
{
        "_id" : ObjectId("572dc9c17bed90127e183950"),
        "nama" : "Ade Sukarno",
        "alamat" : "Perumahan Asri Bekasi",
        "jenkel" : "laki-laki"
}
```

{% include iklan-box.html %}

## Fungsi AND dan OR bersamaan

Kita dapat menggabung kedua fungsi AND dan OR secara bersamaan :

```
db.siswa.find({"jenkel" : "laki-laki", $or:[{ "alamat":"Ciracas, Jakarta" },{"alamat" : "Bekasi"}]});
```

Hasil

```
{
        "_id" : ObjectId("572df94f7bed90127e183952"),
        "nama" : "Danu Wirnoyo",
        "alamat" : "Ciracas, Jakarta",
        "jenkel" : "laki-laki"
}
```

### Referensi

[java2s.com](http://www.java2s.com/Tutorials/Java/MongoDB/index.htm)
