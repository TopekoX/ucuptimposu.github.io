---
layout: article
title: Membuat Aplikasi Maven + Hibernate + MySql CRUD (Annotation)
modified:
categories: hibernate
excerpt:
tags: [hibernate, java, database]
comments: true
ads: true
image:
  feature:
  teaser: hibernate.png
  thumb: hibernate.png
date: 2017-06-17T17:32:09-04:00
---

![Hibernate](/images/hibernate.png)

Di tutorial ini kita akan membuat project Hibernate dengan menggunakan Maven untuk generate projectnya, dan Hibernate untuk CRUD data ke MySQL atau MariaDB. Tutorial ini modifikasi dari [Membuat Aplikasi Maven + Hibernate + MySql CRUD (XML Mapping)](/contoh-projet-maven-hibernate-mysql-xml-mapping/)

**Info:** 
Hibernate mapping di bagi menjadi 2, yaitu mapping XML (klasik) dan mapping Annotation (sejak Hibernate versi 3.5)
{: .notice-info}

Teknologi yang digunakan :

```
1. Maven 3.5.0
2. JDK 1.8.0_45
3. Hibernate 5.2.10
4. MySQL 5.7 atau MariaDB 10.1.24
```

## Generate project dengan Maven

Buat project seperti yang ada pada tutorial [Membuat Aplikasi Maven + Hibernate + MySql CRUD (XML Mapping)](/contoh-projet-maven-hibernate-mysql-xml-mapping/)

**Baca Juga:** 
[Cara membuat project Java dengan maven](/cara-membuat-project-java-dengan-maven/)
{: .notice-success}

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


## Struktur Project

![strukturhibernate](/images/hibernate/strukturhibernate.png)

## Menambahkan depedency Hibernate, MySQL

Edit maven `pom.xml` tambahkan depedency hibernate dan MySQL

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" 
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.timposu</groupId>
  <artifactId>BelajarHibernate</artifactId>
  <packaging>jar</packaging>
  <version>1.0-SNAPSHOT</version>
  <name>BelajarHibernate</name>
  <url>http://maven.apache.org</url>
  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>3.8.1</version>
      <scope>test</scope>
    </dependency>
    
    <!-- MySql Driver -->
	<dependency>
		<groupId>mysql</groupId>
		<artifactId>mysql-connector-java</artifactId>
		<version>5.1.9</version>
	</dependency>
	
	<!-- Hibernate framework -->
    	<dependency>
	    <groupId>org.hibernate</groupId>
	    <artifactId>hibernate-core</artifactId>
	    <version>5.2.10.Final</version>
	</dependency>
	
  </dependencies>
</project>
```

Maven nantinya akan secara otomatis mendownload depedency yang dibutuhkan.

## Buat Hibernate Mapping file, Model Class dan Class Util

Kita akan mapping class, tapi sebelumnya kita buat dulu class model Person.

Buat package `com.timposu.model`

*File : Person.java*

```java
package com.timposu.model;

import java.io.Serializable;

import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.Table;

@Entity
@Table(name = "person")
public class Person implements Serializable{

	private static final long serialVersionUID = 1L;
	
	public Person(String namaDepan, String namaBelakang, String alamat) {
		super();
		this.namaDepan = namaDepan;
		this.namaBelakang = namaBelakang;
		this.alamat = alamat;
	}

	@Id
	@GeneratedValue(strategy = GenerationType.IDENTITY)
	@Column(name = "id")
	private Integer id;

	@Column(name = "NamaDepan")
	private String namaDepan;
	
	@Column(name = "NamaBelakang")
	private String namaBelakang;

	@Column(name = "Alamat")
	private String alamat;
	
	public Person() {
	}

	public Integer getId() {
		return id;
	}

	public void setId(Integer id) {
		this.id = id;
	}

	public String getNamaDepan() {
		return namaDepan;
	}

	public void setNamaDepan(String namaDepan) {
		this.namaDepan = namaDepan;
	}

	public String getNamaBelakang() {
		return namaBelakang;
	}

	public void setNamaBelakang(String namaBelakang) {
		this.namaBelakang = namaBelakang;
	}
	
	public String getAlamat() {
		return alamat;
	}

	public void setAlamat(String alamat) {
		this.alamat = alamat;
	}

}
```

Buat class mapping kedalam package `com.timposu.util`

*File : PersonUtil.java*

```java
package com.timposu.util;

import org.hibernate.SessionFactory;
import org.hibernate.boot.Metadata;
import org.hibernate.boot.MetadataSources;
import org.hibernate.boot.registry.StandardServiceRegistry;
import org.hibernate.boot.registry.StandardServiceRegistryBuilder;

public class PersonUtil {

	private static SessionFactory sessionFactory;
		
	static{
		try{
			StandardServiceRegistry standardRegistry = 
					new StandardServiceRegistryBuilder().configure("hibernate.cfg.xml").build();
			Metadata metadata = new MetadataSources(standardRegistry).getMetadataBuilder().build();
			sessionFactory = metadata.getSessionFactoryBuilder().build();
		}catch (Exception e) {
			System.err.println("Enitial SessionFactory creation failed" + e);
			throw new ExceptionInInitializerError(e);
		}
	}
	
	public static SessionFactory getSessionFactory() {
		return sessionFactory;
	}
}
```

## Buat Hibernate Configuration

Buat file konfigurasi hibernate dan letakkan di folder, `src/main/resources/hibernate.cfg.xml`. Sesuaikan parameternya dengan server MySQL anda.

```xml
<?xml version='1.0' encoding='utf-8'?>
<!DOCTYPE hibernate-configuration PUBLIC
"-//Hibernate/Hibernate Configuration DTD//EN"
"http://hibernate.sourceforge.net/hibernate-configuration-5.0.dtd">

<hibernate-configuration>
   <session-factory>
	   <property name="hibernate.dialect">org.hibernate.dialect.MySQL5Dialect</property>
	   <property name="hibernate.connection.driver_class">com.mysql.jdbc.Driver</property>
	   <property name="hibernate.connection.url">jdbc:mysql://localhost/belajarhibernate</property>
	   <property name="hibernate.connection.username">root</property>
	   <property name="hibernate.show_sql">true</property>
	   <property name="hibernate.format_sql">true</property>
	   <property name="hibernate.connection.password">xxxxxx</property>
	   <property name="hbm2ddl.auto">create</property>
	   
	   <!-- List of class mapping files -->
	   <mapping class="com.timposu.model.Person"/>

</session-factory>
</hibernate-configuration>
```

Perbedaan antara xml dan annotation pada hibernate configuration ada pada tag `<mapping>`

```xml
<mapping resource="Pegawai.hbm.xml"></mapping>
```

ganti dengan

```xml
<mapping class="com.timposu.model.Person"></mapping>
```

## Buat service class CRUD

Class ini buat membuat service CRUD ke MySQL. Tapi sebelumnya biar rapi kita buat package `com.timposu.service`

*File : PersonService.java*

```java
package com.timposu.service;

import java.util.Iterator;
import java.util.List;

import org.hibernate.HibernateException;
import org.hibernate.Session;
import org.hibernate.SessionFactory;
import org.hibernate.Transaction;

import com.timposu.model.Person;


public class PersonService {
private SessionFactory factory;
	
	public PersonService(SessionFactory factory) {
		super();
		this.factory = factory;
	}

	public Integer addPerson(String namaDepan, String namaBelakang, String alamat){
	      Session session = factory.openSession();
	      Transaction tx = null;
	      Integer personID = null;
	      try{
	         tx = session.beginTransaction();
	         Person person = new Person(namaDepan, namaBelakang, alamat);
	         personID = (Integer) session.save(person); 
	         tx.commit();
	      }catch (HibernateException e) {
	         if (tx!=null) tx.rollback();
	         e.printStackTrace(); 
	      }finally {
	         session.close(); 
	      }
	      return personID;
	   }
	
	public void listPerson(){
	      Session session = factory.openSession();
	      Transaction tx = null;
	      try{
	         tx = session.beginTransaction();
	         List persons = session.createQuery("FROM Person").list(); 
	         for (Iterator iterator = 
	                           persons.iterator(); iterator.hasNext();){
	            Person person = (Person) iterator.next(); 
	            System.out.print("Nama Depan: " + person.getNamaDepan()); 
	            System.out.print("  Nama Belakang: " + person.getNamaBelakang()); 
	            System.out.println("  Alamat: " + person.getAlamat()); 
	         }
	         tx.commit();
	      }catch (HibernateException e) {
	         if (tx!=null) tx.rollback();
	         e.printStackTrace(); 
	      }finally {
	         session.close(); 
	      }
	   }
	
	public void updatePerson(Integer IdPerson, String alamat){
	      Session session = factory.openSession();
	      Transaction tx = null;
	      try{
	         tx = session.beginTransaction();
	         Person person = 
	                    (Person)session.get(Person.class, IdPerson); 
	         person.setAlamat(alamat);
			 session.update(person); 
	         tx.commit();
	      }catch (HibernateException e) {
	         if (tx!=null) tx.rollback();
	         e.printStackTrace(); 
	      }finally {
	         session.close(); 
	      }
	   }
	
	public void deletePerson(Integer IdPerson){
	      Session session = factory.openSession();
	      Transaction tx = null;
	      try{
	         tx = session.beginTransaction();
	         Person person = 
	                   (Person)session.get(Person.class, IdPerson); 
	         session.delete(person); 
	         tx.commit();
	      }catch (HibernateException e) {
	         if (tx!=null) tx.rollback();
	         e.printStackTrace(); 
	      }finally {
	         session.close(); 
	      }
	   }
}

```

## Main Class

Ubah `App.java` untuk data CRUD nya

```java
package com.timposu;

import org.hibernate.SessionFactory;

import com.timposu.service.PersonService;
import com.timposu.util.PersonUtil;

public class App 
{
	// buat session
    private static SessionFactory factory;
    
    public static void main( String[] args )
    {   
        try{
        	factory = new PersonUtil().getSessionFactory();
        }catch (Exception e) {
        	System.err.println("Gagal membuat sessionFactory object." + e); 
		}
        
      //buat service
		  PersonService SP = new PersonService(factory);

		  //tambah person & mengembalikan id personnya
	      Integer person1 = SP.addPerson("Ferry", "Gunawan", "Banda Aceh");
	      Integer person2 = SP.addPerson("Fiannur", "Yusmita", "Pontianak");
	      Integer person3 = SP.addPerson("Danu", "Wirnoyo", "Bekasi");

	      //daftar person
	      SP.listPerson();
	      
	      //update data
	      SP.updatePerson(person3, "Citayam");
	      
	      //daftar person
	      SP.listPerson();
	       
	      //hapus person ke 2
	      SP.deletePerson(person2);

	      //daftar person
	      SP.listPerson();
        
    }
}
```


## Struktur folder akhir

![strukturhibernate](/images/hibernate/struktur3.png)

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


## Running

Disini saya running lewat command prompt mengunakan Maven

```
$ mvn clean package exec:java -Dexec.mainClass=m.timposu.App
....
Hibernate: 
    insert 
    into
        person
        (Alamat, NamaBelakang, NamaDepan) 
    values
        (?, ?, ?)
Hibernate: 
    insert 
    into
        person
        (Alamat, NamaBelakang, NamaDepan) 
    values
        (?, ?, ?)
Hibernate: 
    insert 
    into
        person
        (Alamat, NamaBelakang, NamaDepan) 
    values
        (?, ?, ?)
Jun 17, 2017 5:29:37 PM org.hibernate.hql.internal.QueryTranslatorFactoryInitiator initiateService
INFO: HHH000397: Using ASTQueryTranslatorFactory
Hibernate: 
    select
        person0_.id as id1_0_,
        person0_.Alamat as Alamat2_0_,
        person0_.NamaBelakang as NamaBela3_0_,
        person0_.NamaDepan as NamaDepa4_0_ 
    from
        person person0_
Nama Depan: Ferry  Nama Belakang: Gunawan  Alamat: Banda Aceh
Nama Depan: Fiannur  Nama Belakang: Yusmita  Alamat: Pontianak
Nama Depan: Danu  Nama Belakang: Wirnoyo  Alamat: Bekasi
Hibernate: 
    select
        person0_.id as id1_0_0_,
        person0_.Alamat as Alamat2_0_0_,
        person0_.NamaBelakang as NamaBela3_0_0_,
        person0_.NamaDepan as NamaDepa4_0_0_ 
    from
        person person0_ 
    where
        person0_.id=?
Hibernate: 
    update
        person 
    set
        Alamat=?,
        NamaBelakang=?,
        NamaDepan=? 
    where
        id=?
Hibernate: 
    select
        person0_.id as id1_0_,
        person0_.Alamat as Alamat2_0_,
        person0_.NamaBelakang as NamaBela3_0_,
        person0_.NamaDepan as NamaDepa4_0_ 
    from
        person person0_
Nama Depan: Ferry  Nama Belakang: Gunawan  Alamat: Banda Aceh
Nama Depan: Fiannur  Nama Belakang: Yusmita  Alamat: Pontianak
Nama Depan: Danu  Nama Belakang: Wirnoyo  Alamat: Citayam
Hibernate: 
    select
        person0_.id as id1_0_0_,
        person0_.Alamat as Alamat2_0_0_,
        person0_.NamaBelakang as NamaBela3_0_0_,
        person0_.NamaDepan as NamaDepa4_0_0_ 
    from
        person person0_ 
    where
        person0_.id=?
Hibernate: 
    delete 
    from
        person 
    where
        id=?
Hibernate: 
    select
        person0_.id as id1_0_,
        person0_.Alamat as Alamat2_0_,
        person0_.NamaBelakang as NamaBela3_0_,
        person0_.NamaDepan as NamaDepa4_0_ 
    from
        person person0_
Nama Depan: Ferry  Nama Belakang: Gunawan  Alamat: Banda Aceh
Nama Depan: Danu  Nama Belakang: Wirnoyo  Alamat: Citayam
...
```
Dari hasil proses Hibernate, telah berhasil melakukan CRUD di MySQL.

## Cek di MySQL

```sql
MariaDB [belajarhibernate]> select * from Person;
+----+-----------+--------------+------------+
| id | NamaDepan | NamaBelakang | Alamat     |
+----+-----------+--------------+------------+
|  1 | Ferry     | Gunawan      | Banda Aceh |
|  3 | Danu      | Wirnoyo      | Citayam    |
+----+-----------+--------------+------------+
2 rows in set (0.00 sec)
```

DONE.

![Download](/images/download.png) **Download** : *[BelajarHibernateANO.zip](http://adf.ly/1n0L4K)*
{: .notice-success}
