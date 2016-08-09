---
layout: article
title: Java OOP - Keyword Static Dalam Java
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
date: 2016-08-09T23:18:32+08:00
---

Keyword `static` dalam java berfungsi untuk agar method dan variabel akan menjadi milik class bukan milik suatu instance. Dengan kata lain dengan menggunakan `static` kita tidak perlu membuat instance untuk memanggil method dan variabel.

### Contoh Tanpa Static:

```java

class DemoStatic {

	String nama = null;

	public String getNama() {
		return nama;
	}

	public void setNama(String nama) {
		this.nama = nama;
	}

	public static void main(String[] args) {
		DemoStatic d1 = new DemoStatic();
		DemoStatic d2 = new DemoStatic();

		d1.setNama("Ucup");
		System.out.println("Nama " + d1.getNama());
		System.out.println("Nama " + d2.getNama());

	}

}
```

Hasil

```
Nama Ucup
Nama null
```

Dari hasil di atas dapat kita lihat bahwa instance d2 belum terisi value untuk variable `nama` sehingga masih bernilai `null`.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

### Contoh dengan static

```java
class DemoStatic {

	static String nama = null;

	public String getNama() {
		return nama;
	}

	public void setNama(String nama) {
		this.nama = nama;
	}

	public static void main(String[] args) {
		DemoStatic d1 = new DemoStatic();
		DemoStatic d2 = new DemoStatic();

		d1.setNama("Ucup");
		System.out.println("Nama " + d1.getNama());
		System.out.println("Nama " + d2.getNama());

	}

}
```

Hasil

```
Nama Ucup
Nama Ucup
```

Kenapa demikian?  Bila suatu class memiliki static variable, maka variable tersebut akan dipakai bersama2 oleh object-object dari class tersebut.

### Contoh method Static

```java
class DemoStatic {

	static void getNama(){
		System.out.println("Halo Ucup");
	}

	public static void main(String[] args) {

		DemoStatic.getNama();

	}

}
```

Hasil :

```
Halo Ucup
```

Dari hasil di atas kita dapat memanggil method `getNama()` tanpa harus membuat instance-nya dulu.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>
