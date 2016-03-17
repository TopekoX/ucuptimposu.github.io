---
comments: true
date: 2010-01-21 04:06:00+00:00
layout: article
title: Cara install paket RPM dan TGZ di linux
categories: linux
tags: linux
ads: true
image:
  feature: 
  teaser: leds_photo.jpg
---

1. RPM

RPM adalah singkatan dari Red Hat Package Manager. Tidak semua perusahaan distribusi Linux mendukung format ini, tetapi ini merupakan aplikasi yang mudah yang sangat baik menurut saya. Format ini di buat oleh perusahaan RedHat yaitu salah satu Perusahaan Distribusi Linux, dan sudah pasti ente-ente dapat menemukanyya jika anda punya Distribusi Linux ini (Redhat).Format ini juga didukung oleh Fedora,SUSE dan Caldera, mereka ini salah satu dari beberapa perusahaan Distribusi linux lho…

Aplikasi-aplikasi yang berformat ini (rpm), dan dapat di di instal menggunakan aplikasi yang namanya “rpm” ini, anda bisa mendapatkannya di Internet .

Biasanya kalo anda menginstall atau menguninstall suatu aplikasi syaratnya harus menjadi Super User(root).

Untuk menginstal program cukup ketik :

#rpm -i nama_paket.rpm
Untuk mengupgrade aplikasi yang lama ketik:



#rpm -U nama_paket.rpm



untuk menghapus(Erase) paket yang sudah terinstall:



#rpm -e nama_paket.rpm



(Perhatikan cara penulisannya linux bersifat Case Sensitive jadi huruf besar & huruf kecil sangat berpengaruh).

2. TGZ / TAR (tar.gz)
Ada juga yang dalam format “tar”. Hampir semua distribusi Linux dapat membaca format ini, Sebuah aplikasi yang berformat “tar” biasanya adalah aplikasi yang di kompress/di mapatkan. dan kita hanya perlu memekarkan aplikasi tersebut.
Sintaksnya umumnya seperti ini :


# tar -xzvf nama_file.tar.gz



dimana parameter x adalah untuk memekarkan file, z untuk menyaring file hasil compresian dari format gzip , v untuk mode pemberitahuan sehingga user dapat mengetahui proses yang terjadi,sementara , f adalah ada namafile yang harus diikuti

Biasanya kita juga ingin menginstall aplikasi dengan cara mengkompile source code yang kita dapat dari sumbernya, dan kadang atau selalu juga disertakan pentunjuk di dalamnya biasanya ada pada file README atau INSTALL, kita bisa merujuk ke file tersebut. Di dalam petunjuk tersebut ada disebutkan bagaimana cara mengkompile ataupun menginstal suatu aplikasi.
Biasanya stepnya itu seperti ini : (sebaiknya jadikan rujukan dari file README/INSTALL seperti tersebut diatas)



# ./configure



kenapa pake tanda “titik strep (dot slash)” dan di ikuti “configure”, ini karena ada script yang namanya configure pada direktory aktif dimana source code itu ditempatkan, yang di tandai dengan tanda titik ( ” . “),
atau lakukan perintah dibawah ini misalnya source code itu ada di direktory /home/topeko/



# /home/andi/configure



lalu biasanya dilanjutkan dengan



# make



ini memperlihatkan utility make untuk menjalankan proses Makefile dan mengkompile sebuah program untuk kita.
lalu dapat dilanjutkan dengan ….



# make install



Yang mana akan menjalankan utiliti make lagi, yang digunakan untuk mengkopi dan mengkompile file yang di butuhkan untuk menjalankan programnya.

Selain kedua paket diatas , masih lagi paket2 lain seperti deb, lzm dll.....

Silahkan cari tutorialnya di internet sesuai distro yang anda pakai....
