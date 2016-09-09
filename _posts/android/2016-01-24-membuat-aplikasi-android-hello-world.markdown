---
layout: article
title: "Membuat aplikasi Android 'Hello World' dengan Android Studio"
date: 2016-01-24 13:27:04 +0800
comments: true
categories: android
tags: [android, pemrograman android, android studio, java]
ads: true
---



Pada tutorial kali ini kita akan mulai belajar tentang Pemrograman Android. Sebelum kita memulai apa yang perlu kita persiapkan

![](http://i68.tinypic.com/1zei2vd.jpg)

* Sudah __menguasai bahasa pemrograman Java__ minimal Java SE karena Google menjadikan bahasa Java sebagai bahasa resmi pengembangan aplikasi Android.
* Punya komputer PC atau laptop yang cukup mumpuni karena kita akan menggunakan IDE [Android Studio](http://developer.android.com/sdk/index.html) yang cukup makan resource yang banyak.
* Ketekunan dan pantang menyerah (wajib untuk semua programer).

{% include toc.html %}

## Tools Yang dibutuhkan

* [Java Development Kit](http://www.oracle.com/technetwork/java/javase/downloads/) 1.7 atau yang lebih tinggi.
* [Android Studio](http://developer.android.com/sdk/index.html) : IDE yang digunakan untuk membuat aplikasi Android
* SDK : Sekumpulan library yang digunakan untuk membuat aplikasi android
* AVD : Emulator

<!-- more -->

## Step by Step

1. Install JDK
2. Install [Android studio](http://developer.android.com/sdk/index.html).
3. Install Android SDK
4. Membuat Project Android
5. Membuat Android Virtual Device (AVD)
6. Coding...
7. Running..

## 1. Instal JDK

Untuk cara install bisa lihat [di sini](/blog/2015/09/07/install-java-development-kit/) atau tanya aja om [google](http://google.com).

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## 2. Install Android Studio

Download [Android Studio](http://developer.android.com/sdk/index.html), untuk cara installnya berbeda di setiap Sistem Operasi, untuk petunjuk instalasi di OS yang anda pakai bisa dilihat [di sini](http://developer.android.com/sdk/installing/index.html?pkg=studio).

Jika anda menggunakan Windows download Android Studio yang versi bundle, karena paketnya sudah sekaligus dengan Android SDK cuma memang filenya sangat besar untuk saat ini saja filenya hampir 1gb, jadi ini peringatan juga buat golongan fakir bandwidth. Untuk Linux pengalaman saya Android Studionya terpisah dengan SDK nya, jadi didownload secara terpisah.

## 3. Install Android SDK

Untuk yang pakai Windows dan sudah menggunakan Android Sudio versi bundle SDK nya sudah include.

Download [Android SDK](http://developer.android.com/sdk/index.html), extract filenya.

File SDK berada dalam direktori `tools/`, eksekusi file `android` untuk melihat SDK yang ada.

Untuk selengkapnya lihat [di sini](http://developer.android.com/sdk/installing/adding-packages.html).

![](http://i65.tinypic.com/16m9emx.jpg "android sdk manager")

pilih paket versi android/API yang diinginkan, saran saya cukup install versi terbaru dan versi android yang lama yang anda inginkan, dan yang terpenting SDK Platform dan Google APIs yang diinstall sesuaikan dengan APIs jenis processor aplikasi kita.

## 4. Membuat Project Android

Buka aplikasi Android Studio, pilih _Start a new Android Studio Project_


![](http://i65.tinypic.com/1089yzk.jpg)

Pilih minimum SDK atau versi android yang dingikan disini saya memilih versi android 4.0 ICS spesifikasi minimum aplikasi saya

![](http://i63.tinypic.com/34et0rm.jpg)

Pilih model activity atau layout yang diinginkan, saya memilih __Empty Activity__ untuk tampilan aplikasi saya

![](http://i64.tinypic.com/x0qz2f.jpg)

Beri nama activity tersebut di atas.

![](http://i67.tinypic.com/aubih2.jpg)

Jika berhasil Editor akan terbuka seperti dibawah ini

![](http://i66.tinypic.com/9jj0ht.jpg)

Dan struktur projectnya seperti dibawah ini

![](http://i63.tinypic.com/30igl06.jpg)


## 5. Membuat Android Virtual Device (AVD)

Untuk membuka AVD Manager di android studio bisa dengan cepat melalui icon ![](http://developer.android.com/images/tools/avd-manager-studio.png) yang ada di toolbar, kemudian di AVD Manager buat sebuah virtual device dengan klik __Create Virtual Device__ dan buat sesuai perangkat yang diinginkan , System Image dan nama dari AVD nya yang diinginkann. Jangan lupa pada bagian pemberian nama AVD untuk mencentang _Use Host GPU_ biar emulatornya sedikit lebih ringan, karena menggunakan source GPU dari komputer kita.

Untuk mengujinya klik tombol ![](http://developer.android.com/images/tools/as-run.png) untuk menjalankan emulator virtual device.

![](http://i63.tinypic.com/2z5ke3a.jpg "Running")

## 6. Coding

Secara default Android Studio sudah membuat coding aplikasi Hello World.. kita bisa lihat pada file __activity_main.xml__ yang ada di direktori __layout__.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingBottom="@dimen/activity_vertical_margin"
    android:paddingLeft="@dimen/activity_horizontal_margin"
    android:paddingRight="@dimen/activity_horizontal_margin"
    android:paddingTop="@dimen/activity_vertical_margin"
    tools:context="com.timposu.helloapp.MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!" />
</RelativeLayout>
```
Jika anda ingin mengubah tulisan sesuai keinginan silahkan ganti text string yang ada pada `android:text` di tag widget `TextView`.

File layout di atas akan dipanggil oleh class `MainAcivity.java` melalui method `setContentView(R.layout.activity_main)`

```java
package com.timposu.helloapp;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


## 7. Running

Running aplikasi dengan menekan tombol __Run App__ atau dengan menekan tombol `Shift + F10`

![](http://i68.tinypic.com/1zei2vd.jpg)

### Referensi

[http://developer.android.com/index.html](http://developer.android.com/index.html)
