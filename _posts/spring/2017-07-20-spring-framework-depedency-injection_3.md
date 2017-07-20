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

Class diatas akan di inject dengan class `HelloB` di bawah ini

*File : DataHello.java*

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

        DataHello dataHello = context.getBean(DataHello.class);
        System.out.println(dataHello.getHello().getMessage());
    }
}
```


<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


### Run

```
Halo Timposu
```

DONE.

### Tonton Video

<iframe width="560" height="315" src="https://www.youtube.com/embed/ZNFe8u4CxdM" frameborder="0" allowfullscreen></iframe>
