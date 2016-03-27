---
comments: true
date: 2015-09-17 08:48:14+00:00
layout: article
slug: tipe-data-dalam-java
title: Java - Tipe Data dalam Java
categories: java
tags: [java]
ads: true
image:
  feature:
  teaser: java.jpg
---

Didalam java ada 2 jenis tipe data

  * Tipe data primitif (_Primitive Data Types_)
  * Tipe data referensi / objek (_Reference/Object Data Types_)

#### Tipe data primitif

![](http://2.bp.blogspot.com/-lNw_nnuPYoA/UQsqbExrPII/AAAAAAAAAJE/8SBpHrqlJzo/s1600/tbl+tipe+data+java.png)

Java sebenarnya tidak full OOP karena masih menggunakan tipe data primitif, kenapa? karena tipe data ini bukanlah objek sehingga tidak mempunyai method dan hanya memiliki data saja.


Contoh :

```java
// bilangan bulat (Integer)
byte a = 100 ;
short b = -10000;
int c = 100000;
long d = -200000L;

// bilangan desimal (Float Point)
float e  = 123.4f;
double f = 1.234e2;

// boolean
boolean g = true;

// karakter
char h = 'H';
char i = '\u003F'; // outputnya "?"
```

tentu anda bertanya kenapa output dari variabel char i  hasilnya ? .. karena char memang untuk memproses data _unicode_ berupa karakter dan kode `u003F` adalah kode _unicode_ dari karakter `?` dan tanda `\` di dalam java adalah penanda bahwa kode (dibelakangnya) tersebut adalah karakter (`char`). Untuk melihat karakter _unicode_ lainnya bisa disearch di google, salah satunya bisa kita lihat di [http://www.utf8-chartable.de/](http://www.utf8-chartable.de/).


<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

#### Wrapper Class



Wrapper class adalah tipe data yang berupa object, setiap tipe data primitif mempunyai persamaan di wrapper class ini. Walaupun wrapper  berupa class, variabel yang memegang objectnya bukanlah variabel reference. Artinya kalau ada dua buah variabel yang memegang nilai sama, satu variabel nilainya diganti maka variabel yang lain tidak akan ikut berubah nilainya. Sifat ini disebut dengan immutable

Contoh :

```java
Integer a = new Integer(5);
int b = a.intValue();
long c = 100;
Long d = Long.valueOf(c);
int e = Integer.parseInteger("100");
```

### Referensi

  * [https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html)


  * [https://en.wikipedia.org/wiki/Primitive_wrapper_class](https://en.wikipedia.org/wiki/Primitive_wrapper_class)

  <center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>
