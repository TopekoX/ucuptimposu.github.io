---
layout: article
title: Java OOP - Method Overloading
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

Apa yang anda pahami mendengar kata Overloading? bisa di artikan kelebihan kapasitas. Tapi didalam Java, Overloading pada Method adalah menggunakan nama method yang sama tetapi dengan parameter yang berbeda. Jadi di dalam sebuah program Java kita dapat membuat nama method yang sama tetapi dengan parameter harus ada perbedaan.

#### Contoh sederhana

``` java
class DemoOverload {

	// membuat method(metode) dengan nama sum dan parameter a dan b
	void sum(int a, int b){
		System.out.println(a + b);
	}

	// melakukan overload dengan membuat method(metode)
	// dengan nama sum dan parameter yang berbeda (a,b dan c)
	void sum(int a, int b, int c){
		System.out.println(a + b + c);
	}

	public static void main(String[] args) {
		DemoOverload demo = new DemoOverload();
		demo.sum(1, 6);
		demo.sum(4, 2, 3);
	}
}
```

Pada contoh di atas pertama kita membuat sebuah method dengan nama `sum` dengan parameter `a` dan `b`. Selanjutnya kita melakukan overload method `sum` dengan parameter yang berbeda `a`,`b` dan `c`.

output

```
7
9
```

Yang perlu dicatat, Method overload tidak boleh memiliki nama dan parameter yang sama walaupun dengan tipe data yang berbeda.

``` java
public class DemoOverload {

	// membuat method(metode) dengan nama sum dan parameter a dan b
	int sum(int a, int b){
		return a+b;
	}

	// melakukan overload dengan membuat method(metode)
	long sum(int a, int b){
		return a-b;
	}

	public static void main(String[] args) {
		DemoOverload demo = new DemoOverload();
		demo.sum(1, 6);
		demo.sum(3, 4, 5);
	}
}

```

output

```
Error compile
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


{% include series.html %}
