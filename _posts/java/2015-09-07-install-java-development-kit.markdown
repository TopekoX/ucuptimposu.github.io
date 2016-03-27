---
comments: true
date: 2015-09-07 06:41:03+00:00
layout: article
slug: install-java-development-kit
title: Java - Install Java Development Kit
categories: java
tags: [java]
ads: true
image:
  feature:
  teaser: java.jpg
---

Untuk membuat program Java dibutuhkan setidaknya perangkat lunak diantaranya


  1. Java Development Kit (JDK) merupakan perangkat lunak yang digunakan untuk melakukan _compile_ dari kode java menjadi _bytecode_ yang dapat di jalankan oleh Java Runtime Environtment.


  2. Java Runtime Environtment (JRE) merupakan perangkat lunak yang digunakan untuk menjalanka program yang dibuat dengan Java


  3. Editor = editor adalah tempat menulis kode Java



Di dalam JDK sudah terdapat JRE jadi kalo mau membuat program kita cukup mendownload JDK.<!-- more -->



# Download



Untuk melakukan programming dalam Java kita mebutuhkan software JDK (_Java Development Kit_) yang bisa didownload secara gratis di [sini](http://www.oracle.com/technetwork/java/javase/downloads/index.html) , pastikan versi JDK yang didownload sesuai dengan versi Sistem Operasi anda. Download yang .exe untuk windows, .rpm untuk linux berbasis Redhat dan .tar.gz untuk Linux umum dan .dmg untuk Mac OS.



#  Install



Cara install JDK sama seperti dengan aplikasi lainnya.. jika di Windows anda cukup mengklik filenya dan ikuti petunjuknya, jika di Linux disesuaikan dengan distronya, untuk rpm langsung install dengan perintah `rpm -Uvh jdk_xxx.rpm` atau bisa lihat [disini](/blog/2014/06/08/cara-install-jdk-fedora/) , untuk Linux lain format  tar.gz bisa merujuk [ke sini](/blog/2015/08/05/install-oracle-jdk-di-kali-linux/) , untuk Mac OS format .dmg langsung klik saja.



# Setting path di windows



Pastikan JDK sudah terinstall :





  * Klik kanan **'My Computer'** dan pilih **'Properties'**.


  * Klik **'Environment variables'** di dalam tab **'Advanced'**.


  * Didalam kolom tabel cari nama baris **'Path'**  lalu tambahkan lokasi Path JDK ingat TAMBAHKAN bukan diganti, karena akan menghapus Path yang terlebih dahulu terpasang. Contoh variabel yang ada _'C:\WINDOWS\SYSTEM32'_, tambahkan path JDK sehingga menjadi _'C:\WINDOWS\SYSTEM32;c:\Program Files\java\jdk1.8.xxx\bin'_.





# Setting di Linux, UNIX, Solaris, FreeBSD:



Sebenarnya saya tidak perlu memberi tahu cara setting Environment variable PATH di sistem Unix dkk, karena anak-anak Unix/Linux dkk, ini biasanya suka ngotak atik sistem unix , bids di bilsng pintar-pintar lah #eaaaa, tapi secara garis besar nya aja cara setting Path : Contoh path Java kita di **/opt/jdkxxxx/bin**. Tinggal di tambahkan aja kedalam file _.bashrc_ tambahkan ke baris paling bawah _'.bashrc: export PATH=/path/to/java:$PATH'._



# Cek



Untuk mengetahui Java sudah terinstall dengan baik.. ketik perintah di bawah ini kedalam command prompt atau di shell

Ketik `java -version` jika keluaran seperti contoh di bawah ini berarti java sudah terinstall.



    root@timposu:~# java -version
    java version "1.8.0_45"
    Java(TM) SE Runtime Environment (build 1.8.0_45-b14)
    Java HotSpot(TM) 64-Bit Server VM (build 25.45-b02, mixed mode)



ketik lagi `javac -version` jika keluaran seperti dibawah ini .. berarti kita sudah bisa koding java :D



    root@timposu:~# javac -version
    javac 1.8.0_45





# Editor Java



Java kaya akan editor .. tanpa mendownload editor pun kita sebenarnya bisa membuat program Java, bila di Windows kita bisa pake notepad , di linux apalagi bisa pake gedit, nano, vi dll. Tapi  ada yang namanya _Integrated Development Environment _(IDE). Haa....... tool ini dibuat untuk mempermudah kita membuat program didalam Java, jadi intinya di dalam IDE ini udah komplit dah udah ada editonya, compilernya dan tool-tool lain yang dibutuhkan dalam membuat program. Beberapa IDE yang terkenal untuk pemograman Java:





  * Netbeans : IDE ini adalah IDE yang dikeluarkan oleh yang punya Java yaitu Oracle, download di. [https://netbeans.org/ ](https://netbeans.org/)


  * Eclipse : IDE open-source community dapat di download di [http://www.eclipse.org/](http://www.eclipse.org/)


  * IntelliJ IDEA : IDE ini punya 2 versi yang pro dan community. IDE ini juga resmi jadi IDE untuk pengembangan Aplikasi Android namanya Android Studio download Intellij IDEA [https://www.jetbrains.com/](https://www.jetbrains.com/)



Mau pake yang mana? terserah anda dong.. pake notepad pun bisa...

Sampai disini dulu tutorial installasi Java di berbagai OS.. ada banyak referensi di internet untuk menginstall java...
