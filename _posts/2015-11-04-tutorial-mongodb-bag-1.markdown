---
comments: true
date: 2015-11-04 06:02:04+00:00
layout: article
slug: tutorial-mongodb-bag-1
title: Tutorial MongoDB (insert, update, remove) [bag. 1]
categories: mongodb
tags: [mongodb, database]
ads: true
---

![](http://i67.tinypic.com/2mnlqht.jpg)

[MongoDB](https://www.mongodb.org/) termasuk dalam kategori database NOSQL , berbeda dengan database yang biasa kita kenal seperti MySQL, MS SQL Server, Oracle dll yang termasuk RDBMS.

### Kelebihan MongoDB
 * Cepat
 * Ringan
 * Dapat dengan mudah berinteraksi dengan bahasa pemrograman apapun karena data yang diproses hanya berupa collection.

Di dalam MongoDB database adalah tempat menyimpan collection, jadi datanya disimpan dalam bentuk collection. Di dalam mysql collection ini sepadan dengan table.

### MongoDB vs RDBMS
Perbedaan MongoDB dan RDBMS

<!-- more -->


| RDBMS	         |     MongoDB                                                     |
|----------------|-----------------------------------------------------------------|
| Database       |	Database                                                   |
| Table	         |      Collection                                                 |
| Tuple/Row      |	Document                                                   |
| column         |	Field                                                      |
| Table Join     |	Embedded Documents                                         |
| Primary Key    |	Primary Key (Default key _id dibuat oleh mongodb sendiri)  |


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
