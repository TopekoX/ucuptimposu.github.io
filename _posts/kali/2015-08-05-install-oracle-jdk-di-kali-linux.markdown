---
comments: true
date: 2015-08-05 01:32:51+00:00
layout: article
slug: install-oracle-jdk-di-kali-linux
title: Install Oracle JDK di Ubuntu, Debian, Kali Linux
categories: kali
tags: [kali, linux, java, debian, ubuntu]
ads: true
image:
  feature: 
  teaser: kali_linux_wallpaper_by_lukazoid-d800c86.png
---

Secara default java sebenarnya udah terinstall di Kali .. tapi yang versi OpenJDK, buat yang mau ganti ke versi resmi Oracle ikuti langkah berikut... cara ini juga bisa berjalan di ubuntu 14.04( udah di coba).Download dulu jdk nya di [http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html) download yang tar.gz


    
    tar -xzvf /root/jdk-8u45-linux-x64.tar.gz
    mv jdk1.8.0_45 /opt
    cd /opt/jdk1.8.0_45



Register binaries ..biar dibaca sistem


    
    update-alternatives --install /usr/bin/java java /opt/jdk1.8.0_45/bin/java 1
    update-alternatives --install /usr/bin/javac javac /opt/jdk1.8.0_45/bin/javac 1
    update-alternatives --install /usr/lib/mozilla/plugins/libjavaplugin.so mozilla-javaplugin.so /opt/jdk1.8.0_45/jre/lib/amd64/libnpjp2.so 1
    update-alternatives --set java /opt/jdk1.8.0_45/bin/java
    update-alternatives --set javac /opt/jdk1.8.0_45/bin/javac
    update-alternatives --set mozilla-javaplugin.so /opt/jdk1.8.0_45/jre/lib/amd64/libnpjp2.so



<!-- more -->Cek


    
    java -version

	javac -version


