---
comments: true
date: 2015-09-05 17:25:35+00:00
layout: article
slug: mempermudah-penulisan-codding-dengan-emmet-plugin
categories: artikel
tags: [artikel]
ads: true
---

Menulis _codding_ tentu akan sangat dibutuhkan efisiensi waktu sehingga _project_ yang dibuat akan lebih mudah untuk dikembangkan, dan itulah yang selalu dikembangkan oleh berbagai macam text editor untuk mempermudah kerja programmer. Akan tetapi terkadang fitur yang ada dalam suatu text editor belum memberikan kepuasan para programmer dalam menulis sintaks ( <del>karena programmer tidak akan pernah puas :V</del> ), untuk itu terkadang dibutuhkan fitur tambahan yang belum ada di text editor , dan diantaranya adalah plugin [Emmet](https://packagecontrol.io/packages/Emmet) yang membantu mempermudah dalam menulis sintaks di Editor program, Emmet ini sendiri penerus dari Zen Codding.

<!-- more -->



## Cara Kerjanya



Misalnya kita menulis kode HTML pasti  membutuhkan waktu untuk mengetik semua tag, atribut, tanda kutip, tanda kurung dll. Text editor membantu kita dalam penulisan kode contoh warna kode  dll , tapi kita masih perlu banyak mengetik. Emmet akan membuat singkatan sederhana yang akan menjadi potongan kode yang kompleks.

![Cara kerja Emmet](http://www.smashingmagazine.com/wp-content/uploads/2013/03/initializers.gif)
Sumber gambar: http://www.smashingmagazine.com/wp-content/uploads/2013/03/initializers.gif





  * contoh kita akan membuat struktur HTML seperti dibawah ini :





``` html
<!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Document</title>
    </head>
    <body>

    </body>
    </html>
```







  * kita tidak perlu mengetik semua kode di atas cukup mengetik `  ! ` atau ` html:5 ` lalu tekan tombol **Tab** atau **Ctrl + E**. Gimana mudah kan????








## Install Emmet



Emet mendukung  banyak teks editor  dan IDE, salah satu yang terkenal adalah notepad++ dan Sublime Text, untuk melihat teks editor yang didukung dapat  dilihat dan didownload  di sini [http://www.emmet.io/download/](http://www.emmet.io/download/). Tapi pada tutorial kali ini sy hanya membagikan cara install untuk Eclipse dan Sublime Text.



#### Install Emmet di Eclipse IDE



Emmet dapat dengan mudah diinstall di Eclipse cukup klilk menu _Help > Eclipse Marketplace_  pada textbox _Find_ ketik  `Emmet` akan muncul hasil pencarian Emmet Plugin klik _Install _.

![Install Emmet di Eclipse  plugin Emmet di Eclipse Marketplace](http://i713.photobucket.com/albums/ww134/upamisterlobal/1_zpszcj5rgpy.png)


<blockquote>nb: instalasi butuh koneksi internet</blockquote>





#### Install Emmet di Sublime Text 3







  * [Download Emmet disini](https://github.com/sergeche/emmet-sublime/archive/master.zip) atau bisa clone aja projectnya extract lalu rename foldenya menjadi Emmet.



![Rename foldernya menjadi Emmet](http://i713.photobucket.com/albums/ww134/upamisterlobal/2_zpso6fwcmpf.png)]






  * Buka Sublime Text klik menu _Preferences > Browse Package _akan terbuka folder tempat menyimpan plugin Sublime Text, copy folder Emmet ke folder tersebut.


  * Restart Sublime Text


  * Lihat menu _preferences > emmet > Settings Default  _jika terdapat banyak kode seperti dibawah ini berarti Emmet berhasil diInstall jika tidak berarti proses installasi gagal.














##### Permasalahan jika gagal install







  * Emmet membutuhkan `  PyV8 ` download [PyV8 disini](https://github.com/emmetio/pyv8-binaries) download sesuai versi OS nya


  * Buat folder dengan nama **PyV8**


  * contoh file yang didownload ` pyv8-linux64-p3.zip ` ekstract lalu masukan ke dalam folder **PyV8 **dan pindahkan kedalam folder plugin Sublime Text


  * jadi struktur foldernya kira-kira seperti ini



![Isi folder Packages Sublime Text](http://i713.photobucket.com/albums/ww134/upamisterlobal/3_zps0sl3sl6x.png)



[caption id="" align="aligncenter" width="434"][![](http://i713.photobucket.com/albums/ww134/upamisterlobal/4_zpsdzakengb.png)](http://i713.photobucket.com/albums/ww134/upamisterlobal/4_zpsdzakengb.png) Isi folder PyV8[/caption]

selengkapnya tentang emmet sublime text : [https://github.com/sergeche/emmet-sublime](https://github.com/sergeche/emmet-sublime)



### Beberapa fitur dari Emmet



Buat file html baru di Sublime text dan coba kode dibawah ini



#### Contoh







  * ` html:5 ` atau  `  ! ` for untuk HTML5 doctype


  * ` html:xt `  untuk XHTML transitional doctype


  * ` html:4s ` untuk HTML4 strict doctype





    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Document</title>
    </head>
    <body>

    </body>
    </html>







  * `  p.bar#foo ` akan menghasilkan





    <p class="bar" id="foo"></p>







  * ` h1{foo} `





    # foo







  * ` a[href=#] `





    <a href="#"></a>







  * menggunakan karakter `  * ` untuk mebuat jumlah banyaknya perulangan. contoh ` table>tr*3>td*2 `





``` html
<table>
             <tr>
                 <td></td>
                 <td></td>
             </tr>
             <tr>
                 <td></td>
                 <td></td>
             </tr>
             <tr>
                 <td></td>
                 <td></td>
             </tr>
</table>
```






  * Kita bisa menggunakan karakter `  > ` untuk tag yang didalamnya dan `  + ` untuk tag yang setara dan `  ^ ` untuk tag yang di atasnya contoh ` p>span+span^p ` akan menghasilkan:





    <p><span></span><span></span></p>
    <p></p>







  * memuat group contoh ` (.a>h1)+(.b>h2) `





    <div class="a">
        <h1></h1>
        </div>
        <div class="b">
        <h2></h2>
    </div>



dan masih banyak contoh penulisan lainnya silahkan kunjungi [http://docs.emmet.io/](http://docs.emmet.io/)



## Referensi



[http://docs.emmet.io/](http://docs.emmet.io/)

[http://www.smashingmagazine.com/2013/03/goodbye-zen-coding-hello-emmet/](http://www.smashingmagazine.com/2013/03/goodbye-zen-coding-hello-emmet/)

[https://github.com/sergeche/emmet-sublime](https://github.com/sergeche/emmet-sublime)
