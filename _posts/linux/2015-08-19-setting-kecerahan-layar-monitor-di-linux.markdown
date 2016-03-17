---
comments: true
date: 2015-08-19 04:31:49+00:00
layout: article
slug: setting-kecerahan-layar-monitor-di-linux
title: Setting Kecerahan Layar Monitor di Linux
categories: linux
tags: [linux, tips]
ads: true
image:
  feature: 
  teaser: leds_photo.jpg
---

## Install xbacklight



Install xbcklight di Debian base



    sudo apt-get install xbacklight



Install xbcklight di Redhat base



    yum install xbacklight





## Atur tingkat kecerahan



setting brightness  dari 1s/d 100

contoh kecerahan 50%



     xbacklight -set 50



tinggal di atur di startup application nya... biar tiap boot kecerahannya tidak berubah
