---
author: ucup
comments: true
date: 2015-08-08 03:15:29+00:00
layout: article
slug: cara-fix-lua-error-wireshark-root-mode
title: 'Cara Fix lua error: Wireshark root mode'
wordpress_id: 949
categories:
- Kali Linux
- Tips & Trik
tags:
- Kali
- Kali Linux
- Linux
- Wireshark
---

Tool wireshark ini sangat populer di dalam analisis keamanan jaringan.. Sayangnya jika kita menggunakan Kali Linux yang secara default masuk ke user root akan mucul pesan _lua error : bla..bla..bla.. .. _untuk menghilangkan pesan error ini ikuti caranya guampangg banget:

di terminal:



    cd /usr/share/wireshark





    nano init.lua



line #29 edit:



    disable_lua = true



Selesai.
