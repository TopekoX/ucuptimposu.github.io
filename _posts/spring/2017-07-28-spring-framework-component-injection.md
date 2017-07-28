---
layout: article
title: Spring Framework Component Injection
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
date: 2017-07-28T11:33:48+08:00
---

Pada [tulisan sebelumnya](/spring-framework-component/) kita sudah membuat `component` dalam Spring. Pada tulisan ini kita akan mencoba melakukan Component Injection.

### Membuat Class Component

Kita akan membuat 2 buah class Component

*File : HelloComponentB.java*

```java
package com.timposu.belajarspring.belajarspring.component;

import org.springframework.stereotype.Component;

@Component
public class HelloComponentB {

	public String sayMessage(String message) {
		return message;
	}
}
```

*File : HelloComponentA.java*

```java
package com.timposu.belajarspring.belajarspring.component;

import org.springframework.stereotype.Component;

@Component
public class HelloComponentA {
	
	private HelloComponentB componentB;
		
	public HelloComponentA(HelloComponentB componentB) {
		this.componentB = componentB;
	}

	public void sayMessage() {
		System.out.println(componentB.sayMessage("No Smoking"));
	}
}
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

### SpringConfiguration class

Load component tadi melalui class configuation dengan menggunakan Annotation `@ComponentScan`

*File : SpringConfiguration.java*

```java
package com.timposu.belajarspring.belajarspring;

import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;


@Configuration
@ComponentScan("com.timposu.belajarspring.belajarspring")
public class SpringConfiguration {

}
```

### Class Context

Panggil class Configuration dengan `AnnotationConfigApplicationContext`

*File App.java*

```java
package com.timposu.belajarspring.belajarspring;

import org.springframework.context.ApplicationContext;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;

import com.timposu.belajarspring.belajarspring.component.HelloComponentA;

public class App 
{
    public static void main( String[] args )
    {
    	 ApplicationContext context = 
         		new AnnotationConfigApplicationContext(SpringConfiguration.class);
    	
    	 HelloComponentA helloComponentA = context.getBean(HelloComponentA.class);
    	 helloComponentA.sayMessage();
     }
}
```

### Run

```
No Smoking
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

### Download

![Download](/images/download.png) *Download* : *[BelajarSpringJavaConfig.zip](http://adf.ly/1nbhQc)*
{: .notice-success}

### Video

<iframe width="560" height="315" src="https://www.youtube.com/embed/EnY5pqMP0oc" frameborder="0" allowfullscreen></iframe>

