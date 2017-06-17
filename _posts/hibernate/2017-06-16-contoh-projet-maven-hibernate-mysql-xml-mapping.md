---
layout: article
title: Membuat Aplikasi Maven + Hibernate + MySql CRUD (XML Mapping)
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
date: 2017-06-16T23:20:35-04:00
---

![Hibernate](/images/hibernate.png)

Di tutorial ini kita akan membuat project Hibernate dengan menggunakan Maven untuk generate projectnya, dan Hibernate untuk CRUD data ke MySQL atau MariaDB

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

## 1. Buat Tabel

Buat tabel dengan nama `pegawai` di mysql dengan asumsi kita sudah memiliki database dengan nama database `belajarhibernate` 

```sql
CREATE TABLE `pegawai` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `NamaDepan` varchar(20) DEFAULT NULL,
  `NamaBelakang` varchar(20) DEFAULT NULL,
  `Alamat` varchar(20) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=13 DEFAULT CHARSET=latin1 
```

## 2. Generate project dengan Maven

Kita akan membuat project Java dengan nama `BelajarHibernate` dengan maven melalui command prompt :

**Baca Juga:** 
[Cara membuat project Java dengan maven](/cara-membuat-project-java-dengan-maven/)
{: .notice-success}

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

```
mvn archetype:generate -DgroupId=com.timposu -DartifactId=BelajarHibernate -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

## 3. Convert ke Project Eclipse

Disini saya menggunakan IDE Eclipse, kalo anda tidak menggunakan eclipse skipp step ini

```
mvn eclipse:eclipse
```

## 4. Import project ke Eclipse

Dari eclipse pilih File –> Import –> General folder, Existing Projects into Workspace –>pilih lokasi project folder . Done

## 5. Buat folder resources

Buat resources folder di dalam `src/main` sehingga menjadi, `/src/main/resources` , nantinya folder akan dibaca maven sebagai tempat menyimpan file-file tambahan yang butuhkan project. 

## 6. Struktur Project

![strukturhibernate](/images/hibernate/strukturhibernate.png)

## 7. Menambahkan depedency Hibernate, MySQL

Edit maven `pom.xml` tambahkan depedency hibernate dan MySQL

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
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
	
	<!-- Hibernate depedency -->
	<dependency>
	    <groupId>commons-logging</groupId>
	    <artifactId>commons-logging</artifactId>
	    <version>1.2</version>
	</dependency>
	
	<dependency>
	    <groupId>commons-collections</groupId>
	    <artifactId>commons-collections</artifactId>
	    <version>3.2.2</version>
	</dependency>
	
	<dependency>
	    <groupId>cglib</groupId>
	    <artifactId>cglib</artifactId>
	    <version>3.2.5</version>
	</dependency>
	
	<dependency>
	    <groupId>javax.transaction</groupId>
	    <artifactId>jta</artifactId>
	    <version>1.1</version>
	</dependency>
	
	<dependency>
	    <groupId>org.dom4j</groupId>
	    <artifactId>dom4j</artifactId>
	    <version>2.0.0</version>
	</dependency>
	
	<dependency>
		<groupId>org.slf4j</groupId>
		<artifactId>jcl-over-slf4j</artifactId>
		<version>1.7.12</version>
	</dependency>
	
  </dependencies>
</project>
```

Maven nantinya akan secara otomatis mendownload depedency yang dibutuhkan.

## 8. Buat Hibernate Mapping file dan Model Class

Kita akan mapping table pegawai yang sudah kita buat di MySQL kedalam file `Pegawai.hbm.xml`, tapi sebelumnya kita buat dulu class model Pegawai.

Buat package `com.timposu.model`

*File : Pegawai.java*

```java
package com.timposu.model;

public class Pegawai {

	private int id;
	private String namaDepan;
	private String namaBelakang;
	private String alamat;
	
	public Pegawai(){
	}
	
	public Pegawai(String namaDepan, String namaBelakang, String alamat) {
		super();
		this.namaDepan = namaDepan;
		this.namaBelakang = namaBelakang;
		this.alamat = alamat;
	}
	public int getId() {
		return id;
	}
	public void setId(int id) {
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

Buat file mapping kedalam folder `resources`

*File : Pegawai.hbm.xml*

```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE hibernate-mapping PUBLIC 
 "-//Hibernate/Hibernate Mapping DTD//EN"
 "http://www.hibernate.org/dtd/hibernate-mapping-3.0.dtd"> 

<hibernate-mapping>
   <class name="com.timposu.model.Pegawai" table="pegawai">
      <id name="id" type="int" column="id">
         <generator class="native"/>
      </id>
      <property name="namaDepan" column="NamaDepan" type="string"/>
      <property name="namaBelakang" column="NamaBelakang" type="string"/>
      <property name="alamat" column="Alamat" type="string"/>
   </class>
</hibernate-mapping>
```

**Perhatian:** Pastikan pada class name harus sama dengan nama class model beserta packagenya
{: .notice-warning}

## Buat Hibernate Configuration

Buat file konfigurasi hibernate dan letakkan di folder, `src/main/resources/hibernate.cfg.xml`. Sesuaikan parameternya dengan server MySQL anda.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE hibernate-configuration SYSTEM 
"http://www.hibernate.org/dtd/hibernate-configuration-3.0.dtd">

<hibernate-configuration>
   <session-factory>
	   <property name="hibernate.bytecode.use_reflection_optimizer">false</property>
        
	   <property name="hibernate.dialect">org.hibernate.dialect.MySQLDialect</property>
	   <property name="hibernate.connection.driver_class">com.mysql.jdbc.Driver</property>
	   <!-- Assume test is the database name -->
	   <property name="hibernate.connection.url">jdbc:mysql://localhost/belajarhibernate</property>
	   <property name="hibernate.connection.username">root</property>
	   <property name="hibernate.show_sql">true</property>
		<property name="hibernate.format_sql">true</property>
		<property name="hibernate.connection.password">xxxxxx</property>
	   <!-- List of XML mapping files -->
	   <mapping resource="Pegawai.hbm.xml"/>

</session-factory>
</hibernate-configuration>
```

Pada bagian mapping resource adalah nama file mapping sesuai class model yang sudah kita buat. Jika terdapat lebih dari satu file tinggal ditambahkan saja.

## 9. Buat service class CRUD

Class ini buat membuat service CRUD ke MySQL. Tapi sebelumnya biar rapi kita buat package `com.timposu.service`

*File : ServicePegawai.java*

```java
package com.timposu.service;

import java.util.Iterator;
import java.util.List;

import org.hibernate.HibernateException;
import org.hibernate.Session;
import org.hibernate.SessionFactory;
import org.hibernate.Transaction;

import com.timposu.model.Pegawai;

public class ServicePegawai {
	
	private SessionFactory factory;
	
	public ServicePegawai(SessionFactory factory) {
		super();
		this.factory = factory;
	}

	public Integer addPegawai(String namaDepan, String namaBelakang, String string){
	      Session session = factory.openSession();
	      Transaction tx = null;
	      Integer pegawaiID = null;
	      try{
	         tx = session.beginTransaction();
	         Pegawai pegawai = new Pegawai(namaDepan, namaBelakang, string);
	         pegawaiID = (Integer) session.save(pegawai); 
	         tx.commit();
	      }catch (HibernateException e) {
	         if (tx!=null) tx.rollback();
	         e.printStackTrace(); 
	      }finally {
	         session.close(); 
	      }
	      return pegawaiID;
	   }
	
	public void listPegawai(){
	      Session session = factory.openSession();
	      Transaction tx = null;
	      try{
	         tx = session.beginTransaction();
	         List pegawais = session.createQuery("FROM Pegawai").list(); 
	         for (Iterator iterator = 
	                           pegawais.iterator(); iterator.hasNext();){
	            Pegawai pegawai = (Pegawai) iterator.next(); 
	            System.out.print("Nama Depan: " + pegawai.getNamaDepan()); 
	            System.out.print("  Nama Belakang: " + pegawai.getNamaBelakang()); 
	            System.out.println("  Alamat: " + pegawai.getAlamat()); 
	         }
	         tx.commit();
	      }catch (HibernateException e) {
	         if (tx!=null) tx.rollback();
	         e.printStackTrace(); 
	      }finally {
	         session.close(); 
	      }
	   }
	
	public void updatePegawai(Integer IdPegawai, String alamat){
	      Session session = factory.openSession();
	      Transaction tx = null;
	      try{
	         tx = session.beginTransaction();
	         Pegawai pegawai = 
	                    (Pegawai)session.get(Pegawai.class, IdPegawai); 
	         pegawai.setAlamat(alamat);
			 session.update(pegawai); 
	         tx.commit();
	      }catch (HibernateException e) {
	         if (tx!=null) tx.rollback();
	         e.printStackTrace(); 
	      }finally {
	         session.close(); 
	      }
	   }
	
	public void deletePegawai(Integer IdPegawai){
	      Session session = factory.openSession();
	      Transaction tx = null;
	      try{
	         tx = session.beginTransaction();
	         Pegawai pegawai = 
	                   (Pegawai)session.get(Pegawai.class, IdPegawai); 
	         session.delete(pegawai); 
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

## 10. Buat class main

Kita sebenarnya bisa langsung panggil dari class `App.java` tapi ditutorial ini saya buat class baru

*File : ManagePegawai.java*

```java
package com.timposu;

import org.hibernate.SessionFactory;
import org.hibernate.cfg.Configuration;

import com.timposu.service.ServicePegawai;

public class ManagePegawai {
		
	private static SessionFactory factory;
	
	public static void main(String[] args) {
		
		try{
			factory = new Configuration().configure().buildSessionFactory();
		}catch (Throwable ex) { 
	         System.err.println("Gagal membuat sessionFactory object." + ex); 
	    }
			
		  //buat service
		  ServicePegawai SP = new ServicePegawai(factory);

		  //tambah pegawai & mengembalikan id pegawainya
	      Integer pegawai1 = SP.addPegawai("Ferry", "Gunawan", "Banda Aceh");
	      Integer pegawai2 = SP.addPegawai("Fiannur", "Yusmita", "Pontianak");
	      Integer pegawai3 = SP.addPegawai("Danu", "Wirnoyo", "Bekasi");

	      //daftar pegawai
	      SP.listPegawai();
	      
	      //update data
	      SP.updatePegawai(pegawai3, "Citayam");
	      
	      //daftar pegawai
	      SP.listPegawai();
	       
	      //hapus pegawai ke 2
	      SP.deletePegawai(pegawai2);

 	      //daftar pegawai
	      SP.listPegawai();
	   }
	   
}
```

## 11. Struktur folder akhir

![strukturhibernate](/images/hibernate/struktur2.png)


## 12. Running

Disini saya running lewat command prompt mengunakan Maven

```
$ mvn clean package exec:java -Dexec.mainClass=com.timposu.ManagePegawai
....
Hibernate: 
    insert 
    into
        pegawai
        (NamaDepan, NamaBelakang, Alamat) 
    values
        (?, ?, ?)
Hibernate: 
    insert 
    into
        pegawai
        (NamaDepan, NamaBelakang, Alamat) 
    values
        (?, ?, ?)
Hibernate: 
    insert 
    into
        pegawai
        (NamaDepan, NamaBelakang, Alamat) 
    values
        (?, ?, ?)
Jun 17, 2017 1:21:26 AM org.hibernate.hql.internal.QueryTranslatorFactoryInitiator initiateService
INFO: HHH000397: Using ASTQueryTranslatorFactory
Hibernate: 
    select
        pegawai0_.id as id1_0_,
        pegawai0_.NamaDepan as NamaDepa2_0_,
        pegawai0_.NamaBelakang as NamaBela3_0_,
        pegawai0_.Alamat as Alamat4_0_ 
    from
        pegawai pegawai0_
Nama Depan: Ferry  Nama Belakang: Gunawan  Alamat: Banda Aceh
Nama Depan: Fiannur  Nama Belakang: Yusmita  Alamat: Pontianak
Nama Depan: Danu  Nama Belakang: Wirnoyo  Alamat: Bekasi
Hibernate: 
    select
        pegawai0_.id as id1_0_0_,
        pegawai0_.NamaDepan as NamaDepa2_0_0_,
        pegawai0_.NamaBelakang as NamaBela3_0_0_,
        pegawai0_.Alamat as Alamat4_0_0_ 
    from
        pegawai pegawai0_ 
    where
        pegawai0_.id=?
Hibernate: 
    update
        pegawai 
    set
        NamaDepan=?,
        NamaBelakang=?,
        Alamat=? 
    where
        id=?
Hibernate: 
    select
        pegawai0_.id as id1_0_,
        pegawai0_.NamaDepan as NamaDepa2_0_,
        pegawai0_.NamaBelakang as NamaBela3_0_,
        pegawai0_.Alamat as Alamat4_0_ 
    from
        pegawai pegawai0_
Nama Depan: Ferry  Nama Belakang: Gunawan  Alamat: Banda Aceh
Nama Depan: Fiannur  Nama Belakang: Yusmita  Alamat: Pontianak
Nama Depan: Danu  Nama Belakang: Wirnoyo  Alamat: Citayam
Hibernate: 
    select
        pegawai0_.id as id1_0_0_,
        pegawai0_.NamaDepan as NamaDepa2_0_0_,
        pegawai0_.NamaBelakang as NamaBela3_0_0_,
        pegawai0_.Alamat as Alamat4_0_0_ 
    from
        pegawai pegawai0_ 
    where
        pegawai0_.id=?
Hibernate: 
    delete 
    from
        pegawai 
    where
        id=?
Nama Depan: Ferry  Nama Belakang: Gunawan  Alamat: Banda Aceh
Nama Depan: Danu  Nama Belakang: Wirnoyo  Alamat: Citayam
...
```
Dari hasil proses Hibernate, telah berhasil melakukan CRUD di MySQL.

## 13. Cek di MySQL

```sql
MariaDB [belajarhibernate]> select * from pegawai;
+----+-----------+--------------+------------+
| id | NamaDepan | NamaBelakang | Alamat     |
+----+-----------+--------------+------------+
|  1 | Ferry     | Gunawan      | Banda Aceh |
|  3 | Danu      | Wirnoyo      | Citayam    |
+----+-----------+--------------+------------+
2 rows in set (0.00 sec)
```

DONE.

![Download](/images/download.png) **Download** : *[BelajarHibernateXML.zip](http://j.gs/98Gi)*
{: .notice-success}

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

### Referensi

[http://www.mkyong.com/](http://www.mkyong.com/hibernate/quick-start-maven-hibernate-mysql-example/)


