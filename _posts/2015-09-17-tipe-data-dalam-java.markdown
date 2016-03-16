---
author: ucup
comments: true
date: 2015-09-17 08:48:14+00:00
layout: article
slug: tipe-data-dalam-java
title: Java - Tipe Data dalam Java
wordpress_id: 1205
categories:
- Java

tags:
- Java
- Java Dasar
---

Didalam java ada 2 jenis tipe data





  * Tipe data primitif (_Primitive Data Types_)


  * Tipe data referensi / objek (_Reference/Object Data Types_)





#### Tipe data primitif



Java sebenarnya tidak full OOP karena masih menggunakan tipe data primitif, kenapa? karena tipe data ini bukanlah objek sehingga tidak mempunyai method dan hanya memiliki data saja.

<!-- more -->

<table border=1>

<tr >
Tipe Data
Ukuran (bit)
 Nilai Minimal
Nilai Maksimal
 Keterangan
</tr>

<tbody >
<tr >

<td >  byte 
</td>

<td >8 bit (1 byte)
</td>

<td >-128
</td>

<td >127
</td>

<td >Tipe data ini lebih menghemat memori dibanding dengan int, terutama kalau datanya berupa array
</td>
</tr>
<tr >

<td >short
</td>

<td >16 bit (2 byte)
</td>

<td >-32768
</td>

<td > 32767
</td>

<td >Sama dengan byte, gunakan kalau perlu optimisasi penggunaan memory, terutama kalau datanya berupa array
</td>
</tr>
<tr >

<td > int
</td>

<td >32 bit (4 byte)
</td>

<td >-2147483648
</td>

<td >2147483647
</td>

<td >int adalah tipe data yang paling sering digunakan untuk representasi bilangan bulat. Kalau jangkauan angkanya kurang lebar gunakan long.
</td>
</tr>
<tr >

<td >long
</td>

<td >64 bit (8 byte)
</td>

<td >-9223372036854775808
</td>

<td >9223372036854775807
</td>

<td >Data ini digunakan jika jangkauannya lebih besar dari int
</td>
</tr>
<tr >

<td >float
</td>

<td >32 bit (4 byte)
</td>

<td >
</td>

<td >
</td>

<td > float adalah tipe data pecahan yang didefnisikan oleh standard IEEE 754.
</td>
</tr>
<tr >

<td >double
</td>

<td >64 bit (8 byte)
</td>

<td >
</td>

<td >
</td>

<td >double adalah tipe data pecahan yang didefnisikan oleh standard IEEE 754. Umumnya digunakan sebagai tipe data default untuk nilai desimal.
</td>
</tr>
<tr >

<td >boolean** **
</td>

<td >8 bit (1 byte)
</td>

<td >
</td>

<td >
</td>

<td >nilai hanya _true_ atau _false _(benar atau salah)
</td>
</tr>
<tr >

<td >char
</td>

<td >16 bit (2 byte)
</td>

<td >
</td>

<td >
</td>

<td >menyimpan nilai berupa karakter _unicode_
</td>
</tr>
</tbody>
</table>

Contoh :



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
    char i = '\u003F'; // outputnya ?



tentu anda bertanya kenapa output dari variabel char i  hasilnya ? .. karena char memang untuk memproses data _unicode_ berupa karakter dan kode u003F adalah kode _unicode _dari karakter ? dan tanda \ di dalam java adalah penanda bahwa kode (dibelakangnya) tersebut adalah karakter (char). Untuk melihat karakter _unicode_ lainnya bisa disearch di google, salah satunya bisa kita lihat di[ http:http://www.utf8-chartable.de/](http:http://www.utf8-chartable.de/).



#### Wrapper Class



Wrapper class adalah tipe data yang berupa object, setiap tipe data primitif mempunyai persamaan di wrapper class ini. Walaupun wrapper  berupa class, variabel yang memegang objectnya bukanlah variabel reference. Artinya kalau ada dua buah variabel yang memegang nilai sama, satu variabel nilainya diganti maka variabel yang lain tidak akan ikut berubah nilainya. Sifat ini disebut dengan immutable

Contoh :



    Integer a = new Integer(5);
    int b = a.intValue();
    long c = 100;
    Long d = Long.valueOf(c);
    int e = Integer.parseInteger("100");







#### Referensi







  * [https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html)


  * [https://en.wikipedia.org/wiki/Primitive_wrapper_class](https://en.wikipedia.org/wiki/Primitive_wrapper_class)
