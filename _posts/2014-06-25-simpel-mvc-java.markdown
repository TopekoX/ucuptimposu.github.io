---
author: ucup
comments: true
date: 2014-06-25 15:12:19+00:00
layout: article
slug: simpel-mvc-java
title: Simpel MVC Java
wordpress_id: 495
categories:
- Java

tags:
- Java
- Java Dasar
- MVC
- Netbeans
---

Nah.... nih saya mau kasi tutorial Java MVC yang simple aja dulu. Sebelumnya pastiin udah ngerti apa itu [MVC](http://timposu.com/apa-itu-mvc/). MVC sekedar mengingatkan berfungsi agar dalam menulis kode program bisa lebih terstruktur  dan rapi. Karena sebagian dari kita mungkin dalam menulis kode program asal programnya jalan.., masalah biasa muncul ketika kita ingin mengubah kode program tersebut.. kadang kita kita pusing untuk mengubah kode tsbt.. karena kode nya gak rapi.. :v

Step 1 buat project di Netbeans IDE atau  eclipse. namanya terserah., nih saya pake nama DemoMVC . Buat 3 paket masing-2 kasi nama Model, View, Controller

![](http://i713.photobucket.com/albums/ww134/upamisterlobal/timposu/mvc1_zps0e86ea72.png)





  1. Buat Data Entity class dulu di bagian.. `model `. karena ini  yang simpel kita buat  1 data aja yang mau di proses contohnya "nama"





    <code>/**
    *=========================================================
    * Program ini dibuat oleh Ucup Topeko
    * URL: www.timposu.com
    * email : acobunglon@gmail.com
    * Silahkan kode Java ini dipelajari / disebarkan
    * secara bebas...
    *==========================================================
    */

    package com.timposu.model;

    /**
    *
    * @author ucup
    */
    public class Nama {

    private String nama;

    public String getNama() {
    return nama;
    }

    public void setNama(String nama) {
    this.nama = nama;
    }

    }
    </code>







  1. Buat Form di paket **model** di sbb..



![](http://i713.photobucket.com/albums/ww134/upamisterlobal/timposu/mvc1_zps36d2e23d.png)

ubah nama variable JTextField jadi `txtNama` dan JButton jadi `buttonPesan` ... atau ganti sesuai selera...

buat setter dan getter nya ..di bag. sourcenya



    <code>public JButton getButtonPesan() {
    return buttonPesan;
    }

    public JTextField getTxtNama() {
    return txtNama;
    }

    </code>



fungsinya agar bisa di akses kelas luar entar sama controller nya..





  1. Buat **Controller** nya..





    <code>/**
    *=========================================================
    * Program ini dibuat oleh Ucup Topeko
    * URL: www.timposu.com
    * email : acobunglon@gmail.com
    * Silahkan kode Java ini dipelajari / disebarkan
    * secara bebas...
    *==========================================================
    */

    package com.timposu.controller;

    import com.timposu.model.Nama;
    import com.timposu.view.Form;
    import javax.swing.JOptionPane;

    /**
    *
    * @author ucup
    */
    public class Controller {

    private Form form ;
    private Nama nama;

    public Controller(Form form) {
    this.form = form;
    this.nama = new Nama();
    }

    public void proses(){

    nama.setNama(form.getTxtNama().getText());

    if (nama.getNama().trim().isEmpty()){
    JOptionPane.showMessageDialog(form, "Nama jangan kosong..");
    } else {
    JOptionPane.showMessageDialog(form, "Hai..." + nama.getNama());
    }

    }

    public void clear(){

    form.getTxtNama().setText("");
    form.getTxtNama().requestFocus();

    }
    }

    </code>



Controller ini lah yang berisi semua fungsi yang akan di proses di dalam view nya..
kita akan mengirim objek Form yang ada di view ke controller ini melalui parameter



    <code><br></br>public Controller(Form form) {
    this.form = form;
    //
    }

    </code>







  1. Kembali ke Form tadi, pada bagian view.. di sinilah kita mengirim objek ke controller tadi buat Objek dari Controller





    <code>private Controller controller;
    </code>



terus  inisialisasi



    <code>controller = new Controller(this);
    </code>



kemudian buat action di `buttonPesan` yang isinya sbb:



    <code>controller.proses();
    controller.clear();
    </code>



Running...............

![](http://i713.photobucket.com/albums/ww134/upamisterlobal/timposu/mvc1_zpsfd4f6ea8.png)

Sekilas terlihat Kodenya lebih banyak... tapi metode ini lebih efisien jika kode program anda lebih panjang dan rumit..

[Download Source](http://www.4shared.com/zip/mvfIjlrPba/DemoMVC.html?)
