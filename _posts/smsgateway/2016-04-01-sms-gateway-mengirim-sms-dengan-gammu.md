---
layout: article
title: SMS Gateway Mengirim SMS Dengan Gammu
modified:
categories: smsgateway
excerpt:
tags: []
comments: true
ads: true
image:
  feature:
  teaser:
  thumb:
date: 2016-04-01T12:57:49+08:00
---

Kita akan coba mengirim sms dengan Gammu dengan isi pesan "Cek Dong..." ke nomor +6281234567890

```
ucup@timposu:~$ gammu-smsd-inject -c /etc/smsdrc TEXT +6281234567890 -text "Cek Dong..."
```
Jika tidak ada error pesan akan terkirim ke nomor tujuan dan tersimpan di database `smsgateway`.
