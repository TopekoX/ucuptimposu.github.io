---
author : Ucup Timposu
layout: article
title: "Cara Kill Aplikasi Desktop di Linux"
date: 2015-12-26 22:59:22 +0800
comments: true
categories: 
- Linux
- Tips & Trik
tags :
- Linux
- Tips & Trik
---

Linux adalah OS yang kuat,..tapi  aplikasi yang terinstall di atasnya belum tentu kuat, apalagi yang berbasis GUI, bisa jadi penyebabnya ada library yang _missing_ atau _corrupt_. Kalau sudah seperti itu biasanya aplikasi itu _frozen_ dan tidak bisa di close. 

![Aplikasi minta di close paksa](http://i64.tinypic.com/ht68n7.jpg "Aplikasinya Crash")


<!-- more --> 

Cara termudah dengan perintah `xkill` lalu pilih window aplikasi yang ingin di kill.

Cara selanjutnya  dengan perintah  `px`, tapi sebelumnya kita harus memasukan nama aplikasi yang ingin di kill contoh aplikasi java, kebetulan android studio saya lagi hang

		ps aux | grep java

outpunya
		

		ucup     3018  1.5  3.3 4521340 129732 ?      Sl   22:04   1:13 java -jar /home/ucup/xdman/xdman.jar
		ucup     4687  4.1  9.6 5007532 370028 ?      Sl   22:52   1:15 /opt/jdk1.8.0_45/bin/java -Xbootclasspath/a:/opt/android-studio/bin/../lib/boot.jar -classpath /opt/android-studio/bin/../lib/bootstrap.jar:/opt/android-studio/bin/../lib/extensions.jar:/opt/android-studio/bin/../lib/util.jar:/opt/android-studio/bin/../lib/jdom.jar:/opt/android-studio/bin/../lib/log4j.jar:/opt/android-studio/bin/../lib/trove4j.jar:/opt/android-studio/bin/../lib/jna.jar:/opt/jdk1.8.0_45/lib/tools.jar -Xms256m -Xmx1280m -XX:MaxPermSize=350m -XX:ReservedCodeCacheSize=225m -XX:+UseConcMarkSweepGC -XX:SoftRefLRUPolicyMSPerMB=50 -da -Djna.nosys=true -Djna.boot.library.path= -Djna.debug_load=true -Djna.debug_load.jna=true -Dsun.io.useCanonCaches=false -Djava.net.preferIPv4Stack=true -Dawt.useSystemAAFontSettings=lcd -Djb.vmOptionsFile=/opt/android-studio/bin/studio64.vmoptions -XX:ErrorFile=/home/ucup/java_error_in_STUDIO_%p.log -Djb.restart.code=88 -Didea.paths.selector=AndroidStudio1.5 -Didea.platform.prefix=AndroidStudio com.intellij.idea.Main
		ucup      5226  0.0  0.0 114332  2204 pts/1    S+   23:22   0:00 grep --color=auto java

Dilihat saja ID pid nya, itu tinggal kita kill. Aplikasi android studio saya ada di ID 4687.
	
		kill 4687


## Referensi :

http://www.howtogeek.com/211153/how-to-kill-a-desktop-application-or-background-process-on-linux/

