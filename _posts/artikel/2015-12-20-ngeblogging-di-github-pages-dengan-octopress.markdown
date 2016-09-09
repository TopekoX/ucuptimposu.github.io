---
layout: article
title: "Nge Blog di Github Pages dengan Octopress"
date: 2015-12-20 15:46:57 +0800
comments: true
categories: artikel
tags: [artikel, ajax, javascript]
ads: true
---
![Octopress](http://i63.tinypic.com/28ji5ud.jpg)

Ada pepatah mengatakan "_Kalau mau terus eksis, ngeblog lah.._", Iya.. blogging saat ini menjadi suatu rutinitas yang menjadi sarana orang berbagi pengalaman, pengetahuan atau sekedar biar cuap..cuap.. di dunia maya, bahkan juga jadi salah satu tempat mancari nafkah lahir maupun nafkah batin #asekk. Salah satu CMS blog yang sangat terkenal yaitu [Wordpress](http://wordpress.org), saya pun menggunakan wordpress dan akhirnya saya pun harus mengganti engine blog saya dari Wordpress ke Octopress dan dari hosting berbayar saya ke hosting gratisan [Github](http://github.com) walau tidak sepenuhnya gratis jadi saya tetap menyewa domainnya karena saya tidak ingin menggunakan sub domain dari github pages.
<!-- more -->

## Migrasi dari Wordpress ke Github Pages

Kenapa saya migrasi dari Wordpress ke Github Pages :

### Wordpress (atau CMS lainnya)

  * Karena Wordpress bersifat web dinamis yang menggunakan web server dengan database sehigga load webnya lebih lambat dibanding web static
  * Tidak semua fitur dari wordpress yang saya gunakan , karena kebutuhan saya hanya nge blog dan worpress punya banyak fitur lebih.
  * Lambat! (tergantung dari bandwidthnya sih -_-) karena saya hanya menyewa paket domain dan hosting yang paling murah di web hosting saya sehingga penggunaanya dibatasi :( .Belum lagi kalau kita sewa hosting lokal yang sering banget down.
  * Saya kadang merasa malas ngeblog ketika mau nulis artikel, di wordpress saya harus konek internet dulu -> login admin WP -> new Post -> tulis artikel, walaupun bisa di akali secara offline dulu di notepad baru setelah fix baru dimasukan ke WP, tapi tetap saja saya merasa ribet(ini adalah faktor utama blog sy pindahin ke Octopress).

Jadi inti dari alasan saya migrasi ke Octopress adalah kebutuhan dan kecepatan.. bukan karena Wordpress tidak bagus. Fitur Wordpress udah lengkap dan kompleks tetapi saya ingin ngeblog dengan efisien dan cepat, maka saya perlu mencari engine blog yang bisa offline dan dapat diakses secara cepat. Sesuai tuntutan jaman dengan munculnya era _cloud_, salah satu fitur yang bisa kita manfaatkan yaitu [Github Pages](http://pages.github.io).

### Github Pages

Github Pages berbeda cara kerjanya dengan Wordpress karena Github Pages bersifat static.

  * Load halaman web lebih cepat karena kebutuhan server lebih sederhana tidak perlu PHP dan MySQL lagi.
  * Load halaman web lebih cepat karena tidak perlu proses query dari database.
  * Karena tidak ada proses query penggunaan CPU dan RAM pada server tidak terlalu terbebani.
  * Anti HACK, karena sifatnya web static jadi kita tidak harus takut terhadap serangan hack seperti SQL Injection dll, kecuali OS nya yang ditembus jadi tidak usah repot-2 harus rajin update security, fix bugnya.
  * Opensource... yah.. web yang dibuat dengan Github otomatis disimpan dalam repo Github yang bisa dilihat semua orang dan orang lain bisa berkontibusi di project web kita juga, kecuali kita buat project kita jadi private tetapi kita harus bayar untuk itu... gak perlu private sih menurut saya itukan web static jadi gak perlu rahasia-rahasiaan... hahahaha.
  * Support [Markdown](http://daringfireball.net/projects/markdown/), adalah text file biasa dengan sedikit markup,

  Kekurangan :

  * Namanya juga web static jelas tidak lengkap fiturnya kayak web dinamis.. contoh untuk web jual-beli, portal berita, tapi kalo hanya fitur blog ini udah cukup.

### Octopress

Octopress ini adalah framework yang dibuat di atas [Jekyll](jekyllrb.com), beberapa fitur Octopress :

  * Mendukung deploy script ke Github, Heroku, dan rsync.
  * Mendukung Berbagai plugin yang sudah disertakan secara built in.

# Persiapan

  * Export data dari wordpress (kalo yang tidak migrasi pake wordpress skipp sj)
  * Install Octopress
  * Setup Octopress
  * Blogging
  * Deploy ke Github

### Export Wordpress (Yang tidak pakai WP skipp step ini)

Pertama tama biar articleing yang dibuat di WP tidak mubazir jadi bisa kita export, lalu kita konversi menjadi markdown dengan [exitwp](https://github.com/thomasf/exitwp/)

  * Download atau clone dengan `` git clone https://github.com/thomasf/exitwp ``
  * Export artikel atau page wordpress lama  dengan wordpress exporter dari menu admin wordpress tools > export.
  * Tempatkan hasil export wordpress xml ke dalam direktori `` wordpress-xml ``.
  * Jalankan perintah `python exitwp.py`.
  * Hasil konversi blog ada di direktori ` build `

Petunjuk selengkapnya bisa dilihat di file __README__ nya.

### Install Octopress

Ikuti beberapa langkah berikut :

  1. Install [Git](https://git-scm.com)
  2. Install Ruby dengan ` rvm `
  3. Install Jekyll
  4. Clone Octopress

Kebetulan saya menggunakan Linux Fedora 22 jadi perintahnya silahkan menyesuaikan.

#### Install Git

    sudo dnf install git-core

#### Install Ruby dengan RVM

RVM (Ruby Version Manager) digunakan untuk installasi dan management Ruby environments. Ruby dibutuhkan oleh Octopress dan kita bisa menginstall Ruby dengan RVM.

Install depedencynya dulu

    sudo dnf install  curl wget gcc zlib-devel make openssl autoconf

Sebelum menginstall RVM , kita harus import public key di sistem yang akan digunakan curl untuk menginstall RVM disistem.

    gpg2 --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3

Jika cara di atas gagal maka coba cara ke 2 :

    curl -sSL https://rvm.io/mpapis.asc | gpg2 --import -

Install Ruby

    curl -sSL https://get.rvm.io | bash -s stable --ruby

Install depedency yang dibutuhkan Ruby

    rvm requirements

Melihat daftar Ruby yang ada

    rvm list known


    # MRI Rubies
    [ruby-]1.8.6[-p420]
    [ruby-]1.8.7[-head] # security released on head
    [ruby-]1.9.1[-p431]
    [ruby-]1.9.2[-p330]
    [ruby-]1.9.3[-p551]
    [ruby-]2.0.0[-p643]
    [ruby-]2.1.4
    [ruby-]2.1[.5]
    [ruby-]2.2[.1]
    [ruby-]2.2-head
    ruby-head

Contoh versi ruby yang ingin digunakan v.1.9.3

    rvm install 1.9.3
    rvm use 1.9.3
    rvm rubygems latest

Tambahkan path environments di .bashrc perintah berikut `source /home/user/.rvm/scripts/rvm` buka terminal baru ketik `ruby --version` jika muncul versi Ruby berarti ruby sukses terinstall.


#### Install Jekyll

Jekyll perlu kita install karena Octopress dibangun dari Jekyll, Cara installnya :

    gem install jekyll
    gem install bundler

#### Clone Octopress

Kita akan mencloning project Octopress contoh saya buat di direktori dengan nama `timposu`

    git clone git://github.com/imathis/octopress.git timposu

Setelah berhasil cloning Octopress dengan kita mulai akan menginstal paket yang dibutuhkan.. tadi kita simpan Octopress kedalam direktori ` timposu `.

    cd timposu
    bundle install

Selanjutnya install theme Octopress

    rake install

Lihat blog

    rake preview

buka url di browser http://localhost:4000

![tadaaaa](http://i63.tinypic.com/33p386u.jpg)

Sampai tahap ini kita sudah berhasi memasang Octopress di komputer kita. Oke selanjutnya __LETS ROCK.....__

### Setup Octopress

File konfigurasi blog Octopress berada di file `_config.yml `, buka file tersebut lalu ubah sesuai konfigurasi blog anda, secara umum variabel yang diubah adalah sbb:

    url:                # URL blog anda
    title:              # Judul blog digunakan untuk header dan title tags
    subtitle:           # subtitle blog anda
    author:             # Nama anda, untuk RSS, Copyright, Metadata
    description:        # Deskripsi blog anda

Masukan juga usename [Disqus](http://disqus.com) untuk komentar Disqus, twitter dll sesuai kebutuhan.

### Mulai Blogging

#### Membuat Artikel/Posting

Posting blog disimpan di dalam direktori ` source/_articles ` dengan format ` YYYY-MM-DD-article-title.markdown `.

Untuk membuat article blog baru gunakan perintah

    rake new_article["Judul Artikel"]

contoh

    rake new_article["Cara buat blog dengan Octopress"]

Secara otomatis akan dibuatkan file ` *.markdown ` di dalam folder ` source/_articles `, isi file tersebut

    ---
    layout: article
    title: "Cara buat blog dengan Octopress"
    date: 2015-12-21 5:59
    comments: true
    external-url:
    categories:
    ---

kita bisa menambahkan author dan categories

    author : Ucup Timposu

    # One category
    categories: Sass

    # Multiple categories example 1
    categories: [CSS3, Sass, Media Queries]

    # Multiple categories example 2
    categories:
    - CSS3
    - Sass
    - Media Queries


Mulailah menulis isi blog di bawah tulisan di atas :)

Bagi yang habis ekport dari Wordpress copy isi direktori ` _articles ` yang ada dalam direktori ` build ` yang di exitwp ke direktori `source/_articles` yang ada di direktori Octopress untuk menampilkan artikel yang dari Wordpress.

#### Membuat Page

Caranya hampir sama dengan membuat articleing cuma perintahnya yang berbeda :

    rake new_page[about]
    # creates /source/about/index.markdown

    rake new_page[about/page.html]
    # creates /source/about/page.html

#### Generate dan preview

Setiap selesai update blog bisa langsung di generate dan di preview untuk melihat nya.

    rake generate
    rake preview

cek kembali http://localhost:4000

![preview](http://i68.tinypic.com/2nrmxcy.jpg)

### Deploy ke Github Pages

Pastikan udah punya akun [github](http://github.com), Buat [repository baru](https://github.com/new)

![buat repository](http://i68.tinypic.com/6nqgox.jpg)

Beri nama repository sesuai username akun github kita ` username.github.io ` contoh akun saya namanya _timposu_ jadi saya kasi nama ` timposu.github.io `

![beri nama blog](http://i68.tinypic.com/35i3ekh.jpg)

Lalu jalankan perintah berikut untuk menambahkan remote ke repository github

    rake setup_github_pages

Akan muncul permintaan memasukan alamat repository git, tinggal pilih via SSH atau HTTPS. contoh saya pakai yang HTTPS ` https://github.com/username/username.github.io ` ganti username sesuai username github anda.

lalu tinggal di generate dan deploy ke github

    rake generate
    rake deploy

blog anda akan digenerate dan source akan di copy ke `_deploy/`,dan akan di deploy isi dari ` _deploy/ ` ke repository github dengan branch ` master `. Kita coba buka sesuai url repositor yang telah dibuat

![view local](http://i68.tinypic.com/28qx8r4.jpg)

Tapi sebaiknya source kode juga kita deploy kerepository dengan branch ` source `

    git add .
    git commit -m 'commit pertama'
    git push origin source

## Apa Selanjutnya ?

* [Custom domain](/blog/2015/12/22/custom-domain-github-pages/),  biar domain tidak menggunakan domain github.
* [Pasang Plugin Tambahan](https://github.com/imathis/octopress/wiki/3rd-party-plugins), untuk menambahkan fitur tambahan ke dalam blog.
* [Ganti thema](https://github.com/imathis/octopress/wiki/3rd-Party-Octopress-Themes).

OK sampai disini kita sudah bisa membuat blog di Github Pages, memang ini bukan ditujukan untuk pemula yang baru mulai nge blog karena bakalan modarrrrrrr... Saya migrasi Personal Blog saya ke Octopress karena kebutuhan.. bukan berarti sudah tak suka wordpress.. Di project lain juga saya juga masih menggunakan wordpress.. karena fiturnya yang lengkap, dan menurut saya blog pribadi yang saya gunakan tidak terlalu membutuhkan fitur-fitur yang banyak dari wordpress. Jadi saya menggunakannya sesuai kebutuhan.


### Referensi :

http://octopress.org/docs/

https://pages.github.com/
