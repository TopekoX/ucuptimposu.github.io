---
layout: article
title: Spring Framework Depedency Injection Bag 2
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
date: 2017-07-20T12:46:24-04:00
---

![Spring](/images/spring.png)

Di tutorial sebelumnya kita sudah membuat program sederhana [Depedency Injection](/contoh-spring-framework-depedency-injection/).

Pada tutorial ini kita akan menyambung project sebelumnya dengan menambahkan sebuah bean baru

Di tutorial in, kita hanya menyambung [project sebelumnya](/contoh-spring-framework-hello-world-annotation/).

Saya rename 2 class model dengan nama `HelloA` dan `HelloB`.

### Class Model

*File : HelloA.java*

```java
package com.timposu;

public class HelloA {

	private String message;

	public String getmessage() {
		return message;
	}

	public void setMessage(String message) {
		this.message = message;
	}

}
```

Class diatas akan di inject dengan class `HelloB` di bawah ini

*File : HelloB.java*

```java
package com.timposu.belajarspring.model;

public class HelloB {

	private Hello hello; //memanggil class Hello

	public DataHello(Hello hello) {
		super();
		this.hello = hello;
	}

	public Hello getHello() {
		return hello;
	}

	public void setHello(Hello hello) {
		this.hello = hello;
	}

}
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


### Spring Java Config Hello World

Di Bagian class config kita Bean `HelloB` akan memanggil bean `HelloA` akan tetapi karena bean `HelloA` ada 2 makan kita perlu memberikan `name` ke setiap bean `HelloA` yang akan kita buat yang nantinya akan dipanggil oleh Bean `HelloB` menggunakan Annotation `@Qualifier`.

Disini saya kasi nama kedua bean tersebut dengan nama `"Ucup"` dan `"Timposu"`.

```java
package com.timposu.belajarspring;

import org.springframework.beans.factory.annotation.Qualifier;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

import com.timposu.belajarspring.model.HelloB;
import com.timposu.belajarspring.model.HelloA;

@Configuration
public class SpringConfiguration {
	
	@Bean(name = "ucup")
	public HelloA sayHello1() {
		HelloA hello = new HelloA();
		hello.setMessage("Ucup");
		return hello;
	}
	
	@Bean(name = "timposu")
	public HelloA sayHello2() {
		HelloA hello = new HelloA();
		hello.setMessage("Timposu");
		return hello;
	}
	
	@Bean
	public HelloB hello(@Qualifier("timposu") HelloA hello) {
		HelloB helloB = new HelloB(hello);
		return helloB;
	}
	
}
```

### Main Class

Panggil class Configuration dengan `AnnotationConfigApplicationContext`

*File App.java*

```java
package com.timposu.belajarspring.belajarspring;

import org.springframework.context.ApplicationContext;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;

import com.timposu.belajarspring.belajarspring.model.HelloB;

public class App 
{
    public static void main( String[] args )
    {
    	 ApplicationContext context = 
         		new AnnotationConfigApplicationContext(SpringConfiguration.class);
    	 
    	 HelloB helloB = context.getBean(HelloB.class);
         System.out.println("Bean yang dipanggil " + helloB.getHello().getMessage());
    }
}

```


<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


### Run

```
Bean yang dipanggil Timposu
```

DONE.

### Download

![Download](/images/download.png) *Download* : *[BelajarSpringDI2.zip](http://adf.ly/1nbfi6)*
{: .notice-success}


### Tonton Video

<iframe width="560" height="315" src="https://www.youtube.com/embed/ZNFe8u4CxdM" frameborder="0" allowfullscreen></iframe>
