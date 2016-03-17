---
comments: true
date: 2015-01-17 06:48:45+00:00
layout: article
slug: date-time-dalam-java-dengan-simpledateformat
title: Date & Time dalam Java dengan SimpleDateFormat
categories: java
tags: [java]
ads: true
image:
  feature:
  teaser: java.jpg
---

Didalam Java, untuk memunculkan waktu sistem dengan kelas _Date()_  dan untuk melihatnya kita harus merubah tipe datanya ke String dengan method _toString()_.

Contoh<!-- more -->

```java
import java.util.Date;

public class DateDemo {

public static void main(String[] args) {
Date tanggal = new Date();

System.out.println(tanggal.toString());
}
}
```

Maka akan keluar output sbb:



    Sat Jan 17 14:38:09 PST 2015



Agar format tanggal yang dihasilkan sesuai dengan yang kita inginkan maka kita harus mengganti formatnya. Cara yang paling mudah adalah menggunakan   _SimpleDateFormat_

_SimpleDateFormat_ membutuhkan format kode sbb

![](http://i713.photobucket.com/albums/ww134/upamisterlobal/DateFormatCode_zpsbcf5020c.png)

maka kita ganti source tadi sbb

```java
public class DateDemo {

public static void main(String[] args) {
Date tanggal = new Date();

SimpleDateFormat format = new SimpleDateFormat("dd MMMM yyyy");
System.out.println("Hari ini : " + format.format(tanggal));
}
}
```
output nya



    Hari ini : 17 Januari 2015



Sesuaikan format tanggal yang di inginkan :)
