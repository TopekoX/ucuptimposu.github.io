---
author: ucup
comments: true
date: 2015-10-10 11:53:09+00:00
layout: article
slug: java-pengulangan-looping
title: Java - Pengulangan / Looping
wordpress_id: 1288
categories:
- Java

tags:
- Java Dasar
- Java
---

Ada 3 jenis bentuk umum perulangan yang ada dalam java:



### while



Bentuk umum while adalah sebagai berikut



    while(kondisi){
     // blok ini akan diproses apabila kondisi true
    }



contoh :
<!-- more -->



    public class Test{
      public static void main(String[] args){
       int x = 1;
       while (x < 10){
          System.out.println(x);
          x++;
        }
      }
    }



output



    1
    2
    3
    4
    5
    6
    7
    8
    9







### do - while



Bentuk _do-while _adalah sbb:



    do{
          // blok ini akan di cetak terlebih dahulu baru ke kondisi
        }while(kondisi);




contoh :



    public class Test{
      public static void main(String[] args){
       int x = 1;
       do{
          System.out.println(x);
          x++;
        }while(x<10);
      }
    }



output



    1
    2
    3
    4
    5
    6
    7
    8
    9



Hasilnya sama dengan bentuk `while` terus apa bedanya? bentuk `do - while` akan mencetak terlebih dahulu yang ada dalam blok, baru memeriksa kondisi apakah _true_ atau _false_, berbeda dengan `while` yang memeriksa terlebih dahulu kondisinya. Contoh di bawah ini bentuk `do - while` dengan kondisi _false_.



    public class Test{
      public static void main(String[] args){
       int x = 1;
       do{
          //blok ini akan diproses terlebih dahulu
          System.out.println(x);
          x++;
        }while(x < 0); //kondisi false
      }
    }



output :



    1



Walaupun kondisi false tetapi blok `do` akan di proses terlebih dahulu. Jika kondisi _true_ pengulangan akan dilanjutkan, jika _false _pengulangan dihentikan.



### for



Bentuk for sbb:



        for(deklarasi : ekspresi){
         // blok akan dieksekusi for bernilai true
        }




contoh:



    public class Test{
      public static void main(String[] args){
       int x = 10;

        for(int i=1; i <= x; i++){
          System.out.println(i);
        }
      }
    }



output



    1
    2
    3
    4
    5
    6
    7
    8
    9
    10





### Mengenal break dan continue





#### break



Ada kalanya kita ingin keluar dari perulangan yang sedang terjadi di program.. kita bisa menggunakan `break` untuk keluar dari perulangan.

Contoh



    public class Test{
      public static void main(String[] args){
       int x = 1;
       while (x < 10){

          if (x == 5){
           break;
          }

          System.out.println(x);
          x++;
        }
      }
    }



ketika `x == 5` maka akan di eksekusi `break`

output



    1
    2
    3
    4





#### continue



Continue digunakan untuk melanjutkan proses pengulangan

contoh



    public class Test{
      public static void main(String[] args){
       int x = 0;
       while (x < 10){
          x++;
          if (x == 5){
           continue;
          }

          System.out.println(x);
        }
      }
    }





Ketika `x == 5` maka pengulangan akan dilanjutkan tanpa mengeksekusi kode setelah `continue`

output



    1
    2
    3
    4
    6
    7
    8
    9
