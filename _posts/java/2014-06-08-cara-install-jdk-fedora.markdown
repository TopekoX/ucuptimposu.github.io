---
comments: true
date: 2014-06-08 03:29:59+00:00
layout: article
slug: cara-install-jdk-fedora
title: Cara Install Oracle Java JDK di Fedora 21/20, CentOS/RHEL 7/6.6/5.11
categories: java
tags: [java]
ads: true
image:
  feature:
  teaser: java.jpg
---

Secara default biasanya distro besar sudah memaketkan JDK dalam distro mereka yang versi Opensource yang bernama Openjdk. Untuk menginstall JDK Oracle resmi di Fedora 21/20, CentOS/RHEL 7/6.6/5.11 ikuti langkah-langkah berikut.



### 1. Download paket JDK



Untuk menginstall JDK resmi dari Oracle bisa di [download disini](http://www.oracle.com/technetwork/java/javase/downloads/index.html) , download yang versi .rpm dan jenis versi bit sistem anda.



### 2. Login akses root





    su





### 3. Install JDK



sebagai contoh nama paket jdk nya jdk-8u5-linux-xxx.rpm ada di direktori /opt



    ## JDK 32-bit ##
    rpm -Uvh /opt/jdk-8u5-linux-i586.rpm

    ## JDK 64-bit ##
    rpm -Uvh /opt/jdk-8u5-linux-x64.rpm






### 4. Install path java lokasi Java



Agar dikenal di sistem kita pasang link path nya.



    ## java ##
    alternatives --install /usr/bin/java java /usr/java/jdk1.8.0_5/jre/bin/java 200000

    ## Install javac untuk compile##
    alternatives --install /usr/bin/javac javac /usr/java/jdk1.8.0_5/bin/javac 200000
    alternatives --install /usr/bin/jar jar /usr/java/jdk1.8.0_5/bin/jar 200000


    ## javaws (Java Web Start)##
    alternatives --install /usr/bin/javaws javaws /usr/java/jdk1.8.0_5/jre/bin/javaws 200000

    ## Pasang Java Browser (Mozilla) Plugin 32-bit ##
    alternatives --install /usr/lib/mozilla/plugins/libjavaplugin.so libjavaplugin.so /usr/java/jdk1.8.0_5/jre/lib/i386/libnpjp2.so 200000

    ## Java Browser (Mozilla) Plugin 64-bit ##
    alternatives --install /usr/lib64/mozilla/plugins/libjavaplugin.so libjavaplugin.so.x86_64 /usr/java/jdk1.8.0_5/jre/lib/amd64/libnpjp2.so 200000







### 5. Cek





    java -version
    java version "1.8.0_5"
    Java(TM) SE Runtime Environment (build 1.8.0_5-b17)
    Java HotSpot(TM) 64-Bit Server VM (build 5.5-b02, mixed mode)

    javaws
    Java(TM) Web Start 11.5.2.17-fcs
    [...]

    javac -version
    javac 1.8.0_5







### 6. Tukar link path OpenJDK ke JDK



**java**




    alternatives --config java

    There are 4 programs which provide 'java'.

      Selection    Command
    -----------------------------------------------
       1           /usr/java/jdk1.6.0_26/jre/bin/java
       2           /usr/lib/jvm/jre-1.6.0-openjdk/bin/java
       3           /usr/java/jdk1.7.0_55/jre/bin/java
    *+ 4           /usr/java/jdk1.8.0_5/jre/bin/java

    Enter to keep the current selection[+], or type selection number: 4




Catatan:





  * sesuaikan link path JDK anda



  * tanda + adalah yang terpilih






**javac**



    alternatives --config javac

    There are 4 programs which provide 'javac'.

      Selection    Command
    -----------------------------------------------
    *  1           /usr/java/jdk1.6.0_24/bin/javac
     + 2           /usr/java/jdk1.6.0_26/bin/javac
       3           /usr/java/jdk1.7.0_55/bin/javac
       4           /usr/java/jdk1.8.0_5/bin/javac

    Enter to keep the current selection[+], or type selection number: 4




**javaws**



    alternatives --config javaws

    There are 4 programs which provide 'javaws'.

      Selection    Command
    -----------------------------------------------
    *  1           /usr/java/jdk1.6.0_24/jre/bin/javaws
     + 2           /usr/java/jdk1.6.0_26/jre/bin/javaws
       3           /usr/java/jdk1.7.0_55/jre/bin/javaws
       4           /usr/java/jdk1.8.0_5/jre/bin/javaws

    Enter to keep the current selection[+], or type selection number: 4





Catatan:





  * sesuaikan link path JDK anda



  * tanda + adalah yang terpilih






#### libjavaplugin.so (32-bit)





    alternatives --config libjavaplugin.so

    There are 4 programs which provide 'libjavaplugin.so'.

      Selection    Command
    -----------------------------------------------
    *  1           /usr/java/jdk1.6.0_24/jre/lib/i386/libnpjp2.so
     + 2           /usr/java/jdk1.6.0_26/jre/lib/i386/libnpjp2.so
       3           /usr/java/jdk1.7.0_55/jre/lib/i386/libnpjp2.so
       4           /usr/java/jdk1.8.0_5/jre/lib/i386/libnpjp2.so

    Enter to keep the current selection[+], or type selection number: 4








Catatan:





  * sesuaikan link path JDK anda



  * tanda + adalah yang terpilih






#### libjavaplugin.so.x86_64 (64-bit)





    alternatives --config libjavaplugin.so.x86_64

    There are 4 programs which provide 'libjavaplugin.so.x86_64'.

      Selection    Command
    -----------------------------------------------
    *  1           /usr/java/jdk1.6.0_24/jre/lib/amd64/libnpjp2.so
     + 2           /usr/java/jdk1.6.0_26/jre/lib/amd64/libnpjp2.so
       3           /usr/java/jdk1.7.0_55/jre/lib/amd64/libnpjp2.so
       4           /usr/java/jdk1.8.0_5/jre/lib/amd64/libnpjp2.so

    Enter to keep the current selection[+], or type selection number: 4





Catatan:





  * sesuaikan link path JDK anda



  * tanda + adalah yang terpilih






Selesai..



### **CARA CEPAT LINK PATHNYA**



Tambah *JAVA_HOME* variabel environment di **/etc/profile** atau **$HOME/.bash_profile**

Java JDK and JRE latest version (/usr/java/latest)




    ## export JAVA_HOME JDK ##
    export JAVA_HOME="/usr/java/jdk1.8.0_5"
    ## export JAVA_HOME JRE ##
    export JAVA_HOME="/usr/java/jre1.8.0_5"
