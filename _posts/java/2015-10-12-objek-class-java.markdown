---
comments: true
date: 2015-10-12 15:09:19+00:00
layout: article
slug: objek-class-java
title: Class dan Objek dalam Java
categories: java
tags: [java]
ads: true
image:
  feature:
  teaser: java.jpg
---

## Objek dalam Java

Setiap objek pasti memiliki perilaku dan sifat misalnya objek misalnya kursi, sepeda, penanda, bolpoin, meja, mobil dll.

Sebuah objek dalam Java memiliki tiga karakteristik:

* state : mewakili data (nilai) dari sebuah objek.
* behavior / perilaku: mewakili perilaku (fungsi) dari sebuah objek seperti membosankan, menarik dll
* identity / identitas: Identitas Obyek biasanya dilaksanakan melalui ID unik. Tapi, itu digunakan secara internal oleh JVM untuk mengidentifikasi setiap objek unik.

Contoh: Messi adalah objek. Namanya Lionel Messi , kulitnya putih, hal tersebut yang dikenal sebagai state. Messi adalah pemain sepak bola , sehingga bermain sepak bola adalah perilakunya.

Objek merupakan instance dari kelas. Class adalah template  yang objek diciptakan. Jadi objek adalah instance (hasil) dari sebuah class.

## Contoh sederhana

Kita sudah masuk ke contoh OOP, di dalam java kita memperlakukan class sebagai objek, class tersebut kita bisa gunakan di class lain dengan melakukan _Inheritance._ Dibawah ini adalah contoh membuat class yang di _Inheritance _ :



``` java
class A{
      public int a;
      public String b;
}
```



kemudian kita  buat/panggil objek nya di class lain



``` java
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



<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


Dari apa yang kita lihat diatas berarti kita dapat memanipulasi data yang ada dalam objek class A setelah kitabuat objeknya `new A();` . Class berdua di atas dapat kita gabung menjadi 1 file dengan nama B.java


``` java
class A{
      public int a;
      public String b;
}

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

Terus apa jadinya kalau properti `String b` kita tidak masukan nilai?


``` java
class A{
      public int a;
      public String b;
}

public class B {
      public static void main(String[] args){

        A obj = new A(); // membuat objek class A dengan nama obj
        obj.a=10; //isi nilai variabel a dan kita tidak mengisi nilai variabel b
        System.out.println("Nilai a " + obj.a);
        System.out.println("Nilai b " + obj.b);
      }
}
````

output

```
Nilai a 10
Nilai b null
```

nilai `b` akan bernilai `null` karena kita belum memasukan nilai apapun kedalamnya.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>	

## Method
