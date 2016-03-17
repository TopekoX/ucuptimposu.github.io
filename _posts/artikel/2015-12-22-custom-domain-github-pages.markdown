---
layout: article
title: "Cara custom domain Github Pages"
date: 2015-12-22 10:59:38 +0800
categories: artikel
tags: [artikel, ajax, javascript]
ads: true

---

![github pages](http://i68.tinypic.com/wtuo8g.jpg)

Setelah kita [membuat blog di Github Pages](/blog/2015/12/20/ngeblogging-di-github-pages-dengan-octopress/) tentunya kita sudah punya domain yang secara default dibuat dengan nama url `username.github.io`. Untuk mengubah atau mengalihkan nama domain tersebut ke domain kita baik domain root (misal : _domain.com_) atau subdomain (misal : _blog.domain.com_) bisa dilakukan dengan cara mengubah konfigurasi DNS domain yang kita punya.

<!-- more -->

![](http://i68.tinypic.com/28qx8r4.jpg)

## Setting Domain

Yang kita rubah adalah ` A ` dan ` CNAME ` pada domain kita, melalui menu editor DNS, contoh saya menggunakan CPANEL.

![](http://i67.tinypic.com/jtx5yt.jpg)

Pada tutorial ini skenario yang digunakan saya ingin mengubah domain github saya ` timposu.github.io ` menjadi domain ` timposu.com ` kalau kalian menggunakan sub domain kalian ubah saja domainnya contoh ` blog.timposu.com `

* Dari menu Advanced DNS Zone Editor, tambahkan Record baru dengan type ` CNAME ` atau ` ALIAS ` ubah domain kalau yang sudah ada ke point `timposu.github.io`

![](http://oi64.tinypic.com/154uc5w.jpg)

* Jika cara di atas terjadi __ERROR__  atau tidak ponting dengan ` CNAME ` atau ` ALIAS ` tidak apa-apa karena ini juga terjadi sama saya, kita pakai cara kedua buat `A` record dan arahkan Addressnya ke `192.30.252.153` dan `192.30.252.154`.

![](http://i67.tinypic.com/2mzf4wj.jpg)

![](http://i67.tinypic.com/4u6jq0.jpg)

* Jika menggunakan subdomain, contoh ` www.example.com ` atau ` blog.mydomain.com ` , kita hanya merubah ` CNAME ` record mengarah ke `username.github.io`

![](http://i65.tinypic.com/nyu23s.jpg)

## Tambahkan file CNAME

Masuk ke direktori Octopress dan buat file dengan nama ` CNAME ` (nama file harus huruf kapital) ke dalam direktori `source` dan ketik nama domain kita kedalam file tersebut contoh isi file CNAME `timposu.com`.

![](http://i63.tinypic.com/2pskgeh.jpg)

## Deploy ke Github

Jalankan perintah berikut untuk mengenerate dan deploy ke server Github :

`rake generate`

`rake deploy`

Pastikan di repository Github file tersebut sudah ada.

![](http://i68.tinypic.com/2ed1e6p.jpg)

Tadaaaaaaa....

!["custom domain"](http://i68.tinypic.com/5esw49.jpg)

### Referensi

https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages/

https://help.github.com/articles/adding-a-cname-file-to-your-repository/

https://help.github.com/articles/my-custom-domain-isn-t-working/
