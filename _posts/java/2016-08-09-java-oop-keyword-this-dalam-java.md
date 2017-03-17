---
layout: article
title: Java OOP - Keyword This Dalam Java
modified:
categories: java
excerpt:
tags: [java, javacore]
comments: true
ads: true
series: "Tutorial Java Core"
image:
  feature:
  teaser: java.jpg
  thumb:
date: 2016-08-09T23:44:44+08:00
---

Keyword `this` dipergunakan untuk menyatakan objek sekarang, biasanya dipergunakan untuk menghindari variabel dengan nama yang sama antara variabel class dengan variabel property.

### Contoh tanpa this

```java
class DemoThis {

	String nama;
	int id;

	void setSiswa(int id, String nama){
		id = id;
		nama = nama;
	}

	void tampil(){
		System.out.println("ID : " + id);
		System.out.println("Nama : " + nama);

	}

	public static void main(String[] args) {
		DemoThis demoThis = new DemoThis();

		demoThis.setSiswa(1, "Ucup");
		demoThis.tampil();
	}
}
```

Hasil

```
ID : 0
Nama : null
```

Contoh di atas kita tidak menggunakan `this` pada method `setSiswa`.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

### Contoh dengan this

```java
class DemoThis {

	String nama;
	int id;

	void setSiswa(int id, String nama){
		this.id = id;
		this.nama = nama;
	}

	void tampil(){
		System.out.println("ID : " + id);
		System.out.println("Nama : " + nama);

	}

	public static void main(String[] args) {
		DemoThis demoThis = new DemoThis();

		demoThis.setSiswa(1, "Ucup");
		demoThis.tampil();
	}
}
```

Hasil

```
ID : 1
Nama : Ucup
```

pada contoh di atas kita menambahkan `this` pada blok method `setSiswa` pada variabel `id` dan `nama` yang mengarah pada variabel pada class bukan pada parameter method `setSiswa`.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>
