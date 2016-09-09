---
comments: true
date: 2015-01-04 05:42:20+00:00
layout: article
slug: tutorial-dasar-sqlite
title: Tutorial Dasar SQLite
categories: artikel
tags: [artikel, mvc]
ads: true
---

[Sebelumnya, kita telah membahas tentang apa itu SQLite](http://timposu.com/apa-itu-sqlite/), saya akan membagikan perintah dasar di SQLite.
Silahkan[ download SQLite](http://www.sqlite.org/download.html) terlebih dahulu dan menginstallnya.
Jika anda memakai Windows, contoh file yang didownload  bernama  sqlite-shell-win32-x86-3080704.zip
kemudian ekstraks filenya, anda akan menemukan  file sqlite3.exe , pada tutorial ini saya menyimpan file sqlite3.exe di drive D . Masuk ke Command Prompt kemudian arahkan ke direktori sqlite dalam hal ini drive D:

**Membuat / Membuka Database**

Kita akan membuat database sekaligus file dengan nama "kampus.db" nama tidak harus sama dan  ekstensi tidak harus db, tanpa ekstensi pun database dapat dproses, jadi nama database suka-2 anda.<!-- more -->


    
    D:\sqlite3 kampus.db
     SQLite version 3.7.14.1 2012-10-04 19:37:12
     Enter ".help" for instructions
     Enter SQL statements terminated with a ";"



Setelah itu anda akan masuk ke prompt sqlite
**Melihat Database**


    
    .databases
    
    





**Membuat tabel.**


    
     create table mahasiswa ( nim integer primary key ,nama varchar );
    



**Melihat daftar table**

Sekarang kita sudah mempunyai tabel mahasiswa. untuk melihat daftar tabel, gunakan perintah .tabels


    
    .tables
     mahasiswa



**Memodifikasi tabel**

Anggaplah kita ingin menambahkan kolom alamat  kedalam tabel. kita bisa menggunakan perintah _alter_


    
    alter table mahasiswa add column alamat varchar;



**Melihat struktur tabel**
Untuk melihat structur tabel, kita menggunakan perintah .schema namatabel.


    
    .schema mahasiswa



**Memasukan data ke tabel**


    
    insert into mahasiswa (nim, nama, alamat)
    values('1','Ucup Topeko' , 'Jlan Penuh Asmara'),
    ('2','Saiful','Jlan Nafsu Belaka');



atau


    
    insert into mahasiswa values('3','Udin','Jln Aku yang hampa tanpamu ');
    
    
    insert into mahasiswa values('4','Ijonk','Jln Jandaku');
    



Cara memasukan data di SQLite tidak jauh berbeda dengan MySQL atau database yang lain

**Melihat Isi Tabel **


    
    select * from mahasiswa;
    1|Ucup Topeko|Jlan Penuh Asmara
    2|Saiful|Jlan Nafsu Belaka
    3|Udin|Jln Aku yang hampa tanpamu
    4|Ijonk|Jln Jandaku





Agar perintah select menampilkan nama kolom dan data terlihat lebih rapih, gunakan perintah berikut


    
    .header on
    .mode column
    select * from mahasiswa;
     nim         nama             alamat
     --------    --------------  --------------------------
    1            Ucup Topeko     Jlan Penuh Asmara
    2            Saiful          Jlan Nafsu Belaka
    3            Udin            Jln Aku yang hampa tanpamu
    4            Ijonk           Jln Jandaku



**Mengubah data**


    
    update mahasiswa set nama='Unyil' where nim='1';
    select * from mahasiswa; 
     nim        nama              alamat
     ---------- --------------   --------------------------
    1            Unyil           Jlan Penuh Asmara
    2            Saiful          Jlan Nafsu Belaka
    3            Udin            Jln Aku yang hampa tanpamu
    4            Ijonk           Jln Jandaku



**Menghapus Data**


    
    delete from mahasiswa where nim='1';
    select * from book;
    nim          nama             alamat
     ---------- -------------- --------------------------
    2            Saiful          Jlan Nafsu Belaka
    3            Udin            Jln Aku yang hampa tanpamu
    4            Ijonk           Jln Jandaku



**Export Data Tabel**
Untuk mengexport data kedalam format SQL, gunakan perintah berikut


    
    .output mahasiswa.sql
    .dump mahasiswa





**Import data**


    
     drop table mahasiswa;
    .read mahasiswa.sql





Sampai sini dulu... ya... stay terus di blog ini...untuk dapatkan info terbaru...

Tonton di Youtube




