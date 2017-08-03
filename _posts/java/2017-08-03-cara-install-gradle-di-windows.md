---
layout: article
title: Cara Install Gradle Di Windows
modified:
categories: java
excerpt:
tags: [java, spring, android, fedora, gradle, eclipse, netbeans, idea]
comments: true
ads: true
image:
  feature:
  teaser: gradlephant.png
  thumb: gradlephant.png
date: 2017-08-03T13:05:33+08:00
---

![Gradle](/images/gradlephant.png)

Sama seperti [Maven](https://maven.apache.org/), [Gradle](https://gradle.org/) adalah aplikasi Build Tool yang sangat populer selain Maven di dalam dunia Java. Gradle digadang-gadang memiliki teknologi yang moderen sehingga banyak programmer yang mempercayakan projectnya ditangani oleh Gradle.

*Baca* [Maven vs Gradle](https://gradle.org/maven-vs-gradle/)

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

Pada postingan sebelumnya kita udah [install Gradle di Fedora](/cara-install-manual-gradle-di-linux-fedora-redhat-centos/) dan kali ini kita akan install di Windows.

Syarat pertama Java harus sudah terinstall

```
>java -version
java version "1.8.0_141"
```

Download Gradle di [https://gradle.org/releases/](https://gradle.org/releases/), contoh versi yang di download `gradle-4.0.2-bin.zip`. Unzip, lalu simpan misal di direktori yang diinginkan misal saya simpan di `C:\gradle-4.0.2`.

Di *File Explorer* klik kanan *This PC* (or *Computer*) icon, lalu klik *Properties -> Advanced System Settings -> Environmental Variables*.

Di *System Variables* pilih *Path*, lalu klik *Edit*. tambahkan `C:\Gradle\gradle-4.0.2\bin`. Klik OK.

![Path Gradle Windows](/images/java/path-gradle-win.png)

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

Cek instalasinya lewat CMD:

```
> gradle -v

------------------------------------------------------------
Gradle 4.0.2
------------------------------------------------------------

Build time:   2017-07-26 15:04:56 UTC
Revision:     108c593aa7b43852f39045337ee84ee1d87c87fd

Groovy:       2.4.11
Ant:          Apache Ant(TM) version 1.9.6 compiled on June 29 2015
JVM:          1.8.0_131 (Oracle Corporation 25.131-b11)
OS:           Windows 7 6.1 amd64
```

### Nonton Video

<iframe width="560" height="315" src="https://www.youtube.com/embed/4npbOirlsVI" frameborder="0" allowfullscreen></iframe>


