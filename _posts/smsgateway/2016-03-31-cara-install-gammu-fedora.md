---
layout: article
title: SMS Gateway - Cara Install Gammu di Fedora
modified:
categories: smsgateway
excerpt:
tags: [smsgateway, gammu]
comments: true
ads: true
image:
  feature:
  teaser:
  thumb:
date: 2016-03-31T21:15:16+08:00
---

Setelah kita mengenal [Apa Itu Gammu](/apa-itu-gammu/) kita mulai menginstall Gammu pada tutorial ini.

## Install & Setting Gammu

Download Gammu via `yum` atau `dnf` (untuk Fedora 22 keatas)

Via `yum`

```
ucup@timposu:~$ sudo yum install gammu
```

via `dnf`

```
ucup@timposu:~$ sudo dnf install gammu
```

Untuk menggunakan Gammu kita harus pakai root atau bisa juga user superadministrator dengan menggunakan perintah `sudo`.
Copy file `gammurc` dan `smsdrc` ke direktori `/etc`

```
ucup@timposu:~$ sudo  cp /usr/share/doc/gammu/examples/config/gammurc /etc

ucup@timposu:~$ sudo  cp /usr/share/doc/gammu/examples/config/smsdrc /etc
```

edit file `gammurc`

```
ucup@timposu:~$ sudo nano /etc/gammurc
```

Isi konfig di sesuai bawah ini

```
device = /dev/ttyUSB0
connection = at115200
```
Untuk jenis HP silahkan menggunakan `/dev/ttyACM0` pada devices contoh jenis hp sonyericsson jika anda menggunakan Usb modem seperti Wavecom anda bisa menggantinya dengan  `/dev/ttyUSB0` atau `/dev/ttyUSB1` tergantung dimana devices anda dikenali oleh linux. Untuk connection bisa secara umum menggunakan koneksi `at115200` atau bisa dilihat pada [Gammu Phone Databases](http://wammu.eu/phones/)

Bila Anda gunakan lebih dari satu HP, maka silahkan tambahkan konfigurasinya pada bagian bawahnya sama seperti cara di atas.

```
[gammu1]
.
.

[gammu2]
.
.
......
```

Cek Konfigurasi sudah Berhasil atau belum menggunakan `gammu identify`.

Jika output seperti dibawah ini berarti konfigurasi berhasil dan Gammu berhasil terhubung dengan modem/handphone, jika hasil error silahkan cek kembali konfigurasi anda belum sesuai atau modem/hp anda tidak di support Gammu.

```
ucup@timposu:~$ sudo gammu identify
Device               : /dev/ttyUSB0
Manufacturer         : Wavecom
Model                : MULTIBAND  900E  1800 (MULTIBAND  900E  1800)
Firmware             : 651b09gg.Q2406B 244 041410 13:45
IMEI                 : 012345678901234
SIM IMSI             : 510110361489525
```
{% include iklan-box.html %}

## Setting Database

Untuk Fedora 22 keatas sekaran paket repositorinya sudah pakai MariaDB pengganti MySQL, tapi tenang aja baik perintah atau querynya hampir 100% sama.

Install Database MariaDB

```
ucup@timposu:~$ sudo dnf install mariadb-server
```

Jalankan service MariaDB

```
ucup@timposu:~$ sudo systemctl start mariadb
```

Buat database untuk Gammu contoh nama database `smsgateway`, kemudian kita import database yang sudah disediakan Gammu di dalam direktori `/usr/share/doc/gammu/examples/sql/`  dengan nama `mysql.sql` bisa lewat PHPMyadmin atau lewat command prompt. Didalam direktori itu ada database untuk Sqlite dan PostgreSQL

```
mysql -u root -p sms_pajak < /usr/share/doc/gammu/examples/sql/mysql.sql
```

## Setting smsdrc

Buka file `smsdrc` lalu edit parameter dibawah ini

```
device = /dev/ttyUSB0
connection = at115200
service = sql
user = usermysql
password = passwordmysql
pc = localhost
database = smsgateway
driver = native_mysql
```

## Menjalankan Service Gammu

Jalankan service Gammu dengan perintah dibawah ini :

```
ucup@timposu:~$ sudo gammu-smsd -c /etc/smsdrc
```
Jika tidak ada error Gammu berhasil berjalan, kalau belum silahkan cek lagi konfigurasinya.

### Referensi

* [http://wammu.eu/gammu/](http://wammu.eu/gammu/)
* [https://fedoraproject.org/wiki/QA:Testcase_MySQL_or_MariaDB_in_gammu](https://fedoraproject.org/wiki/QA:Testcase_MySQL_or_MariaDB_in_gammu)
* [http://wammu.eu/docs/manual/smsd/mysql.html](http://wammu.eu/docs/manual/smsd/mysql.html)
