---
comments: true
date: 2015-11-04 06:02:04+00:00
layout: article
title: Tutorial MongoDB
categories: tutorial
tags: [mongodb, database]
ads: true
image:
  feature: feature/mongodb.jpg
  teaser:  mongo.jpg
  credit: mongowithmahesh.in
  creditlink: http://mongowithmahesh.in/
---

[MongoDB](https://www.mongodb.org/) termasuk dalam kategori database NOSQL , berbeda dengan database yang biasa kita kenal seperti MySQL, MS SQL Server, Oracle dll yang termasuk RDBMS. MongoDB dibuat dari C++ dan bersifat opensource. Gaya penulisan dokumen MongoDB seperti JSON sehingga membuat integrasi data dalam aplikasi lebih mudah dan lebih cepat.

## 1. Intro MongoDB

Pengantar tutorial MongoDB

* [Mengenal MongoDB](/mengenal-mongodb/)
* [Install MongoDB di Windows](/cara-install-mongodb-windows/)
* [Install MongoDB di Linux](/cara-install-mongodb-di-linux/)


### Perintah Dasar MongoDB :

####  melihat database
```
db
```

#### membuat database
contoh membuat collection dengan nama siswa
```
use  siswa
```

####  menghapus database
```
db.dropDatabase()
```

####  insert data
contoh membuat tabel sekaligus melakukan insert

```
db.siswa.insert(
    {
        "nama":"Ucup",
        "alamat":"Jln. Loyo Selalu",
        "usia":13
    }
)
```
Id key otomatis dibuatkan

####  insert data array
```
db.siswa.insert(
    [{
        "nama":"Azwar Anas",
        "alamat":"Jln. Slamet Riyadi",
        "usia":15
     },
     {
        "nama":"Abd Munir",
        "alamat":"Jln. Sutoyo",
        "usia":17
     }    
    ]
)
```

####  melihat daftar collection dalam database
```
show collections
```

####  melihat isi collection
```
db.siswa.find()
```

####  melihat isi collection dalam bentuk JSON
```
db.siswa.find().pretty()
```

####  melihat isi collection hanya 1 result
```
db.siswa.findOne()
```

atau menampilkan dengan id tertentu

```
db.siswa.findOne(
 {"_id" : ObjectId("56337621a5741ce990f98a12")}
)
```

####  menghapus data (remove)
```
db.siswa.remove({
    "_id" : ObjectId("56337621a5741ce990f98a12")
})
```

####  mengubah data (update)
```
db.siswa.update(
    {"_id" : ObjectId("56337621a5741ce990f98a11")},
    {
     "nama" : "Azwar Anas",
     "alamat" : "Jln. Taubat Nasuha",
     "usia" : 15
    }
)
```

####  menghapus collection
```
db.siswa.drop()
```
