---
author: ucup
comments: true
date: 2015-10-12 15:09:19+00:00
layout: article
slug: objek-class-java
title: Class dan Objek dalam Java
wordpress_id: 1312
categories:
- Java
tags:
- Java
- Java Dasar
---

Kita sudah masuk ke materi OOP, di dalam java kita memperlakukan class sebagai objek, class tersebut kita bisa gunakan di class lain dengan melakukan _Inheritance. _Dibawah ini adalah contoh membuat class yang di _Inheritance _:<!-- more -->



``` java A.java
class A{
      public int a;
      public String b;
}
```



kemudian kita  buat/panggil objek nya di class lain_ _



``` java B.java
public class B {
      public static void main(String[] args){

        A obj = new A(); // membuat objek class A dengan nama obj
        obj.a=10; //isi nilai variabel a
        obj.b="Halo"; //isi nilai variabel b
        System.out.println("Nilai a " + obj.a);
        System.out.println("Nilai b " + obj.b);
      }
}
```



output



    Nilai a 10
    Nilai b Halo





Dari apa yang kita lihat diatas berarti kita dapat memanipulasi data yang ada dalam objek class A setelah kitabuat objeknya `new A();` . Class berdua di atas dapat kita gabung menjadi 1 file dengan nama B.java


``` java A.java    
class A{
      public int a;
      public String b;
}
```

``` java B.java
public class B {
      public static void main(String[] args){

        A obj = new A(); // membuat objek class A dengan nama obj
        obj.a=10; //isi nilai variabel a
        obj.b="Halo"; //isi nilai variabel b
        System.out.println("Nilai a " + obj.a);
        System.out.println("Nilai b " + obj.b);
      }
}
````



output yang dihasilkan sama.
