---
author: ucup
comments: true
date: 2015-11-04 06:12:30+00:00
layout: article
slug: mengenal-yeoman
title: Mengenal Yeoman !
wordpress_id: 1363
categories:
- Javascript
- NodeJS
tags:
- Javascript
- NodeJS
- Yeoman
---

![](http://i66.tinypic.com/2ytw4g2.jpg)

## Apa itu Yeoman?

[Yeoman](http://yeoman.io/) adalah generator untuk aplikasi web, berbicara tentang generator generator ini mendukung banyak aplikasi project web modern seperti Angular, EmberJS dll.


## Kenapa harus Yeoman?



Nah.. kita sudah tau kalau Yeoman adalah generator untuk aplikasi web, dengan Yeoman aplikasi web yang kita buat akan secara otomatis di generate oleh Yoeman jadi kita gak perlu pusing masalah struktur folder, alur kerja, paket pendukung dll, karena Yoeman bertujuan untuk mempermudah masalah pembuatan website yang rumit dengan alur kerja _the scaffolding workflow_.

<!-- more -->

Alur kerja _(Workflow)_ Yeoman terdiri dari tiga tools utama untuk meningkatkan produktivitas dan kepuasan ketika membangun aplikasi web. Tools tersebut adalah:





  * [yo](https://github.com/yeoman/yo) - _scaffolding_ dari Yeoman


  * Paket manager [bower](http://bower.io/) atau [npm](https://www.npmjs.com/) - untuk mendownload paket kebutuhan dalam project Yeoman


  * _Build tool_ [grunt](http://gruntjs.com/) atau [gulp](http://gulpjs.com/) - untuk melakukan building aplikasi web Yeoman



Masing-masing projet tools diatas dikelola oleh komunitas masing-masing, tapi bekerja sama dengan baik sesuai alur kerja untuk menjaga project Yeoman tetap efektif untuk digunakan. Berikut alur binary Yeoman

[![Alur Yeoman](https://camo.githubusercontent.com/b3665911e14793c7141619f3b6be380f8b92e61d/687474703a2f2f79656f6d616e2e696f2f7374617469632f776f726b666c6f772e356364653834653363302e6a7067)](https://camo.githubusercontent.com/b3665911e14793c7141619f3b6be380f8b92e61d/687474703a2f2f79656f6d616e2e696f2f7374617469632f776f726b666c6f772e356364653834653363302e6a7067)



## [](https://github.com/timposu/source-kode-tutorial/tree/master/yeoman#install-prerequisites)Install prerequisites



Sebelum menginstall Yeoman pastikan aplikasi dibawah ini sudah terinstall dengan baik :





  * [Node.js](https://nodejs.org/)


  * [npm](https://www.npmjs.com/) (sudah satu paket dengan Node.js)


  * [git](https://git-scm.com/)





## [](https://github.com/timposu/source-kode-tutorial/tree/master/yeoman#yo)yo



Yo dikelola oleh Yeoman project dan menawarkan aplikasi web _scaffolding_, memanfaatkan _scaffolding_ template kita sebut sebagai generator. Kita bisa menginstal yo dan setiap generator dengan menggunakan `npm`.



## [](https://github.com/timposu/source-kode-tutorial/tree/master/yeoman#install-yo-dan-generator-pendukung)Install yo dan generator pendukung





    $ npm install -g yo bower grunt-cli gulp








## [](https://github.com/timposu/source-kode-tutorial/tree/master/yeoman#install-basic-scaffolding)Install _Basic scaffolding_



Untuk menginstall _scaffold web application_ , kita perlu menginstall `generator-webapp` generator. Paket ini adalah default untuk pembuatan web application generator, paket ini sudah termasuk didalamnya [HTML5 Boilerplate](https://html5boilerplate.com/), [jQuery](http://jquery.com/),[Modernizr](http://modernizr.com/), dan [Bootstrap](http://getbootstrap.com/).



    $ npm install -g generator-webapp




Membuat folder project



    $ mkdir latihan-yeoman
    $ cd latihan-yeoman




jalankan



    $ yo webapp




Secara otomatis Yeoman akan menginstall paket-paket pendukung, jadi sediakan koneksi internet yang mumpuni yah... :D



## [](https://github.com/timposu/source-kode-tutorial/tree/master/yeoman#install-scaffolding-angularjs-app)Install _Scaffolding AngularJS app_



Untuk menginstall paket Yeoman untuk generator AngularJS pakai perintah dibawah ini



    $ npm install -g generator-angular




jika berhasil buat folder baru seperti contoh sebelumnya dan jalankan perintah di bawah ini



    $ yo angular






## [](https://github.com/timposu/source-kode-tutorial/tree/master/yeoman#grunt)Grunt



Menjalankan aplikasi dengan grunt



    $ grunt serve




output






    Running "serve" task

    Running "clean:server" (clean) task
     1 path cleaned.

    Running "wiredep:app" (wiredep) task

    Running "wiredep:test" (wiredep) task

    Running "concurrent:server" (concurrent) task

    Running "copy:styles" (copy) task
    Copied 1 file

    Done, without errors.


    Execution Time (2015-11-04 05:52:41 UTC)
    loading tasks               196ms  █████████████████████████████ 85%
    loading grunt-contrib-copy   19ms  ███ 8%
    copy:styles                  15ms  ███ 7%
    Total 230ms

    Running "articlecss:server" (articlecss) task
     1 processed stylesheet created.

    Running "connect:livereload" (connect) task
    Started connect web server on http://localhost:9000

    Running "watch" task
    Waiting...









jika berhasil buka browser, url defaultnya [http://localhost:9000/#/](http://localhost:9000/#/)

[![yeoman preview](https://raw.githubusercontent.com/timposu/source-kode-tutorial/master/yeoman/img/pic.png)](https://raw.githubusercontent.com/timposu/source-kode-tutorial/master/yeoman/img/pic.png)



## [](https://github.com/timposu/source-kode-tutorial/tree/master/yeoman#referensi)Referensi







  * [yeoman learning](http://yeoman.io/learning/)


  * [yeoman codelab](http://yeoman.io/codelab/index.html)
