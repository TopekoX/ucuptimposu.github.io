---
comments: true
date: 2014-07-28 21:56:32+00:00
layout: article
title: Tutorial dasar-dasar MySQL
categories: mysql
tags: [mysql, mariadb]
ads: true
image:
  feature: 
  teaser:  mysql-maria.jpg
---

### LOGIN



Login ke database server anda

![](http://i67.tinypic.com/24gjbpt.jpg)


![login](http://i64.tinypic.com/2llccr8.jpg "login mysql")



### MEMBUAT DATABASE



<!-- more -->

Untuk melihat database yang telah ada jalankan perintah



```sql
SHOW DATABASES;
```

![](http://i64.tinypic.com/14xfhbm.jpg)



Membuat database



```sql
CREATE DATABASE NAMA_DATABASE;
```



Contoh kita akan membuat database dengan nama "SEKOLAH"

![](http://i64.tinypic.com/oh0is5.jpg)

Untuk melihat database yang sudah dibuat jalankan perintah SHOW DATABASES





### MENGHAPUS DATABASE



Pada saat anda ingin menhapus database pastikan anda berhati-hati karena menghapus database sama saja menghapus data / tabel yang ada dalam database tersebut.



```sql
DROP DATABASE NAMA_DATABASE
```


![](http://i66.tinypic.com/m7evpj.jpg)

Karena pada tutorial ini kita latihan menggunakan database SEKOLAH maka ulangi langkah Membuat Database di atas untuk membuat database SEKOLAH kembali.

![](http://i68.tinypic.com/25f6fpe.jpg)


Lihat database yang anda,  pastikan database SEKOLAH yang telah kita buat tadi muncul.






### MEMBUAT TABEL



Setelah kita membuat database, database tersebut masih kosong dan belum memiliki tabel. Dan sebelum membuat tabel pastikan kita membuat tabel di database SEKOLAH



```sql
USE NAMA_DATABASE;
```


![](http://i65.tinypic.com/149ob2h.jpg)

Setelah itu baru buat tabel



```sql
CREATE TABLE NAMA_TABLE (
NAMA_ATRIBUT TIPE_DATA [KETERANGAN],
NAMA_ATRIBUT TIPE_DATA [KETERANGAN],
);
```



Contoh kita buat tabel SISWA

![](http://i68.tinypic.com/30aarkn.jpg)

Lihat tabel yang ada



```sql
SHOW  TABLES;
```


![](http://i67.tinypic.com/kdu2jc.jpg)


**MENGHAPUS TABLE**



```sql
DROP TABLE NAMA_TABEL;
```




berikut contohnya

![](http://i63.tinypic.com/slr88m.jpg)

**MEMASUKKAN DATA KE DALAM TABEL**

Oke tahap berikutnya kita akan memasukan data kedalam tabel



```sql
INSERT INTO NAMA_TABEL (NAMA_KOLOM1, NAMA_KOLOM2) VALUES (ISIKOLOM1, ISIKOLOM2)
```

ATAU

```sql
INSERT INTO NAMA_TABEL VALUES (ISIKOLOM1, ISIKOLOM2)
```



Berikut contohnya tapi sebelum itu kita buat tabel dulu contoh tabel SISWA dengan kolom ID sebagai "Primary Key" yang bersifat AUTO_INCREMENT (pemberian ID secara otomatis ), selain itu kita juga misal kita juga membuat kolom nama tipe datanya VARCHAR  dengan maksimal karakter huruf 50 digit, Alamat dengan tipe data Text dan Tanggal Lahir dengan tipe data DATE. . Bagi yang belum mengerti apa itu Primary Key dan istilah2 lainnya saya sarankan untuk membaca buku tentang konsep Database DBMS, tapi kalo gak ada bukunya cuekin aja,,, :D

![](http://i65.tinypic.com/2wd7f4l.jpg)

Memasukkan data

![](http://i67.tinypic.com/28qqkqv.jpg)

![](http://i67.tinypic.com/qs9hk0.jpg)

Pasti ada yang bertanya format tanggal nya kok gitu? tahun-bulan-tanggal ..yahhh sy cuma bisa jawab dari sononya jga gitu :p . Kita juga tidak melakukan pengisian Field ID karena sifatnya yang Auto Increment (bisa juga di isi dengan isian _null_). Diatas itu contoh pengisian untuk satu data saja. Berikut contoh pengisian dengan beberapa data.



**MENAMPILKAN DATA**

Pada bagian menampilkan data mempunyai banyak atribut tapi kita hanya akan memakai yang penting saja atau paling sering digunakan.



```sql
SELECT [ATRIBUT] FROM NAMA_TABEL
```



Menampilkan seluruh data

![](http://i65.tinypic.com/4rvziq.jpg)


Menampilkan beberapa data berdasar kolom yang di pilih

![](http://i66.tinypic.com/nz2hrr.jpg)

PENYARINGAN



```sql
SELECT [ATRIBUT] NAMA_TABEL WHERE [ATRIBUT]

```



Menampilkan data dengan ID=1


Menampilkan data yang bernama Zakia

![](http://i65.tinypic.com/2nia740.jpg)


Selain dengan tanda = kita juga bisa menggunakan tanda < , >,  !=,  >=,  <= sebagai operator penyaringan

contoh menampilkan data siswa yang lahir sebelum 1987

![](http://i63.tinypic.com/25fptop.jpg)



Proses di atas masih 1 kondisi kita bisa menambahkan kondisi lainnya dengan menggunakan AND dan OR contoh kita akan mencari yang lahir rentang waktu 1987 - 1988

![](http://i65.tinypic.com/122enn9.jpg)



menampilkan data yang lahir tanggal sebelum tahun 1985 atau yang bernama Beddu Kendeng

![](http://i63.tinypic.com/21j0sur.jpg)



Menampilkan data dengan nama yang berawalan Z menggunakan regex LIKE  Z%

![](http://i67.tinypic.com/2hfkpjl.jpg)

Menampilkan data dengan nama yang berakhiran G menggunakan regex LIKE %G

![](http://i68.tinypic.com/2z4xpmt.jpg)

Menampilkan data dengan nama yang mengandung huruf E menggunakan regex LIKE %E%

![](http://i65.tinypic.com/nl7whl.jpg)

**MENGUBAH DATA**

Perintah mengubah data menggunakan perintah UPDATE



```sql
UPDATE [NAMA_TABEL]

SET NAMA_ATRIBUT = "NILAI_BARU"

WHERE [KONDISI]
```



Misal kita mengubah Nama yang ber Id 1 menjadi Saiful Jamil

![](http://i63.tinypic.com/2lswh3.jpg)

**MENGHAPUS DATA**

Untuk menghapus data kita menggunakan perintah DELETE , misal kita menghapus data yang ber ID=3



```sql
DELETE FROM [NAMA TABEL]

WHERE [KONDISI]
```


![](http://i67.tinypic.com/4sm9t4.jpg)


Menghapus semua data

```sql
DELETE FROM [NAMA_TABLE]
```

![](http://i64.tinypic.com/2a6tjsl.jpg)

Oke bray sampe sini dulu yah kalo ada yang mau di tanyakan silahkan tinggalkan koment





## Referensi

https://dev.mysql.com/doc/
