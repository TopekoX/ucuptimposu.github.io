---
author: ucup
comments: true
date: 2014-06-27 16:34:12+00:00
layout: article
slug: membuat-class-java-yang-baik-dan-benar-dengan-netbeans
title: Membuat Class Java yang baik dan Benar dengan Netbeans
wordpress_id: 509
categories:
- Java

tags:
- Java
- Java Dasar
---

Sekarang kita akan membuat class yang baik dan benar menurut para programmer java. _“apa itu class yang baik dan benar ?”_

class yang bisa disebut baik dan benar adalah class yang memiliki metode yang dinamakan _getter _dan _setter _dan juga harus memiliki metode `equals` dan juga `hashcode` . akan saya bahas satu persatu :





  * getter, metode ini dinamakan metode pengambilan informasi. misalnya saya ingin mendapatkan informasi nama sebuah class, maka class tersebut harus memiliki sebuah metode yang bernama ` getNama() ` , sehingga dengan kata lain getter adalah metode getXxxx (Xxxx = nama atribut/field).


  * setter, metode ini kebalikan dari getter yaitu untuk mengubah informasi, misal saya ingin mengubah informasi nama maka dalam class tersebut harus ada metode setNama(tipeData parameter). jadi kesimpulannya setter adalah metode setXxx(tipeAtribut parameter) (Xxx = nama atribut).


  * equals, metode ini digunakan untuk membandingkan class tersebut dengan class yang lain, apakah sama atau tidak. ini bermanfaat ketika kita menggunakan operasi perbandingan “==”. dan metode ini mengembalikan nilai _true _jika objek yang dibandingkan sama dan _false _jika tidak


  * hashcode, merupakan metode untuk mendapatkan unik integer dari sebuah class, hal ini sangat berguna ketika kita membuat sebuah kumpulan data yang tidak boleh sama atau duplikasi.



selain dalam metode, class yang baik dan benar juga harus memiliki kontruktor baik itu kontruktor javabeans (tak memiliki parameter) ataupun bukan javabeans (memiliki parameter). **OK!!!** lebih baik kita langsung coding ajach. sekarang coba buat sebuah class dengan nama **Mahasiswa **:



    <code>public class Mahasiswa {

    }

    </code>



lalu beri atribut sesuai dengan yang anda inginkan misal :



    import java.util.Date;

    public class Mahasiswa {

    private String nim;
    private String nama;
    private String jenisKelamin;
    private Date tanggalLahir;
    private String alamat;
    }




sekarang kita buat metode getter dan setternya. masuk ke menu :

[![image](http://eecchhoo.files.wordpress.com/2008/06/image-thumb9.png?w=294&h=338)](http://eecchhoo.files.wordpress.com/2008/06/image9.png)

maka akan keluar tooltip seperti dibawah ini :

[![image](http://eecchhoo.files.wordpress.com/2008/06/image-thumb10.png?w=221&h=251)](http://eecchhoo.files.wordpress.com/2008/06/image10.png)

pilihlah “_**Getter and Setter**_“, maka akan muncul dialog seperti dibawah ini :

[![image](http://eecchhoo.files.wordpress.com/2008/06/image-thumb11.png?w=243&h=276)](http://eecchhoo.files.wordpress.com/2008/06/image11.png)

seleksi semuanya, lalu klik **GENERATE**. sekarang class yang tadi kita buat akan berubah seperti ini :



    import java.util.Date;

    public class Mahasiswa {

     private String nim;
    private String nama;
    private String jenisKelamin;
    private Date tanggalLahir;
    private String alamat;

        public String getAlamat() {
    return alamat;
    }

        public void setAlamat(String alamat) {
    this.alamat = alamat;
    }

        public String getJenisKelamin() {
    return jenisKelamin;
    }

        public void setJenisKelamin(String jenisKelamin) {
    this.jenisKelamin = jenisKelamin;
    }

        public String getNama() {
    return nama;
    }

        public void setNama(String nama) {
    this.nama = nama;
    }

        public String getNim() {
    return nim;
    }

        public void setNim(String nim) {
    this.nim = nim;
    }

        public Date getTanggalLahir() {
    return tanggalLahir;
    }

        public void setTanggalLahir(Date tanggalLahir) {
    this.tanggalLahir = tanggalLahir;
    }
    }



sekarang kita buat metode equals dan hashcode, sama seperti tadi tampilkan tooltip seperti pada getter and setter :

[![image](http://eecchhoo.files.wordpress.com/2008/06/image-thumb12.png?w=174&h=159)](http://eecchhoo.files.wordpress.com/2008/06/image12.png)

pilihlah **equals() **and **hashCode()** sehinnga muncul dialog seperti dibawah ini :

[![image](http://eecchhoo.files.wordpress.com/2008/06/image-thumb13.png?w=471&h=256)](http://eecchhoo.files.wordpress.com/2008/06/image13.png)

seleksi seluruhnya lalu klik **GENERATE**, sekarang class yang tadi kita buat akan seperti ini :



    import java.util.Date;

    public class Mahasiswa {

    private String nim;
    private String nama;
    private String jenisKelamin;
    private Date tanggalLahir;
    private String alamat;

        public String getAlamat() {
    return alamat;
    }

        public void setAlamat(String alamat) {
    this.alamat = alamat;
    }

        public String getJenisKelamin() {
    return jenisKelamin;
    }

        public void setJenisKelamin(String jenisKelamin) {
    this.jenisKelamin = jenisKelamin;
    }

        public String getNama() {
    return nama;
    }

        public void setNama(String nama) {
    this.nama = nama;
    }

        public String getNim() {
    return nim;
    }

        public void setNim(String nim) {
    this.nim = nim;
    }

        public Date getTanggalLahir() {
    return tanggalLahir;
    }

        public void setTanggalLahir(Date tanggalLahir) {
    this.tanggalLahir = tanggalLahir;
    }

        @Override
    public boolean equals(Object obj) {
    if (obj == null) {
    return false;
    }
    if (getClass() != obj.getClass()) {
    return false;
    }
    final Mahasiswa other = (Mahasiswa) obj;
    if (this.nim != other.nim && (this.nim == null || !this.nim.equals(other.nim))) {
    return false;
    }
    if (this.nama != other.nama && (this.nama == null || !this.nama.equals(other.nama))) {
    return false;
    }
    if (this.jenisKelamin != other.jenisKelamin && (this.jenisKelamin == null || !this.jenisKelamin.equals(other.jenisKelamin))) {
    return false;
    }
    if (this.tanggalLahir != other.tanggalLahir && (this.tanggalLahir == null || !this.tanggalLahir.equals(other.tanggalLahir))) {
    return false;
    }
    if (this.alamat != other.alamat && (this.alamat == null || !this.alamat.equals(other.alamat))) {
    return false;
    }
    return true;
    }

        @Override
    public int hashCode() {
    int hash = 7;
    hash = 71 * hash + (this.nim != null ? this.nim.hashCode() : 0);
    hash = 71 * hash + (this.nama != null ? this.nama.hashCode() : 0);
    hash = 71 * hash + (this.jenisKelamin != null ? this.jenisKelamin.hashCode() : 0);
    hash = 71 * hash + (this.tanggalLahir != null ? this.tanggalLahir.hashCode() : 0);
    hash = 71 * hash + (this.alamat != null ? this.alamat.hashCode() : 0);
    return hash;
    }
    }



ok sekarang kita akan buat kontruktor, seperti tadi tampilkan tooltipnya :

[![image](http://eecchhoo.files.wordpress.com/2008/06/image-thumb14.png?w=106&h=94)](http://eecchhoo.files.wordpress.com/2008/06/image14.png)

lalu pilih **Constructor**, maka akan muncul dialog seperti ini :

[![image](http://eecchhoo.files.wordpress.com/2008/06/image-thumb15.png?w=280&h=247)](http://eecchhoo.files.wordpress.com/2008/06/image15.png)

seleksi atribut yang akan diinisialisasikan dalam parameter , misalnya saya mengseleksi semuanya, lalu klik **GENERATE**, maka class yang kita buat akan menjadi seperti ini :



    import java.util.Date;

    public class Mahasiswa {

    private String nim;
    private String nama;
    private String jenisKelamin;
    private Date tanggalLahir;
    private String alamat;

    public Mahasiswa(String nim, String nama, String jenisKelamin, Date tanggalLahir, String alamat) {
    this.nim = nim;
    this.nama = nama;
    this.jenisKelamin = jenisKelamin;
    this.tanggalLahir = tanggalLahir;
    this.alamat = alamat;
    }

        public String getAlamat() {
    return alamat;
    }

        public void setAlamat(String alamat) {
    this.alamat = alamat;
    }

        public String getJenisKelamin() {
    return jenisKelamin;
    }

        public void setJenisKelamin(String jenisKelamin) {
    this.jenisKelamin = jenisKelamin;
    }

        public String getNama() {
    return nama;
    }

        public void setNama(String nama) {
    this.nama = nama;
    }

        public String getNim() {
    return nim;
    }

        public void setNim(String nim) {
    this.nim = nim;
    }

        public Date getTanggalLahir() {
    return tanggalLahir;
    }

        public void setTanggalLahir(Date tanggalLahir) {
    this.tanggalLahir = tanggalLahir;
    }

        @Override
    public boolean equals(Object obj) {
    if (obj == null) {
    return false;
    }
    if (getClass() != obj.getClass()) {
    return false;
    }
    final Mahasiswa other = (Mahasiswa) obj;
    if (this.nim != other.nim && (this.nim == null || !this.nim.equals(other.nim))) {
    return false;
    }
    if (this.nama != other.nama && (this.nama == null || !this.nama.equals(other.nama))) {
    return false;
    }
    if (this.jenisKelamin != other.jenisKelamin && (this.jenisKelamin == null || !this.jenisKelamin.equals(other.jenisKelamin))) {
    return false;
    }
    if (this.tanggalLahir != other.tanggalLahir && (this.tanggalLahir == null || !this.tanggalLahir.equals(other.tanggalLahir))) {
    return false;
    }
    if (this.alamat != other.alamat && (this.alamat == null || !this.alamat.equals(other.alamat))) {
    return false;
    }
    return true;
    }

        @Override
    public int hashCode() {
    int hash = 7;
    hash = 71 * hash + (this.nim != null ? this.nim.hashCode() : 0);
    hash = 71 * hash + (this.nama != null ? this.nama.hashCode() : 0);
    hash = 71 * hash + (this.jenisKelamin != null ? this.jenisKelamin.hashCode() : 0);
    hash = 71 * hash + (this.tanggalLahir != null ? this.tanggalLahir.hashCode() : 0);
    hash = 71 * hash + (this.alamat != null ? this.alamat.hashCode() : 0);
    return hash;
    }
    }






Fungsi dari equals itu digunakan untuk membandingkan apakah dua buat objek sama, jadi sebenarnya





` a == b `





adalah **salah**, kenapa? karena a dan b mengarah ke objek yang berbeda, harusnya





` a.equals(b) `





baru bener





dan kalo hasCode itu buat mendapatkan uniqe key dari sebuah object, dan biasanya setiap object memiliki uniqe key yang berbeda kalau sama berarti object tersebut sama .Jadi seperti itulah class yang baik dan benar. tapi sebenarnya ada satu metode yang tak kalah pentingnya, yaitu ` toString() ` . metode ini sangat penting untuk pencetakan sebuah class.





### Referensi



[http://khannedy.com/2008/06/27/membuat-class-yang-baik-dan-benar-menggunakan-netbeans-ide/](http://khannedy.com/2008/06/27/membuat-class-yang-baik-dan-benar-menggunakan-netbeans-ide/)
[http://java2s.com](http://java2s.com)
[http://tutorialspoint.com](http://tutorialspoint.com)
