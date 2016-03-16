---
author: ucup
comments: true
date: 2015-09-12 10:58:49+00:00
layout: article
slug: syntax-dasar-java
title: Java - Syntax Dasar Java
wordpress_id: 1156
categories:
- Java

tags:
- Java
- Java Dasar
---

Didalam Bahasa Pemograman Java, kita mengenal





  * **Class **: Class adalah inti program java, setiap kita membuat program dalam java berarti kita akan membuat class, yang perlu diperhatikan nama class harus sama dengan nama file class tersebut contoh kita akan membuat class dengan nama file ` NamaKelas.java `





    public class NamaKelas { }







  * **Object** : Object adalah instansiasi dari class. Kalau dianalogikan class adalah sebuah cetakan dan object adalah materi hasil cetakan dari class. Setiap object akan mempunyai state (instance variabel/properties) yang membedakan satu object dengan object lain, kemudian object juga mempunyai behaviour (method) dimana logic dari class disimpan.

<!-- more -->

  * **Method** : Method adalah sekumpulan kode yang diberi nama, untuk merujuk ke sekumpulan kode tersebut digunakan sebuah nama yang disebut dengan nama method. Method bisa mempunyai parameter sebagai input dan nilai kembalian sebagai output.





    public class NamaKelas {
      void namaMethod(){}
    }







  * **Instance Variables **: Setiap objek memiliki seperangkat properti yang unik dari variabel. Variabel tersebut dapat diisi/dimodifikasi dengan nilai-nilai melalui objek yang dibuat.



Memang untuk pemula terkadang membingunkan tapi nantinya anda akan memahami sendiri seiring dengan seringnya anda membuat program java.



## Halo Dunia



Program Hello World biasanya digunakan oleh programmer sebagai kode program pertama yang dibuat di berbagai bahasa pemograman. Untuk memulai membuat program Hello World di dalam Java  sebagai berikut :





  * Buka aplikasi editor misal notepad, gedit dll


  * Buat kode program dibawah ini, saya akan mengganti Hello World dengan Halo Dunia, simpan dengan nama ` Halo.java ` . Ingat ekstensinya ` .java `





    public class Halo{   
        public static void main(String[] args){
            System.out.println("Halo dunia");
        }
    }







  * Buka command prompt lalu arahkan ke direktori filenya lalu ketik ` javac Halo.java ` untuk mencompile


  * Jika tidak ada masalah, jalankan programnya dengan perintah ` java Halo `





    Halo Dunia





## Aturan dalam java



Didalam java ada beberapa aturan ketika menulis program  java





  * **Case Sensitive** : Kita tidak boleh salah menempatkan huruf besar dan huruf kecil karena sangat berpengaruh .


  * **Nama Class **: Setiap membuat nama class huruf pertama diawali dengan huruf besar , ini sudah merupakan kebiasaan oleh programmer java seluruh dunia, contoh kita akan membuat class java yang terdiri dari beberapa kata





    public class ProgramPertama { }







  * **Nama Method** : Berbeda dengan nama class , nama method huruf pertama harus diawali dengan huruf kecil, dan selanjutnya kata kedua bisa dengan huruf besar.





    public class ProgramPertama{

      public void iniMethodPertamaku() { }
    }







  * **Nama Program **: Nama file program harus sesuai dengan nama kelas. Contoh nama program dari kelas ` ProgramPertama ` harus disimpan dengan nama file ` ProgramPertama.java ` .


  * **public static void main(String args[])** : Setiap program java yang ingin di Run atau dijalankan,  harus memiliki method ` main() ` . Method ` main() ` berfungsi untuk menjalankan program Java, tanpa method ini program java hanya bisa dicompile tapi tidak bisa dijalankan.





## Identifier



Identifers adalah nama-nama yang bisa dideklarasikan dalam java tetapi bukan bagian keyword java, yang termasuk dalam identifers antara lain: _class, interface, variabel/property_ dan _method._

Tata cara penamaan identifers di java diatur oleh beberapa aturan:





  * Aturan pertama sudah kita bahas sebelumnya adalah semua keyword java tidak boleh digunakan sebagai identifers


  * Identifers harus diawali oleh huruf, simbol mata uang dolar($) atau karakter penghubung underscore (_). Angka tidak boleh digunakan sebagai karakter pertama identifers.


  * Setelah karakter pertama, berikutnya boleh diikuti oleh huruf, simbol mata uang dolar, karakter penghubung, dan angka.


  * Tidak ada pembatasan panjang identifers


  * Identifers di java bersifat case-sensitif, goo dengan Goo adalah dua buah identifers berbeda.


  * Nama public class harus sama persis dengan nama fle .java





## Java Modifiers



Seperti bahasa pemograman lainnya, java mengijinkan  memodifikasi kelas, metode, dll, dengan menggunakan modifiers. Ada dua kategori pengubah:





  * **Access Modifiers: **default, public , protected, private


  * **Non-access Modifiers: **final, abstract, strictfp



Akan dibahas diarticleingan berikutnya



## Java Variables



Tipem variabel dalam java





  * Local Variables


  * Class Variables (Static Variables)


  * Instance Variables (Non-static variables)





## Java Array



Array adalah objek yang menyimpan beberapa variabel dari jenis yang sama. Namun, sebuah array itu sendiri adalah objek. Akan dibahas di tutorial selanjutnya.



## Java Keyword



Berikut macam-macam keyword dalam java

[![Keyword java](http://i713.photobucket.com/albums/ww134/upamisterlobal/1_zpsssxcga4c.png)](http://i713.photobucket.com/albums/ww134/upamisterlobal/1_zpsssxcga4c.png)



## Komentar dalam program java







  * Untuk membuat komentar multi baris gunakan blok ` /* */  `


  * Untuk membuat komentar satu baris gunakan blok ` // `





    /*
    * ini adalah blok komentar
    * multi baris
    */

    public class Halo{
        //ini adalah komentar 1 baris
        public static void main(String[] args){
            System.out.println("Halo dunia");
        }

    }





## Inheritance / Pewarisan



Di  java , class dapat diturunkan ke class anaknya. Pada dasarnya kita hanya perlu untuk membuat class baru yang mewariskan sifat class induknya , maka kita dimungkinkan untuk mewarisi kode yang sudah ada dikelas induknya. Dalam skenario ini class induk yang ada disebut superclass dan kelas turunan disebut subclass.



## Interface



Dalam Java, sebuah interface dapat didefinisikan sebagai alat komunikasi antara objek  dengan satu sama lain. Interface memainkan peran penting ketika datang ke konsep pewarisan. Sebuah interface mendefinisikan metode, yang digunakan oleh class anak (subclass). Namun pelaksanaan metode terserah subclass. Jadi bisa dibilang interface hanya mendefinisikan method tanpa implementasi ,  kemudian class anak lah yang menginplementasikan method tersebut.



## Referensi



Ebook : [Java Desktop - ifnu bima](https://project-template.googlecode.com/files/Java%20Desktop%20-%20Ifnu%20Bima.pdf)

[http://www.tutorialspoint.com/java/java_basic_syntax.htm](http://www.tutorialspoint.com/java/java_basic_syntax.htm)
