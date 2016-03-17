---
comments: true
date: 2009-11-06 09:35:00+00:00
layout: article
title: Membuat User baru di MySql
categories: mysql
tags: mysql
ads: true
image:
  feature: 
  teaser:  mysql-maria.jpg
---

Selain kita bisa login sebagai root(super user) kita juga bisa membuat user sendiri di database MySql.

caranya pertama login sebagai root(pastinya)

seandainya kita ingin membuat user dengan nama `aco` dan dengan password `adadeh` maka kita ketik:

```sql
mysql> create user 'aco'@'localhost' identified by 'adadeh';
```

maka kita sudah membuat user bernama aco dan passwordnya adadeh
untuk memberi akses sepenuhnya kepada user aco maka ketik

```sql
mysql> GRANT ALL PRIVILEGES ON *.* TO 'aco'@'localhost' WITH GRANT OPTION;
```

sekarang login kembali dengan mengetik

```
mysql -u aco -p
Enter password:
```

