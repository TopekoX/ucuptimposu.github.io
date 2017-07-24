---
layout: article
title: Spring Framework - Component
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
date: 2017-07-24T10:46:24-04:00
---

![Spring](/images/spring.png)

Pada tutorial ini kita akan membuat `component`. Pada tutorial Spring sebelumnya kita disibukan dengan membuat bean dalam class Configuration. Sebenarnya kita bisa langsung membuat bean secara otomatis setiap mendefinisikan sebuah class `component` dengan menambahkan annotation `@Component`. Nantinya class tersebut acan dipanggil di dalam class Configuration melalui annotation `@ComponentScan` atau `@ComponentScans`.

### Buat file Component

*File : HelloComponentA.java*

```java
package com.timposu.belajarspring.component;

import org.springframework.stereotype.Component;

@Component
public class HelloComponentA {
	
	private HelloComponentB b;
	
	public HelloComponentA(HelloComponentB b) {
		this.b = b;
	}

	public void sayMessage() {
		System.out.println("Apa kabar dunia???");
	}
}
```

Dengan membuat class `component` diatas kita tidak perlu membuat `bean` pada class Configuration yang perlu di tambahkan cukup annotation `@ComponentScan`.


### Spring Java Config

Disini kita perlu tambahkan annotation `@ComponentScan`, untuk meload package tempat class `component` berada.

```java
package com.timposu.belajarspring;

import org.springframework.beans.factory.annotation.Qualifier;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

import com.timposu.belajarspring.model.HelloB;
import com.timposu.belajarspring.model.HelloC;
import com.timposu.belajarspring.model.HelloA;

@Configuration
@ComponentScan("com.timposu.belajarspring.component") //menambahkan componenscan
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
	
	@Bean
	public HelloC helloC(@Qualifier("ucup") HelloA a, HelloB b) {
		HelloC c = new HelloC(a, b);
		return c;
	}
	
}
```

### Main Class

Panggil class Configuration dengan `AnnotationConfigApplicationContext`

*File App.java*

```java
package com.timposu.belajarspring;

import org.springframework.context.ApplicationContext;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;

import com.timposu.belajarspring.component.HelloComponentA;

public class App 
{
    public static void main( String[] args )
    {
        ApplicationContext context = 
        		new AnnotationConfigApplicationContext(SpringConfiguration.class);
        
//        Hello hello = context.getBean(Hello.class);
//        System.out.println(hello.getMessage());
        
//        HelloB helloB = context.getBean(HelloB.class);
//        System.out.println(helloB.getHello().getMessage());
        
//        HelloC helloC = context.getBean(HelloC.class);
//        System.out.println(helloC.getHelloA().getMessage());
//        System.out.println(helloC.getHelloB().getHello().getMessage());
        
        HelloComponentA hc = context.getBean(HelloComponentA.class);
        hc.sayMessage();
    }
}
```


<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


### Tonton Video

<iframe width="560" height="315" src="https://www.youtube.com/embed/DU-Z88X7wlA" frameborder="0" allowfullscreen></iframe>
