---
comments: true
date: 2015-10-05 07:40:02+00:00
layout: article
slug: statement-kondisi
title: Java - Statement Kondisi
categories: java
tags: [java]
ads: true
series : "Tutorial Java Core"
image:
  feature:
  teaser: java.jpg
---

Conditional Statement digunakan untuk mengambil keputusan dalam eksekusi program yang terbagi 3 :





  * ` if ` statement


  * ` if - else ` statement


  * ` if - else if -else ` statement


  * ` switch ` statement



<!-- more -->



### Kondisi IF




``` java    
if(kondisi) {
/** blok ini akan dieksekusi apabila kondisi bernilai true **/
}
```



contoh


```java   
public class Test{
public static void main(String [] args){
	int a=5;
	if (a < 10) {
		System.out.println("a lebih kecil dari 10");
	}
 }
}
```



dari kode di atas dapat dilihat bahwa blok dalam `if` akan di eksekusi karena kodisi a < 10 adalah true

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


### Kondisi IF - ELSE





```java
if(kondisi) {
/** blok ini akan dieksekusi apabila kondisi bernilai true **/
}else (kondisi) {
/** blok ini akan dieksekusi apabila kondisi if sebelumnya bernilai false**/
}
```

contoh


```java   
public class Test{
public static void main(String [] args){
	int a=5;
	if (a < 3) {
		System.out.println("a lebih kecil dari 3");
	} else{
		 System.out.println("a tidak lebih kecil dari 3");
	}
  }
}
```




<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

### Kondisi IF - ELSE IF - ELSE





``` java
if(kondisi) {
    /** blok ini akan dieksekusi apabila kondisi bernilai true **/
    }else if (kondisi) {
    /** blok ini akan dieksekusi apabila kondisi if sebelumnya bernilai false dan kondisi else if ini bernilai true **/
    }else (kondisi) {
    /** blok ini akan dieksekusi apabila kondisi if sebelumnya bernilai false**/
}
```



Contoh


``` java    
public class Test{
public static void main(String [] args){
	int nilai=90;
	if (a <= 50) {
		System.out.println("Nilai anda kurang");
	} else if(a <= 70){
		 System.out.println("Nilai anda cukup");
	}else{
		 System.out.println("Nilai anda baik sekali");
	}
   }
}
```


### SWITCH Statement



Statement ini bentuknya berbeda dari sebelumnya.. Statement akan di eksekusi apabila _value_ sama dengan _expression_.



``` java
switch(expression){
        case value :
           //Statements
           break; //optional
        case value :
           //Statements
           break; //optional
        default : //Optional
           //Statements
 }
```



Contoh :

``` java    
public class Test{
     public static void main(String [] args){
      char grade = 'C';

          switch(grade)
          {
             case 'A' :
                System.out.println("Sangat baik!");
                break;
             case 'B' :
                System.out.println("Baik!");
                break;
             case 'C' :
                System.out.println("Cukup!");
                break;
             case 'D' :
                System.out.println("Buruk!");
                break;
             case 'E' :
                System.out.println("Mengulang");
                break;
             }
          System.out.println("Hasil ujian " + grade);
       }
}
```



Output



    Cukup!
    Hasil ujian C



Kita bisa menggunakan perintah `default` apabila _expression_ tidak ditemukan dalam blok `switch`. Contoh:


``` java    
public class Test{
     public static void main(String [] args){
      char grade = 'F';

          switch(grade)
          {
             case 'A' :
                System.out.println("Sangat baik!");
                break;
             case 'B' :
                System.out.println("Baik!");
                break;
             case 'C' :
                System.out.println("Cukup!");
                break;
             case 'D' :
                System.out.println("Buruk!");
                break;
             case 'E' :
                System.out.println("Mengulang");
                break;
             default:
                System.out.println("Nilai Error!!!");
             }   
        }
    }
```


Output



    Nilai Error!!!



Perhatikan juga disitu ada perintah `break`. Perintah tersebut digunakan untuk keluar dari blok ` switch `. Contoh kita tidak menggunakan break


``` java   
public class Test{
     public static void main(String [] args){
      char grade = 'D';

          switch(grade)
          {
             case 'A' :
                System.out.println("Sangat baik!");

             case 'B' :
                System.out.println("Baik!");

             case 'C' :
                System.out.println("Cukup!");

             case 'D' :
                System.out.println("Buruk!");

             case 'E' :
                System.out.println("Mengulang");

             default:
                System.out.println("Nilai Error!!!");
             }   
        }
    }

```

Output



    Buruk!
    Mengulang!
    Nilai Error!!!



Dapat dilihat bahwa setelah mengekseskusi nilai yang sesuai eksekusi akan terus dilanjutkan karena tidak ada perintah `break`.

{% include series.html %}
