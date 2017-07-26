---
layout: article
title: Contoh Spring Framework Depedency Injection
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
date: 2017-07-09T12:46:24-04:00
---

![Spring](/images/spring.png)

Depedency Injection(DI) adalah fitur yang dibawah oleh spring, nah di tutorial ini kita akan membuat contoh project DI sederhana.

Biar lebih mudah dipahami di bawah ini gambar dimana kita akan membuat 2 buah class yang salah satunya akan di panggil / di inject.

![Depedency Injection](/images/spring/DI.png)

*Gambar : Depedency Injection*

Di tutorial in, kita hanya menyambung [project sebelumnya](/contoh-spring-framework-hello-world-annotation/).

### Class Model

*File : Hello.java*

```java
package com.timposu;

public class Hello {

	private String message;

	public String getmessage() {
		return message;
	}

	public void setMessage(String message) {
		this.message = message;
	}

}
```

Class diatas akan di inject dengan class di bawah ini

*File : DataHello.java*

```java
package com.timposu.belajarspring.model;

public class DataHello {

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

Tambahkan Bean `DataHello`

```java
package com.timposu;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class AppConfig {

	@Bean
	public Hello createHello(){
		Hello hello = new Hello();
		hello.setName("Ucup Timposu");
		return hello;
	}

	@Bean
	public DataHello hello(Hello hello) {
		DataHello dataHello = new DataHello(hello);
		return dataHello;
	}
}
```

Pada method `hello` parameternya akan diinject oleh spring secara otomatis. Spring akan mencari bean yang sesuai dengan tipe parameternya.


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
Halo Ucup Timposu
```

DONE.

### Video

<div style="position:relative;height:0;padding-bottom:75.0%"><iframe src="https://www.youtube.com/embed/9anTdmI17FM?ecver=2" width="480" height="360" frameborder="0" style="position:absolute;width:100%;height:100%;left:0" allowfullscreen></iframe></div>
