---
layout: article
title: Mengenal MongoDB
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
date: 2016-03-28T20:18:48+08:00
---
[MongoDB](https://www.mongodb.org/) termasuk dalam kategori database NOSQL , berbeda dengan database yang biasa kita kenal seperti MySQL, MS SQL Server, Oracle dll yang termasuk RDBMS. MongoDB dibuat dari C++ dan bersifat opensource. Gaya penulisan dokumen MongoDB seperti JSON sehingga membuat integrasi data dalam aplikasi lebih mudah dan lebih cepat.

## Kelebihan MongoDB

 * Cepat
 * Ringan
 * Dapat dengan mudah berinteraksi dengan bahasa pemrograman apapun karena data yang diproses hanya berupa collection.

Di dalam MongoDB database adalah tempat menyimpan collection, jadi datanya disimpan dalam bentuk collection. Di dalam mysql collection ini sepadan dengan table.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## Konsep MongoDB

Jadi gini si MongoDB ini menggunakan database untuk mengatur data, dan database adalah tempat menyimpan collection atau koleksi. Setiap database terdiri dari sebuah file sendiri di dalam sistem MongoDB. Sebuah server MongoDB dapat memiliki  banyak database(seperti halnya MySQL).

## MongoDB vs RDBMS
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


<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>
