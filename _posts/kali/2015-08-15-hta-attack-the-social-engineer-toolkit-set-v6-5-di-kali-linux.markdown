---
comments: true
date: 2015-08-15 14:48:38+00:00
layout: article
title: HTA Attack The Social-Engineer Toolkit (SET) v6.5 di KALI LINUX
categories: kali
tags: [kali, linux, metasploit, penetration, security]
ads: true
youtubeId: iR53zf9weO8
image:
  feature: 
  teaser: kali_linux_wallpaper_by_lukazoid-d800c86.png
---

![](http://i64.tinypic.com/ipr22a.jpg)

Social-Engineer Toolkit (SET) adalah salah satu tool andalan di KALI Linux yang terdiri dari tool-tool Attack yang mendukung dalam melakukan Penetrasi Keamanan sistem. Salah satu yang menjadi kegemaran saya Reverse_TCP Meterpreter .. hmmm mungkin anda juga... :D. Dibulan Juli kemarin [trustedsec.com](http://trustedsec.com) merilis versi terbaru dari SET ini yaitu versi 6.5.(kode name "Mr. Robot") dengan beberapa penambahan fitur.

<!-- more -->



### version 6.5







  * added brand new attack vector HTA attack and incorporated powershell injection into it


  * fixed a prompt that would cause double IP questions in certain attack vectors


  * slimmed down powershell injection http/https attack vectors in order to use in payload delivery


  * added exploit to browser attack Adobe Flash Player ByteArray Use After Free (2015-07-06)


  * added exploit to browser attack Adobe Flash Player Nellymoser Audio Decoding Buffer Overflow (2015-06-23)


  * added exploit to browser attack Adobe Flash Player Drawing Fill Shader Memory Corruption (2015-05-12)



Pada tutorial kali ini kita hanya fokus pada fitur baru yaitu HTA Attack!!!! :D tapi sebelum itu apa itu HTA..? tunggu kita ke _wikipedia_ dulu...! ternyata HTA itu adalah Aplikasi HTML ( HTA ​​) program Microsoft Windows yang sourcenya dari HTML , Dynamic HTML , terdiri dari satu atau lebih bahasa scripting yang didukung oleh Internet Explorer , seperti VBScript atau JScript.

Yahhh cuma bisa di IE dong... tapi biarlah ini bisa jadi pembelajaran bahwa IE itu sangat rentang dari sisi keamanannya..


Oke.. pastikan versi SET nya udah 6.5 atau yang terbaru...(punya saya 6.5.2 running on Kali Linux 1.1.0) secara default Kali versi 1.1.0 masih menggunakan SET 6.3. cara update nya ..



### Update



masuk ke terminal console pastikan aktif direktorinya di home contoh di `/root` cek pake perintah `pwd` download [ SET Toolkit](https://www.trustedsec.com/social-engineer-toolkit/)



    git clone https://github.com/trustedsec/social-engineer-toolkit/ set/



setelah selesai download akan muncul direktori baru dengan nama `set` , hapus folder `set` yang ada di `/usr/local` kemudian pindahkan direktori `set` yang ada di `/root` ke `/usr/local`



    rm -rf /usr/local/set
    cp /root/set /usr/local/set





## Attack



Catatan: Antara komputer saya dan komputer target saling berhubungan dalam suatu jaringan dan pada tutorial ini IP address saya 192.168.1.17

Untuk mulai menjalankan,  ketik perintah berikut untuk menjalankan SET Toolkit



    setoolkit



akan ada persetujuan tekan tombol Y untuk setuju,

[![](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082511_zpsvignmkij.png)](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082511_zpsvignmkij.png)

pastikan versi SET Toolkit nya sudah 6.5 !. Ikuti Step by Step langkah dibawah ini:

pilih **1) `Social-Engineering Attacks`**

[![](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082516_zpsyfacbh0g.png)](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082516_zpsyfacbh0g.png)pilih **2) `Website Attack Vector`**

[![](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082531_zpsgzw7benq.png)](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082531_zpsgzw7benq.png)

pilih **8) `HTA Attack Method`** lalu masukan IP address kita (192.168.1.17) kemudian isi port (kosongkan saja untuk defaultnya 443) dan pilih jenis serangan Meterpreter, dalam tutorial ini saya pakai `https` (3) kalo anda mencoba yang lain tidak apa-apa.

[![](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082615_zpsc2fnmch7.png)](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082615_zpsc2fnmch7.png)

pilih **2) `Site Cloner `** untuk mencloning Situs https://twitter.com , pilihan ini untuk mencloning situs yang sudah ada.

[![](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082616_zpsk514ekjr.png)](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082616_zpsk514ekjr.png)

Tunggu sampai metasploit handlernya aktif, seperti gambar dibawah ini:

[![](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082725_zpsvdz4fvdw.png)](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082725_zpsvdz4fvdw.png)

Kalo sudah aktif kita coba di komputer target yang menggunakan Windows 8 , buka Internet Explorer dan masukan ip address server metasploit kita yang sudah kita isikan (192.168.1.17). Tunggu hingga muncul jendela Launcher.hta nah.... file ini lah yang menjadi jembatan kita nantinya untuk meremote target.. ketika dia membuka file HTA tersebut.

[![](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082751_zpsou8g26qb.png)](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082751_zpsou8g26qb.png)


Jika file hta tersebut dieksekusi target maka dari sisi server akan memberitahu bahwa kita telah menangkap / membuka sesi Meterpreter. Dalam gambar di bawah ini telah terbuka 1 sesi dari ip 192.168.1.6

[![](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082849_zpszgahmwu0.png)](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082849_zpszgahmwu0.png)

Jrenggg,,, setelah itu kita tinggal meremote target.

[![](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082851_zps8rnhefqg.png)](http://i713.photobucket.com/albums/ww134/upamisterlobal/Screenshot%20from%202015-08-15%20082851_zps8rnhefqg.png)

Kalau anda masih bingung cara kerjanya silahkan tonton video dibawah ini.



{% include youtube.html id=page.youtubeId %}





> PERHATIAN : BIJAKLAH MENGGUNAKAN TUTORIAL INI !!! KAMI TIDAK BERTANGGUNG JAWAB TERHADAP PENYALAHGUNAAN TUTORIAL INI!! TUJUAN TUTORIAL INI DIBUAT UNTUK PEMBELAJARAN SEMATA!!! 
