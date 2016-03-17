---
comments: true
date: 2015-09-18 09:54:39+00:00
layout: article
slug: java-variabel-dalam-java
title: Java - Variabel dalam Java
categories: java
tags: [java]
ads: true
image:
  feature:
  teaser: java.jpg
---

Variabel adalah suatu tempat menyimpan suatu nilai atau data kedalam suatu tempat yang diwakili dengan nama. Masing-masing variabel di Java memiliki jenis tertentu, yang memiliki ukuran dan tata letak memori , rentang nilai yang dapat disimpan dalam memori , dan seperangkat operasi yang dapat diterapkan ke variabel.

Berikut contoh mendeklarasikan satu tipe data Java dan nama variabel. Untuk mendeklarasikan lebih dari satu variabel dari jenis tertentu, Anda dapat menggunakan koma `,` untuk memisahkannya.

<!-- more -->


    int a, b, c;         // deklarasi 3 variabel sekaligus dengan nama a, b, dan c.
    int a = 10, b = 10;  // contoh initialization, memasukan nilai 10 kedalam variabel dengan nama a dan 10 kedalam nama b.
    byte B = 22;         // initializes tipe data byte ke variable B.
    double xx = 3.14159; // declares dan assigns nilai ke variabel xx.



Ada 3 jenis variabel:





  * Local variables


  * Instance variables


  * Class/static variables







### Local Variable



Variabel lokal hanya dideklarasikan dalam method, constructor, atau blok. Variabel lokal tidak dapat digunakan di luar  method, constructor, atau blok tempat dideklarasikan.

**Contoh :**


```java
class DemoVariabelLokal{

	// membuat method lokal test
	void test(){
	 int umur=0; //mendeklarasikan variabel lokal dengan nama umur dan memasukan nilai 0 ke dalamnya
	 umur = umur + 20; //memasukan nilai umur yang sudah ada ditambah dengan 20
	 System.out.println("Umur saya : " + umur);
	}       

	public static void main(String[] args){
	    DemoVariabelLokal demo = new DemoVariabelLokal(); // instansiasi objek dari kelas DemoVariabelLokal
	     demo.test(); //memanggil method test yang ada di dalam kelas DemoVariabelLokal
	}

}
```


output :



    Umur saya : 20



**Contoh :**

Kita akan mencoba mendefinisikan variabel lokat tanpa inisialisasi variabel

```java
class DemoVariabelLokal{
	// membuat method lokal test
	void test(){
	 int umur; //mendeklarasikan variabel lokal tanpa inisialisasi
	 umur = umur + 20; //memasukan nilai umur yang sudah ada ditambah dengan 20
	 System.out.println("Umur saya : " + umur);
	}       

	public static void main(String[] args){
	    DemoVariabelLokal demo = new DemoVariabelLokal(); // instansiasi objek dari kelas DemoVariabelLokal
	     demo.test(); //memanggil method test yang ada di dalam kelas DemoVariabelLokal
	}

}
```



output akan **error**, karena kita belum melakukan inisialisasi kevariabel umur.



    DemoVariabelLokal.java:6: error: variable umur might not have been initialized
         umur = umur + 20;
                ^
    1 error






### Instance variables



Variabel didefinisikan didalam kelas akan tetapi diuar method dan blok, dan variabel ini dapat diakses kedalam method/blok didalam kelas tersebut. Variabel tersebut juga dapat di modifikasi jika sudah di inisialisasi dan variabel tersebut besifat `public` .

Contoh

```java
class DemoVariabelInstance{
	public String nama; // instance variabel yang dapat diakses oleh objek dari DemoVariabelInstance

	//membuat method panggil getNama
	public void getNama(){
	    System.out.println("Nama Saya " + nama);
	}

	public static void main(String[] args){
	    DemoVariabelInstance demo = new DemoVariabelInstance(); // instansiasi objek dari kelas DemoVariabelInstance
	     demo.nama = "Ucup"; // memasukan "Ucup" kedalam variabel nama
	     demo.getNama(); //memanggil method getNama yang ada di dalam kelas DemoVariabelInstance
	}
}
```



Output



    Nama Saya Ucup





### Class / static  variable



Variabel static didefinisikan didalam kelas akan tetapi diuar method dan blok, dan variabel ini dapat diakses kedalam method/blok didalam kelas tersebut dengan kata kunci `static`. Method ini dapat diakses tanpa melakukan inisialisasi lagi, Variabel statis dapat diakses dengan memanggil dengan nama kelas `ClassName.VariableName`.

Contoh


```java
class DemoVariabelStatis{

public static double gaji; // membuat method static

	public static void main(String[] args) {
	    gaji = 5000000; // langsung memberi nilai gaji tanpa melakukan inisialisasi objek lagi
	    System.out.println("Gaji Saya " + gaji);
	}
}
```


pada contoh diatas kita langsung memberi nilai gaji tanpa inisialisasi telebih dahulu, pada contoh di atas bisa juga ditulis seperti dibawah ini


```java
class DemoVariabelStatis{

	public static double gaji; // membuat method static

	public static void main(String[] args) {
	    DemoVariabelStatis.gaji = 5000000; // langsung memberi nilai gaji tanpa melakukan inisialisasi objek lagi
	    System.out.println("Gaji Saya " + DemoVariabelStatis.gaji);
	}
}
```


output nya sama :



    Gaji Saya 5000000.0



