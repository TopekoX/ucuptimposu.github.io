---
layout: article
title: Contoh Maven + Spring Framework Hello World (XML)
modified:
categories: spring
tags: [spring, java, jee, maven]
comments: true
ads: true
image:
  feature:
  teaser: spring.png
  thumb: spring.png
date: 2017-06-26T10:12:38-04:00
---

![Hibernate](/images/spring.png)

Ditutorial kali ini, kita akan membuat project Spring sederhana Hello World. 

Teknologi yang digunakan:

```
1. Spring 4.3.9
2. Maven 3.5.0
3. JDK 1.8
4. Eclipse (IDE lain menyesuaikan)
```

## Generate Project dengan Maven

Setiap ingin membuat project Spring saya menyarankan mengenerate dengan Maven atau Grandle, walau setiap IDE modern saat ini sudah menyediakan struktur project sendiri ketika kita membuat project Spring, akan tetapi menggunakan Maven lebih menyenangkan karena bisa diimport di berbagai IDE.

**Baca Juga:** 
[Cara membuat project Java dengan maven](/cara-membuat-project-java-dengan-maven/)
{: .notice-success}

**Generate Project**

```
mvn archetype:generate -DgroupId=com.timposu -DartifactId=BelajarSpring -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

## Convert ke Eclipse Project

Karena disini saya menggunakan Eclipse jadi perlu saya convert project terlebih dahulu.

```
mvn eclipse:eclipse
```

## Import project

Dari Eclipse pilih File –> Import –> General folder, Existing Projects into Workspace –>pilih lokasi project folder . Done

## Add Depedency

Tambahkan depedency Spring 4 ke dalam `pom.xml`, untuk mendownload dependency Spring via Maven Central Repository.

```xml
<dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-context</artifactId>
        <version>4.3.9.RELEASE</version>
</dependency>
```

Sehingga menjadi

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

*pom.xml*

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" 
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.timposu</groupId>
  <artifactId>BelajarSpring</artifactId>
  <packaging>jar</packaging>
  <version>1.0-SNAPSHOT</version>
  <name>BelajarSpring</name>
  <url>http://maven.apache.org</url>
  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>3.8.1</version>
      <scope>test</scope>
    </dependency>
    
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-context</artifactId>
        <version>4.3.9.RELEASE</version>
    </dependency>
    
  </dependencies>
</project>
```

## Class Bean Hello

Buat sebuah class sederhana *Hello.java*

```java
package com.timposu;

public class Hello {
	
	private String name;

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

}
```

##  Bean Configuration

Buat sebuah file configuration dengan nama `Bean.xml` (nama terserah) kedalam folder `resources` (jika belum ada, silahkan buat dulu) 

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="hello" class="com.timposu.Hello">
        <property name="name" value="Ucup Timposu"></property>
    </bean>

</beans>
```

**Info:** 
Spring Configuration di bagi menjadi 2, yaitu XML (jadul) dan Annotation (sejak JDK versi 1.5)
{: .notice-info}

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## Struktur Project

Struktur file akhir sebagai berikut:

![Struktur Spring](/images/spring/1.png)

## Main Class

Edit `App.java`

```java
package com.timposu;

import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

/**
 * Hello world!
 *
 */
public class App 
{
    public static void main( String[] args )
    {
        ApplicationContext context = new ClassPathXmlApplicationContext("Bean.xml");
        
        Hello hello = (Hello) context.getBean("hello");
        System.out.println("Halo " + hello.getName());
    }
}
```

## Output

```
Halo Ucup Timposu
```

## Referensi

[http://docs.spring.io/](http://docs.spring.io/spring/docs/current/spring-framework-reference/htmlsingle/#beans)


