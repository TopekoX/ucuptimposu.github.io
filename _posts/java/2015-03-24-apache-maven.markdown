---
comments: true
date: 2015-03-24 03:54:30+00:00
layout: article
slug: apache-maven
title: Kenalan Sama Apache Maven
categories: java
tags: [java]
ads: true
image:
  feature:
  teaser: java-code.jpg
---

Untuk membuat projek program java untuk skala menengah dan besar, kita pasti membutuhkan library atau framework. Okelah minimal mungkin kita butuh library mysql connector , untuk aplikasi yang berbasis database.. kita mungkin cuma butuh itu. Terus kita mau buat report/laporan untuk aplikasi kita, yah.. kita cuma butuh library dari jasperreport, Oke guys.. sampai fase ini kita mungkin belum menemukan masalah yang berarti.. saat fase ini kita masih bikin project mungkin per individu atau masih kelas mahasiswa.

 <!-- more -->

 Sipp... kita udah mulai beranjak ke project Enterprise,,  tapi mungkin individu atau sendiri bikin projectnya.. mungkin masih tahap belajar,, kita terbiasa pake Netbeans untuk bikin Java GUI.. dan konon katanya untuk bikin project yang Enterprise kebanyakan pakenya Eclipse... yah,, kita sudah harus menguasai 2 IDE atau lebih..(Udah itu resikonya siapa suruh belajar Java)... walaupun di Netbeans sangat bisa bikin aplikasi Enterprise tapi kebanyakan orang lebih memilih Eclise untuk IDE nya karena lebih ringan untuk di jalankan.. apalagi untuk laptop yang spek rendah.. kalo pake Netbeans teriaklah itu laptop ..

Terus hoby yang saya alami.. sering gonta ganti pasangan .. eh salah gonta ganti laptop atau pc untuk menyelesaikan project.. hmmm harus sesuaikan lagi projectnya dari kompi satu ke kompi yang lain edit konfig netbeans lagi.
Terus yang kerja dalam Tim, gimana dong... ada yang suka pake Netbeans ada yang suka Eclipse bisa tidak nyambung projectnya.. FATAL nih.. apalagi kalo kita udah kerja pake framework  Spring atau hibernate yang notabennya juga butuh library yang lain.. terus library yang itu butuh library yang lainnya...dan seterusnya..
Beda project beda toolsnya... beda tujuan dari aplikasi yang kita buat beda library yang dipakai..hmm blum lagi kalo kerja dalam TIM dengan macam - macam jenis laptop/komputer dan beda IDE yang di gunakan...

_Terus Solusinya gmana donk..????_

Untuk mengatasi hal di atas.. Jeng..jeng.. jeng... dibuat lah builder yang namanya Apache Maven, selain Maven ada builder lain yang kita kenal dalam java tapi saya cuma akan bahas Maven (Soalnya yang lain belum pernah saya pelajari :p ). Kelebihan Maven Apa? Ok kita akan bahas..

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

**Kelebihan Menggunakan Maven**





  * Dengan Maven kita cuma akan membuat sebuah project yang bisa di buka banyak IDE. Dengan begitu kita hanya buat satu buah project yang bisa dibuka oleh Netbeans atau Eclipse tanpa masalah.


  * Dengan Maven kita tidak perlu bingung menyusun struktur susunan folder yang ada, karena Maven akan otomatis membuatkannya, berbeda kalo kita buat project di Eclipse atau Netbeans, susunan project akan berbeda antar satu IDE dan IDE yang lain, bahkan terkadang IDE yang sama berbeda susunan foldernya contoh: project Netbeans Java Application berbeda dengan Web Application susunan foldernya padahal masih IDE yang sama.


  * Kita tidak perlu pusing mencari framework atau library yang dibutuhkan karena Mavenlah yang akan mencarikan kita lewat repository nya.. untuk yang satu ini kita butuh koneksi internet.. dan repo itu akan disimpan dalam folde .m2 , proses download nya hanya 1 kali untuk library yang sama.



**INSTALASI**





  1. pastikan JDK udah terinstall


  2. Download [Apache Maven](http://maven.apache.org/) , kemudian extract misal kita extract ke /opt -->Linux atau C:\Program Files -> Windows


  3. Seting CLASSPATH Apache Maven


  4. Masuk ke terminal console untuk mengetahui Maven sudah terinstall





    mvn -version



jika output keluar seperti di bawah ini berarti mvn sudah berhasi terinstall



    Apache Maven 3.2.5 (12a6b3acb947671f09b81f49094c53f426d8cea1; 2014-12-15T01:29:23+08:00)
    Maven home: /opt/apache-maven-3.2.5
    Java version: 1.8.0_31, vendor: Oracle Corporation
    Java home: /usr/java/jdk1.8.0_31/jre
    Default locale: en_US, platform encoding: UTF-8
    OS name: "linux", version: "3.18.7-200.fc21.x86_64", arch: "amd64", family: "unix"


<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

**MEMBUAT PROJECT**

Di Maven membuat project bisa dari terminal console atau lewat Netbeans atau Eclipse.. Pada contoh di artikel ini kita coba lewat Terminal.. Sebelum saya lanjutkan perlu saya tekankan bahwa maven akan secara otomatis akan mendownload paket-2 yang dibutuhkan pada project kita oleh karena itu kita akan membutuhkan koneksi Internet untuk mendownload file-2 yang dibutuhkan.

Kita akan membuat project dengan nama _Belajar-Maven_ dengan paket _com.timposu.maven_



    mvn archetype:create -DgroupId=com.timposu.maven -DartifactId=Belajar-Maven



maka secara otomatis juga maven akan membuat struktur folder project kita

![](http://i68.tinypic.com/1z67blt.jpg)

dan didalam folder tersebut strukturnya kurang lebih seperti gambar di bawah ini:

![](http://i64.tinypic.com/xfdurt.jpg)

dan kita sudah bisa membuka project ini dari netbeans atau eclipse..

**Open Project dengan Netbeans**
Buka Open Project project akan secara otomatis terbaca oleh netbeans

![](http://i66.tinypic.com/10pn6gw.jpg)

**Open Project dengan Eclipse**

Versi Eclipse  yang saya gunakan Eclipse Luna for JEE

_FIle > import > Maven > Exiting Maven Project _pada bagian root directory arahkan ke folder Balajar-Maven

![](http://i68.tinypic.com/14w87lv.jpg)

![](http://i63.tinypic.com/2ekrojn.jpg)

yang perlu diperhatikan adalah file konfigurasi maven yang bernama _pom.xml_ file konfigurasi tersebut disitu kita meletakan semua konfigurasi project kita. Fungsi file ini untuk mendownload dari repository maven yaitu library-library / framework yang dibutuhkan dalam project kita yang untuk selanjutnya disimpan dalam folder **.m2**.

![](http://i67.tinypic.com/qyu35k.jpg)


Contoh saya butuh library mysql-connector saya cukup menambahkan depedencies pada tag <depedencies>


``` xml
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <version>5.1.34</version>
</dependency>
```

![](http://i66.tinypic.com/15q90jq.jpg)


Untuk mengetahui depedencies yang dibutuhkan bisa liat di [http://mvnrepository.com/](http://mvnrepository.com/) setelah menambahkan depedensinya lanjut dengan perintah berikut



    mvn clean install



Maven akan secara otomatis mendownload repository yang dibutuhkan.



## KESIMPULAN



Dengan Maven masalah seperti gonta-ganti IDE sudah terpecahkan karena Maven didukung oleh IDE bersar dalam Java seperti Netbeans dan Eclipse. Masalah kebutuhan paket library dan framework sudah terpecahkan karena kita tidak akan pusing dengan paket yang dibutuhkan oleh project kita.
