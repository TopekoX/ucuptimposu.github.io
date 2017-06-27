---
layout: article
title: Contoh Spring Framework Hello World (Annotation)
modified:
categories: spring
excerpt:
tags: [spring, java, jee, maven]
comments: true
ads: true
image:
  feature:
  teaser: spring.png
  thumb: spring.png
date: 2017-06-26T12:46:24-04:00
---

![Spring](/images/spring.png)

Sejak Spring versi 3, Spring mulai memperkenalkan konfigurasi menggunakan class. Konfigurasi yang sebelumnya dimasukan parameternya ke dalam file xml dapat dipindahkan kedalam Class Configuration.

Cara ini sebenarnya lebih memudahkan dalam melakukan konfigurasi terhadap Spring project akan tetapi kita masih dapat memilih menggunakan xml atau class annotation.

Saya masih akan mengobok-obok program Spring [Hello World](/contoh-spring-framework-hello-world/) yang sudah saya buat sebelumnya, yang saya akan ubah adalah konfigurasi yang sebelumnya melalui `bean.xml` diubah ke dalam class @Annotation.

*XML file*

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

Diganti menjadi Class Configuration

```java
package com.timposu;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class AppConfig {
	
	@Bean(name = "hello")
	public Hello createHello(){
		Hello hello = new Hello();
		hello.setName("Ucup Timposu");
		return hello;
	}	
}
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


## Spring Java Config Hello World

Kita akan melanjutkan project Spring [Hello World](/contoh-spring-framework-hello-world/) sebelumnya.

### Depedency pom.xml

*File : pom.xml*

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
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

### Class Model

*File : Hello.java*

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

### Java Config Annotation

*File : AppConfig.java*

```java
package com.timposu;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class AppConfig {
	
	@Bean(name = "hello")
	public Hello createHello(){
		Hello hello = new Hello();
		hello.setName("Ucup Timposu");
		return hello;
	}
	
}
```

### Main Class

Panggil class Configuration dengan `AnnotationConfigApplicationContext`

*File App.java*

```java
package com.timposu;

import org.springframework.context.ApplicationContext;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;

/*
 * Hello world!
 *
 */
public class App 
{
    public static void main( String[] args )
    {
        ApplicationContext context = new AnnotationConfigApplicationContext(AppConfig.class);
        
        Hello hello = context.getBean(Hello.class);
        System.out.println("Halo " + hello.getName());
    }
}
```

### Struktur Direktori

![Struktur Spring](/images/spring/2.png)

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


### Run

```
Halo Ucup Timposu
```

### Kesimpulan

Dari penggunaan JavaConfig dan XMLConfig terlihat perbedaan penggunaan file XML dan Class @Annotation. Mana yang terbaik? menurut hemat saya sama-sama baik, akan tetapi menggunakan annotation memberikan keuntungan dalam hal kecepatan dalam membuat program. Kita tidak dipusingkan lagi mengingat property yang ada dalam XML ketika mendefinisikan bean, di sisi lain penggunaan annotation di dalam editor IDE memberikan kemudahan karena terdapat suggestion code sehingga mempermudah dalam penulisan kode program. 

Dari itu, di dalam blog ini penggunaan JavaConfig Annoation dalam tutorial Spring akan lebih banyak digunakan.

![Download](/images/download.png) *Download* : *[BelajarSpringJavaConfig.zip](http://adf.ly/1n9bkv)*
{: .notice-success}

