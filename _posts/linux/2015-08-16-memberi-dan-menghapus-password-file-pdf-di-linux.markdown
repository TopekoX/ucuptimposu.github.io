---
comments: true
date: 2015-08-16 03:45:57+00:00
layout: article
slug: memberi-dan-menghapus-password-file-pdf-di-linux
title: Memberi dan Menghapus password file PDF di Linux
categories: linux
tags: [linux, security]
ads: true
image:
  feature: 
  teaser: leds_photo.jpg

---

Untuk Encrypt & Decrypt password pdf dilinux bisa menggunakan tool `pdftk` , tapi sebelumnya pastikan Java telah terinstall di sistem Linux anda install pdftk berbasis debian (Ubuntu , Mint dkk):



    sudo apt-get install pdftk



install pdftk berbasis redhat lihat petunjuk disini: [https://www.pdflabs.com/docs/install-pdftk-on-redhat-or-centos/](https://www.pdflabs.com/docs/install-pdftk-on-redhat-or-centos/) ketik di terminal : `pdftk` jika muncul pdftk command instructions berarti pdftk telah berhasil terpasang di Linux anda <!-- more -->



# Encrypt





    pdftk <source>.pdf output <destination>.pdf userpw <password>



contoh:



    pdftk plain.pdf output pass.pdf userpw rahasia




<table >

<tr >
  Kode          
  Keterangan                                                    
</tr>

<tbody >
<tr >

<td >plain.pdf    
</td>

<td >nama file sumber yang tidak terpassword            
</td>
</tr>
<tr >

<td >pass.pdf    
</td>

<td >nama file hasil enkripse yang sudah terpassword
</td>
</tr>
<tr >

<td >rahasia      
</td>

<td >passwordnya                                                        
</td>
</tr>
</tbody>
</table>





# Decrypt



Ini adalah kebalikan cara di atas



    pdftk <source>.pdf input <password> output <destination>.pdf




contoh:



    pdftk pass.pdf input_pw rahasia output plain.pdf



<table >

<tr >
  Kode
  Keterangan
</tr>

<tbody >
<tr >

<td >pass.pdf
</td>

<td >nama file sumber yang ada password
</td>
</tr>
<tr >

<td >out.pdf
</td>

<td >nama file hasil dekripsi yang sudah dihilangkan passwordnya
</td>
</tr>
<tr >

<td >rahasia
</td>

<td >passwordnya
</td>
</tr>
</tbody>
</table>

Nonton Videonya
