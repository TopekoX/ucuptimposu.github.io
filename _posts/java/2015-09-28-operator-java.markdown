---
comments: true
date: 2015-09-28 11:40:24+00:00
layout: article
slug: operator-java
title: Java - Operator Java
categories: java
tags: [java]
ads: true
series : "Tutorial Java Core"
image:
  feature:
  teaser: java.jpg
---

Didalam java ada beberapa jenis operator yang digunakan untuk memanipulasi variabel.



### Operator Aritmatika



Operator aritmatika digunakan untuk melakukan perhitungan matematika. Sebagai contoh variabel `a=10` dan `b=30`

| Operator | Keterangan | contoh |
|:----------:|------------|--------|
| +	| Penjumlahan	| a + b menghasilkan 40 |
| -	| Pengurangan	| b - a menghasilkan 20 |
| *	| Perkalian	| a * b menghasilkan 300 |
| /	| Pembagian	| b / a menghasilkan 3 |
| %	| Modulus / Sisa hasil pembagian	| 7 % 2 menghasilkan 1 (karena 1 sisa hasil bagi 7 : 2) |
| ++	| Increment	| Menambahkan 1 nilai contoh b++ = 31 |
| --	| Decrement	| Mengurangi 1 nilai contoh b-- = 29   |




<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

### Operator Relasi



Operator relasi hanya akan menghasilkan nilai boolean true atau false. Sebagai contoh variabel `a=10` dan `b=30`

| Operator | Keterangan | contoh |
|----------|------------|--------|
| ==	| sama dengan	| a == b menghasilkan false |
| !=	| tidak sama	| a != b mengasilkan true |
| >	| lebih besar	| a > b menghasilkan false |
| <	| lebih kecil	| a < b menghasilkan true |
| >=	| lebih besar atau sama|	a >= b menghasilkan false |
| <=	| lebih kecil	| a <= b menghasilkan true |


<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

### Operator Logika



Operator logika digunakan untuk membandingkan 2 buah tipe data boolean.. hasilnya pun berupa boolean. Contoh a true dan b false.

<table >

<tr >
Operator
Keterangan
contoh
</tr>

<tbody >
<tr >

<td >&&
</td>

<td >logika AND
</td>

<td >a && b menghasilkan false (akan menghasilkan true jika kedua nilainya true)
</td>
</tr>
<tr >

<td >||
</td>

<td >logika OR
</td>

<td >a || b mengasilkan true (akan menghasilkan false jika keduanya false)
</td>
</tr>
<tr >

<td >!
</td>

<td >logika NOT
</td>

<td >!b akan menghasilkan true (lawan dari nilai variabelnya)
</td>
</tr>
</tbody>
</table>

Sebenarnya masih ada jenis operator lainnya tapi saya hanya membahas diatas karena operator diatas paling banyak digunakan untuk operator lain silahkan menuju [ke sini](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/operators.html).

{% include series.html %}
