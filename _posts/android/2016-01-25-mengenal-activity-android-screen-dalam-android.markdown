---
layout: article
title: "Mengenal Activity Android (Screen dalam Android)"
date: 2016-01-25 23:24:46 +0800
comments: true
categories: android
tags: [Android, Pemrograman Android, Android Studio, Java]
ads: true
---

Di dalam Android, _Activity_ merupakan sebuah _Screen_ / tampilan, dan biasanya aplikasi terdiri dari beberapa screen misalnya terdiri dari tampilan home aplikasi, about atau tampilan status aplikasi lainnya.

Pada tutorial ini kita akan belajar bagaimana berinteraksi antar activity (screen), ketika tombol diklik maka akan pindah ke activity(screen) lainnya.

> _Tutorial ini menggunakan Android Studio IDE_


#  Buat Project

Bisa lihat [disini step nya](/membuat-aplikasi-android-hello-world/)

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

#  Buat file layout XML

Karena kita akan menggunakan 2 screen activity maka kita akan membuat 2 file `.xml` di dalam direktori project `res/layout`.

  1. `res/layout/main1.xml` - Layout Screen 1
  2. `res/layout/main2.xml` - Layout Screen 2

<!--more-->

file `main1.xml`

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent">

    <TextView
        android:id="@+id/text"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Ini adalah Layout 1"/>

    <Button
        android:id="@+id/tombol"
        android:layout_width="fill_parent"
        android:layout_height="wrap_content"
        android:text="Klik untuk pindah layout"/>

</LinearLayout>
```

file `main2.xml`

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent">

    <TextView
        android:id="@+id/text"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Selamat datang di Layout 2"/>

</LinearLayout>
```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>	

# Membuat Activities

Untuk berhubungan antar layout activity gunakan:

```java
Intent intent = new Intent(context, anotherActivity.class);
startActivity(intent);
```

Buat 2 class Activities

  1. `App1.java` -> `res/layout/main1.xml`
  2. `App2.java` -> `res/layout/main2.xml`

File `App1.java`

```java
package com.timposu.demodatabase;

import android.app.Activity;
import android.content.Context;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

/**
 * Created by ucup on 1/26/16.
 */
public class App1 extends Activity {

    Button tombol;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.main1);
        addListenerButton();
    }

    public void addListenerButton(){
        final Context context = this;
        tombol = (Button) findViewById(R.id.tombol);

        tombol.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent = new Intent(context, App2.class);
                startActivity(intent);
            }
        });
    }
}
```

File `App2.java`

```java
package com.timposu.demodatabase;

import android.app.Activity;
import android.os.Bundle;

/**
 * Created by ucup on 1/26/16.
 */
public class App2 extends Activity{
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.main2);
    }
}
```

# Ubah file AndroidManifest.xml

Kita perlu memasukan activities ke dalam file `AndroidManifest.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.timposu.demodatabase">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity android:name=".App1">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
        <activity android:name=".App2"/>
    </application>

</manifest>
```

# Running

Running Aplikasi

* App1 / Main1 layout. kliktombol untuk pindah layout

![](http://i63.tinypic.com/i2ufxk.jpg)

* App2 / Main2 layout

![](http://i66.tinypic.com/1j9477.jpg)


### Referensi

* [Android Developer](http://developer.android.com/guide/topics/fundamentals/activities.html)
