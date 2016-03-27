---
comments: true
date: 2015-10-11 04:32:49+00:00
layout: article
slug: java-array
title: Java - Array
categories: java
tags: [java]
ads: true
image:
  feature:
  teaser: java.jpg
---

Kalau sebelumnya kita hanya bisa memasukan satu nilai kedalam variabel yang tersimpan dalam memory, maka dengan array kita dapat memasukan beberapa nilai sekaligus ke dalam variabel array.

## Deklarasi Array

```java
tipedata[] namaVariabel;

// atau

tipedata namaVariabel[];
```

## Membuat Array

Untuk membuat array kita harus membua referensi array tipedata tersebut sbb:

```java
tipedata[] namaVariabel = new tipedata[size];
```
atau sizenya bisa langsung diisi

```java
tipedata[] namaVariabel = {value0, value1, value2, ...};
```

## Array 1 Dimensi

Index di dalam array dimulai dari __0 bukan  1__, jadi kalau kita mendeklarasikan array :

```java
int[] nilai = new int[10];
```

Berarti kita telah membuat 10 ruang untuk diisi nilai dengan index ruang tersebut dimulai dengan index 0 dan berakhir dengan index 9.

![Java array](https://docs.oracle.com/javase/tutorial/figures/java/objects-tenElementArray.gif) 

[sumber gambar disini](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html)

### contoh

```java
public class DemoArray {

	public static void main(String[] args) {

		int[] nilai = new int[10];

		nilai[0] = 10;
		nilai[1] = 29;
		nilai[2] = 78;
		nilai[3] = 22;
		nilai[4] = 74;
		nilai[5] = 23;
		nilai[6] = 87;
		nilai[7] = 34;
		nilai[8] = 32;
		nilai[9] = 13;

	}
}
```
<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

#### Menggunakan length

kita bisa menggunakan `length` untuk mencari jumlah lebar array.

```java
public class DemoArray {

	public static void main(String[] args) {

		int[] nilai = new int[10];

		nilai[0] = 10;
		nilai[1] = 29;
		nilai[2] = 78;
		nilai[3] = 22;
		nilai[4] = 74;
		nilai[5] = 23;
		nilai[6] = 87;
		nilai[7] = 34;
		nilai[8] = 32;
		nilai[9] = 13;

		for(int i=0; i < nilai.length; i ++){
			System.out.println(nilai[i]);
		}

	}
```
output

```
10
29
78
22
74
23
87
34
32
13
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

#### Menggunakan foreach

Selain menggunakan `length` kita juga bisa menggunakan `foreach` untuk menampilkan nilai dalam array

```java
public class DemoArray {

	public static void main(String[] args) {

		int[] nilai = new int[10];

		nilai[0] = 10;
		nilai[1] = 29;
		nilai[2] = 78;
		nilai[3] = 22;
		nilai[4] = 74;
		nilai[5] = 23;
		nilai[6] = 87;
		nilai[7] = 34;
		nilai[8] = 32;
		nilai[9] = 13;

		for(int i : nilai){  //menggunakan foreach
			System.out.println(i);
		}
  }
}
```

Hasilnya outputnya sama dengan `length`

## Array 2 Dimensi

Selain 1 dimensi array bisa juga dalam bentuk 2 dimensi. Untuk mempermudah memahaminya ingat saja tabel pasti ada kolom dan baris.

![](http://www.tutorialspoint.com/cprogramming/images/two_dimensional_arrays.jpg)

Gambar diambil dari [sini](http://www.tutorialspoint.com)

### Contoh

```java
public class DemoArray2Dimensi {

	public static void main(String[] args) {

		// contoh membuat array 4 baris dan 3 kolom
		String[][] biodataArray = {
                  {"Ucup","Jln. Maleo","Palu"},
                  {"Ferry","Jln. Beriman","Aceh"},
                  {"Ade Sukarno","Jln. Maju Terus","Bekasi"},
                  {"Dafiq","Jln. Beriman","Lampung"}
		};

		for (int i = 0 ; i < 4; i++){
			for (int x = 0; x < 3; x ++){
				System.out.print(biodataArray[i][x]);
				System.out.print(" | ");
			}
			System.out.println();
		}
	}

}
```

Output

```
Ucup | Jln. Maleo | Palu |
Ferry | Jln. Beriman | Aceh |
Ade Sukarno | Jln. Maju Terus | Bekasi |
Dafiq | Jln. Beriman | Lampung |
```

Dengan memahami konsep array kita akan mudah memahami konsep collection dan Pemrograman lain seperti JSON, atau MongoDB yang menggunakan collection dalam mengelola datanya.

### Referensi
 [https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html)
