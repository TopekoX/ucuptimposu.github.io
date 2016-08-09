---
layout: article
title: Java OOP - Constructor Dalam Java
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
date: 2016-07-30T15:24:59+08:00
---


Constructor dalam java adalah method khusus yang digunakan untuk initialize dari sebuah object. Secara default constructor telah dibuat otomatis ketika kita membuat class java, tanpa harus menuliskannya.

{% include toc.html %}

## Syarat sebuah Constructor

1. Nama Constructor harus sama dengan nama class
2. Constructor tidak boleh mengembalikan nilai

## Tipe Constructor

1. Default constructor (tanpa argumen)
2. Constructor berparameter

## Membuat default constructor

Contoh membuat constructor tanpa argumen.

```java
class DemoConstructor {

	DemoConstructor() {
		System.out.println("Halo!!! salam dari constructor");
	}

	public static void main(String[] args) {
		// menginisialisasi objek sekaligus memanggil constructor
		DemoConstructor demoConstructor = new DemoConstructor();
	}
}
```

output

```
Halo!!! salam dari constructor
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## Membuat constructor dengan parameter

```java
class DemoConstructor {

	String nama;
	int umur;

	DemoConstructor(String x, int y) {
		nama = x;
		umur = y;
	}

	void tampil(){
		System.out.println("Nama = " + nama );
		System.out.println("Umur = " + umur );
	}

	public static void main(String[] args) {

		DemoConstructor demoConstructor = new DemoConstructor("Ucup",25);
		demoConstructor.tampil();

	}
}
```

output

```
Nama = Ucup
Umur = 25
```

## Constructor Overloading

```java
class DemoConstructor {

	String nama;
	int umur;
  String alamat;

	DemoConstructor(String x, int y) {
		nama = x;
		umur = y;
	}

  DemoConstructor(String x, int y, String z) {
		nama = x;
		umur = y;
    alamat = z;
	}

	void tampil(){
		System.out.println("Nama = " + nama );
		System.out.println("Umur = " + umur );
    System.out.println("Alamat = " + alamat );
	}

	public static void main(String[] args) {

		DemoConstructor demoConstructor1 = new DemoConstructor("Ucup",25);

    demoConstructor.tampil();

	}
}
```

output

```
Nama = Ucup
Umur = 25
Alamat = null
===============================
Nama = Ucup
Umur = 25
Alamat = Jl. Rambutan
```

## Perbedaan Method dan Constructor

| Constructor | Method  |
|-------------|---------|
| Constructor is used to initialize the state of an object.	| Method is used to expose behaviour of an object.|
| Constructor must not have return type. |	Method must have return type. |
| Constructor is invoked implicitly. |	Method is invoked explicitly. |
| The java compiler provides a default constructor if you don't have any constructor.	| Method is not provided by compiler in any case. |
| Constructor name must be same as the class name.	| Method name may or may not be same as class name. |

{% include series.html %}

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>
