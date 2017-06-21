---
layout: article
title: Mengapa Harus Belajar Spring Framework
modified:
categories: spring
excerpt:
tags: [spring, java, jee]
comments: true
ads: true
image:
  feature:
  teaser: spring.png
  thumb: spring.png
date: 2017-06-20T23:23:22-04:00
---

![Spring](/images/spring.png)

Mengapa Spring Framework? Kenapa harus belajar Spring Framework? Kenapa tidak belajar teknologi lain seperti Java Enterprise Edition. Nah pada tulisan kali ini saya mencopy tulisan milik empuh [Eko Kurniawan Khannedy](https://twitter.com/khannedy), yang dia posting di [medium.com](https://medium.com/idspring/mengapa-spring-framework-f3411b5e40ab).

## Spring Framework vs Java Enterprise Edition

Spring Framework sendiri pertama kali dibuat oleh Rod Johnson tahun 2002 sebagai alternatif dari Java Enterprise Edition. Jadi memang Spring Framework secara tidak langsung dibuat sebagai pesaing Java Enterprise Edition. Jika dilihat dari perkembangannya, popularitas Java Enterprise Edition dari hari ke hari semakin menurun dibanding Spring Framework.

Sekarang mari kita bahas, apa hal-hal yang bagus di Spring Framework, sehingga Spring Framework ini sangat penting untuk dipelajari.

### Mature

Spring Framework dibuat sejak tahun 2002, itu artinya udah berumur sekitar 15 tahun (sampai 2017). Dan memang framework ini sudah mature sekali, sudah proven dan sudah tidak bisa dipungkiri, sudah banyak sekali berjalan di aplikasi-aplikasi besar di production.

Rata-rata framework yang sudah uzur biasanya digantikan oleh framework yang baru. Namun berbeda dengan Spring Framework, walaupun framework itu bisa dibilang sudah lama, tapi framework ini tetap selalu menjadi hits di dunia Java. Salah satu asalannya adalah, karena framework ini opensource sehingga semua orang bisa berkontribusi untuk meningkatkan framework Spring.

### Lightweight

Jika dibandingkan dengan Java Enterprise Edition, Spring Framework sangatlah ringan. Kita tidak perlu menunggu puluhan menit untuk restart Enterprise Application hanya untuk mendeploy ulang aplikasi kita. Spring Framework bisa jalan walaupun hanya di aplikasi web server seperti Tomcat atau Jetty.

Bahkan semenjak hadirnya Spring Boot, orang-orang semakin menyukai menggunakan Spring Framework karena web servernya bisa di embed dalam single jar, sehingga untuk menjalankan aplikasinya kita tidak perlu mendeploy ke web server lagi.

Artinya dengan resource hardware yang lebih kecil dan lebih produktif, kita bisa mendapatkan manfaat yang sama, bahkan lebih baik dibandingkan menggunakan Java Enterprise Edition.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Iklan Responsive -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-4504493660273886"
     data-ad-slot="7129625873"
     data-ad-format="auto"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script></center>

### Supported Framework

Spring Framework sebenarnya bukanlah framework untuk menggantikan framework-framework yang lain, justru tujuan utama Spring Framework adalah sebagai fondasi untuk framework-framework yang lain. Spring Framework sendiri mendukung dan didukung oleh framework-framework yang sudah mature lainnya, seperti Hibernate, AspectJ, Bean Validation, JPA, Hystrix, OpenFeign, RxJava dan lain-lain.

Oleh karena itu, saat kita menggunakan Spring Framework sebagai fondasi aplikasi yang akan kita buat, maka akan banyak sekali framework mature yang bisa kita gunakan dengan mudah, bahkan kita juga bisa dengan mudah mengintegrasikan framework lain secara manual.

### Backward Compatible

Hal yang patut diacungi jempol dari Spring Framework adalah, *backward compatible*. Sejak pertama kali Spring Framework rilis menggunakan konfigurasi XML sampai sekarang yang lebih popular menjadi konfigurasi Annotation. Spring Framework selalu *backward compatible*.

Walaupun umurnya yang sudah terbilang lama, tapi karena dari awal desain API Spring Framework sangat bagus, dia selalu bisa menjaga backward compatible, bandingkan dengan framework seperti Play Framework (tiap ganti versi, selalu rewrite framework) atau framework-framework yang lainnya.

### Good API Design

Coba sekali-kali Anda clone project Spring Framework, lalu obok-obok source code nya. Anda akan lihat kalo API Design Spring Framework sangatlah bagus. Dia sangat mudah untuk di extends, bahkan jika kita ingin mengintegrasikan framework lain, itupun sangat mudah.

### Spring Ecosystem

Spring Framework adalah fondasi dari Spring Ecosystem-nya. Pernah dengar tentang Spring Boot? Spring Cloud? dan Spring Data? Yup, itu adalah framework-framework lain yang di develop diluar core Spring Framework nya itu sendiri.
Saat ini dari Spring Framework, sudah banyak dikembangkan framework pendukung lainnya seperti yang bisa dilihat di halaman [https://spring.io/projects](https://spring.io/projects). Sehingga menggunakan Spring Framework, akan mempermudah lagi dalam membuat aplikasi, saat ini yang menurut saya sangat membantu sekali adalah Spring Boot, Spring Data dan Spring Cloud.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Iklan Responsive -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-4504493660273886"
     data-ad-slot="7129625873"
     data-ad-format="auto"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script></center>

Masih banyak framework-framework pendukung ekosistem Spring lainnya seperti Spring Session, Spring Mobile, Spring Security, Spring Batch, Spring Stream dan lain-lain.

### The Bad Part

Memang tidak ada semua framework yang tidak memiliki kekurangan, begitu juga dengan Spring Framework.

### No Standard

Berbeda dengan Java Enterprise Edition yang dibuat standarisasinya. Spring Framework tidak memiliki standard. Jika kita develop aplikasi sesuai spesifikasi Java Enterprise Edition, biasanya kita bisa dengan mudah ganti Application Server-nya, misal JBoss, Glassfish, Webspere dan lain-lain.

Tapi tidak dengan Spring Framework, karena memang Spring Framework itu tidak memiliki standard, jadi sekali kita menggunakan Spring, maka selamanya aplikasi kita harus menggunakan Spring. Jika ingin ganti teknologi, maka kita harus rewrite lagi aplikasi kita.

### Fast Updates.

Jika diperhatikan update Java Enterprise Edition itu rentannya sekitar 3–5 tahun sekali. Tapi kalo Spring Framework? Bisa jadi tiap hari selalu ada update terbaru.
Jadi dengan menggunakan Spring Framework, berarti Anda harus sudah menerima kalo Anda selalu harus selalu update informasi seputar Spring Framework, karena mungkin tiap hari akan ada update Spring Framework terbaru.

Tapi tidak perlu khawatir, karena perubahan terbaru Spring Framework tidak akan mem-break fitur yang telah berjalan.

### Spring Framework di Indonesia
Sekarang pertanyaannya, apakah setimpal belajar Spring Framewok, terutama di Indonesia. Oke, percaya atau tidak, saat ini di Indonesia, hampir semua lowongan kerja untuk Java Engineer selalu mensyaratkan menguasai Spring Framework.

Jadi apakah setimpal belajar Spring Framework? Yup sudah pasti, terutama untuk Java Engineer.

Sumber : [medium.com](https://medium.com/idspring/mengapa-spring-framework-f3411b5e40ab)