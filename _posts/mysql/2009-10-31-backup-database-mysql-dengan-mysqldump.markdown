---
comments: true
date: 2009-10-31 12:17:00+00:00
layout: article
title: Backup database MySql dengan mysqldump
categories: mysql
tags: mysql
ads: true
---

Mysqldump adalah program klien yang mengexport isi tabel ke file-file. Program ini bermanfaat untuk:
Membuat backup database.
Mentransfer isi database ke server lainnya.





## Pengoperasian dari mysqldump





mysqldump mempunyai tiga mode umum operasi tergantung bagaimana dia dipanggil, sbb: Defaultnya, mysqldump menerjemahkan argumen pertama (yang bukan opsion) sebagai nama database dan mendump semua isi tabel dalam database tsb. Jika argumen lain mengikuti nama database, mysql menerjemahkan mereka sebagai nama tabel dan mendumpnya. Perintah berikut ini mendump isi dari semua tabel dalam database arsy ke dalam nama file telpon.sql ke Drive D.

`mysqldump telpon > d:\telpon.sql`





Jangan lupa untuk menjalankan program klien, sebutkan usernya misal jika menggunakan user root , contoh:
`mysqldump telpon > d:\telpon.sql -u root -p`





lalu masukan password root.





Argumen yang berada setelah nama database adalah tabel-tabel, sbb:
`mysqldump telpon customer hp > d:\telpon.sql`





Mendump beberapa database Dengan opsi `–database` atau `-B` , mysqldump menerjemahkan setiap argumen (yang bukan opsi) sebagai nama database dan mendump semua tabel dalam setiap nama database, sbb:
`mysqldump –database telpon toko > d:\telpon_dan_toko.sql `





atau





`mysqldump –B telpon toko > d:\telpon_dan_toko.sql`





Mendump semua database Dengan opsi `–all-database` atau `-A` , mysqldump mendump semua tabel dalam semua database, sbb: 
`mysqldump –all-databases > semua_dbase.sql `





atau





`mysqldump –A-databases > semua_dbase.sql`
