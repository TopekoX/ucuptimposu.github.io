---
layout: article
title: Cara Install Manual Gradle Di Linux Fedora, Redhat, Centos
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
date: 2017-08-02T22:18:40+08:00
---

![Gradle](/images/gradlephant.png)

Sama seperti [Maven](https://maven.apache.org/), [Gradle](https://gradle.org/) adalah aplikasi Build Tool yang sangat populer selain Maven di dalam dunia Java. Gradle digadang-gadang memiliki teknologi yang moderen sehingga banyak programmer yang mempercayakan projectnya ditangani oleh Gradle.

*Baca* [Maven vs Gradle](https://gradle.org/maven-vs-gradle/)

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

Pada postingan kali ini kita akan menngistall Gradle secara manual di Redhat base OS, misalnya Fedora, Centos maupun Redhat.

Syarat pertama Java harus sudah terinstall ([Cara Install Java](cara-install-jdk-fedora/))

```
$ java -version
java version "1.8.0_141"
```

Download Gradle di [https://gradle.org/releases/](https://gradle.org/releases/), contoh versi yang di download `gradle-4.0.2-bin.zip`. Unzip, lalu simpan misal di dalam `/opt`, lalu daftarkan kedalam sistem pathnya melalui command `alternatives` :

```
$ sudo alternatives --install /usr/bin/gradle gradle /opt/gradle-4.0.2/bin/ 200000
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


Cek instalasinya :

```
$ gradle -v

------------------------------------------------------------
Gradle 4.0.2
------------------------------------------------------------

Build time:   2017-07-26 15:04:56 UTC
Revision:     108c593aa7b43852f39045337ee84ee1d87c87fd

Groovy:       2.4.11
Ant:          Apache Ant(TM) version 1.9.6 compiled on June 29 2015
JVM:          1.8.0_141 (Oracle Corporation 25.141-b15)
OS:           Linux 4.11.11-300.fc26.x86_64 amd64
```

### Tonton Video

<iframe width="560" height="315" src="https://www.youtube.com/embed/85nQHyPZGCk" frameborder="0" allowfullscreen></iframe>

#### Referensi

[gradle.org/install](https://gradle.org/install/#install)
