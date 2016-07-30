---
layout: article
title: Java OOP - Method dalam Java
modified:
categories: java
excerpt:
tags: [java, javacore]
comments: true
ads: true
series: "Tutorial Java Core"
image:
  feature:
  teaser:
  thumb:
date: 2016-07-11T23:16:42+08:00
---

Method atau metode adalah sebuah fungsi(function) yang berisi algoritma untuk melakukan tugas tertentu. Method sepada dengan function dalam PHP atau Javascript. Method berada di dalam blok class, yang dapat dipanggil didalam class yang sama ataupun di class berbeda (sesuai aksesnya).

{% include toc.html %}

## Method yang mengembalikan nilai

Method yang mengembalikan nilai akan menghasilkan nilai ketika method ini dipanggil. Untuk mengembalikan nilai harus menggunakan keyword `return`.

Contoh deklarasi :

```java
tipeData namaMethod() {
    return nilaiYgDikembalikan
}
```

Contoh

```java
String getNama() {
    return "Ucup";
}
```

Method di atas ketika dipanggil akan mengembalikan nilai dengang tipe data `String` yang bernilai `Ucup`. Yang perlu diperhatihan tipe data yang dikembalikan harus sama dengan tipe data nilai yang dikembalikan.

## Method yang tidak mengembalikan nilai

Selain mengembalikan nilai method juga ada juga yang tidak mengembalikan nilai

```java
void namaMethod() {
    // Lakukan Sesuatu
}
```

contoh

```java
void setNama() {
    nama = "Ucup";
}
```
<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## Method berparameter

Parameter adalah nilai yang dimasukkan kedalam sebuah method. Nilai tersebut disisipkan kedalam `()`

Contoh

```java
void setUmur(String umur) {
    um = umur;
}
```

## Contoh 1

```java
class DemoMethod {

	String nama;
	int umur;

	// method tanpa pengembalian nilai
	void setNama(){
		nama = "Ucup";
	}

	// method dengan pengembalian nilai nama dengan tipe data String
	String getNama(){
		return nama;
	}

	// method dengan parameter
	void setUmur(int umr){
		umur = umr;
	}

	// method dengan pengembalian nilai umur dengan tipe data Integer
	int getUmur(){
		return umur;
	}

	public static void main(String[] args) {
		DemoMethod demoMethod = new DemoMethod();

		// memanggil method setNama
		demoMethod.setNama();

		// memanggil method getNama dan memasukan kedalam variabel namaPerson		
		String namaPerson = demoMethod.getNama();

		// memasukan nilai umur ke dalam method
		demoMethod.setUmur(25);

		System.out.println("Nama : " + namaPerson);
		System.out.println("Umur : " + demoMethod.getUmur());

	}

}
```

Hasil

```
Nama : Ucup
Umur : 25
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## Contoh 2

```java
class DemoMethod2 {

  /* Membuat method berparameter penjumlahan,
  * pengurangan, perkalian dan pembagian
  */
	void penjumlahan(int a, int b){
		System.out.println("Nilai " + a + " + " + b + " = " + (a+b));
	}

	void pengurangan(int a, int b){
		System.out.println("Nilai " + a + " - " + b + " = " + (a-b));
	}
	void perkalian(int a, int b){
		System.out.println("Nilai " + a + " x " + b + " = " + (a*b));
	}

	void pembagian(int a, int b){
		System.out.println("Nilai " + a + " / " + b + " = " + (a/b));
	}

	public static void main(String[] args) {

		DemoMethod2 demoMethod = new DemoMethod2();

    // memanggil method
		demoMethod.penjumlahan(3, 5);
		demoMethod.pengurangan(5, 4);
		demoMethod.perkalian(4, 5);
		demoMethod.pembagian(10, 2);

	}

}
```

output

```
Nilai 3 + 5 = 8
Nilai 5 - 4 = 1
Nilai 4 x 5 = 20
Nilai 10 / 2 = 5
```

{% include series.html %}
