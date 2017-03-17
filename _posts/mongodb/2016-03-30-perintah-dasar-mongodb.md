---
layout: article
title: MongoDB - Perintah Dasar MongoDB
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
date: 2016-03-30T23:55:00+08:00
series: "Tutorial MongoDB"
---

{% include series.html %}

Ini adalah tutorial singkat MongoDB, yang berisi perintah-perintah dasar MongoDB

##  melihat database
```
db
```

## membuat database
contoh membuat collection dengan nama siswa
```
use  siswa
```

##  menghapus database
```
db.dropDatabase()
```

##  insert data
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

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

##  insert data array
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

##  melihat daftar collection dalam database
```
show collections
```

##  melihat isi collection
```
db.siswa.find()
```

##  melihat isi collection dalam bentuk JSON
```
db.siswa.find().pretty()
```

##  melihat isi collection hanya 1 result
```
db.siswa.findOne()
```

atau menampilkan dengan id tertentu

```
db.siswa.findOne(
 {"_id" : ObjectId("56337621a5741ce990f98a12")}
)
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

##  menghapus data (remove)
```
db.siswa.remove({
    "_id" : ObjectId("56337621a5741ce990f98a12")
})
```

##  mengubah data (update)
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

##  menghapus collection
```
db.siswa.drop()
```

### Referensi

* [https://docs.mongodb.org/manual/](https://docs.mongodb.org/manual/)
