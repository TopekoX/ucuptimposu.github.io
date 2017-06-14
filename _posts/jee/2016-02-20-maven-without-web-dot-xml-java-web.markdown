---
layout: article
title: "Maven Without web.xml Java Web"
date: 2016-02-20 19:15:08 +0800
comments: true
categories: [jee]
tags: [java, jee, java web, maven]
ads: true
image:
  feature:
  teaser: maven.png
---

![Maven Logo](../images/maven.png)

Semenjak _Servlet Spec_ sudah memasuki versi 3.0 penggunaan `web.xml` di java web sudah bersifat optional, akan tetapi ketika kita menggunakan maven misalnya, saat menjalankan Tomcat server maka maven akan error jika file `web.xml` tidak ada. Untuk mengatasi itu kita tinggal menambahkan kode xml di bawah ini ke dalam file `pom.xml` pada tag `build` :

```xml
<build>
  <plugins>
    <plugin>
	<groupId>org.apache.maven.plugins</groupId>
	<artifactId>maven-war-plugin</artifactId>
	<configuration>
	    <failOnMissingWebXml>false</failOnMissingWebXml>
	</configuration>
    </plugin>
  </plugins>
</build>
```
 <center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>
