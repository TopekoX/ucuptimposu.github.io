---
layout: article
title: Spring Life Cycle
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
date: 2017-08-27T15:18:52+08:00
---

Biasanya dalam menjalankan aplikasi kita menjalankan sesuatu sebelum aplikasi itu di panggil (init) misalnya membuka koneksi ke server dan menjalankan sesuatu ketika aplikasi itu di matikan (destroy) misalnya menutup koneksi ke server.

Didalam spring kita bisa memanfaatkan 2 annotation untuk init dan destroy

* `@PostConstruct` : dipanggil ketika aplikasi mulai dijalankan.
* `@PreDestroy` : dipanggil ketika aplikasi akan dimatikan.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Iklan Responsive -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-4504493660273886"
     data-ad-slot="7129625873"
     data-ad-format="auto"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script></center>

contoh :

*  Buat class service *AppService.java*

```java
package com.timposu.belajarspring.belajarspring.service;

import javax.annotation.PostConstruct;
import javax.annotation.PreDestroy;

import org.springframework.stereotype.Component;

@Component
public class AppService {

	public void message() {
		System.out.println("Hello world");
	}

	@PostConstruct
	public void initApp() {
		System.out.println("Membuka koneksi ke Server !!!");
	}

	@PreDestroy
	public void destroyApp() {
		System.out.println("Menutup koneksi ke Server !!!");
	}
}

```

*  Buat class *App.java* kemudian memanggil `AbstractApplicationContext` untuk di cast karena kita membutuhkan method `registerShutdownHook` agar dapat menampilkan kedalam output destroy.

```java
package com.timposu.belajarspring.belajarspring;

import org.springframework.context.ApplicationContext;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.support.AbstractApplicationContext;

import com.timposu.belajarspring.belajarspring.component.HelloComponentA;
import com.timposu.belajarspring.belajarspring.service.AppService;

public class App
{
    public static void main( String[] args )
    {
    	 ApplicationContext context =
         		new AnnotationConfigApplicationContext(SpringConfiguration.class);

    	 AppService service = context.getBean(AppService.class);
    	 service.message();

    	 ((AbstractApplicationContext) context).registerShutdownHook();
     }
}

```

* Output

![spring cycle](/images/spring/out-spring-cycle.png)

Sebenarnya selain menggunakan cara di atas kita juga bisa mengimplementasikan interfaces `InitializingBean` dan `DisposbleBean`.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- Iklan Responsive -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-4504493660273886"
     data-ad-slot="7129625873"
     data-ad-format="auto"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script></center>

### Referensi

* [www.wideskills.com](http://www.wideskills.com/spring/spring-bean-lifecycle)
* [Tutorialspoint.com](https://www.tutorialspoint.com/spring/spring_bean_life_cycle.htm)
