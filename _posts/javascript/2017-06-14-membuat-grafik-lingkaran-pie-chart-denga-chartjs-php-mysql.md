---
layout: article
title: Membuat Grafik Lingkaran (Pie Chart) Denga Chartjs + PHP + MySQL
modified:
categories: javascript
excerpt:
tags: [chart, chartjs, javascript, php, mysql]
comments: true
ads: true
image:
  feature:
  teaser: chartjs.png
  thumb: chartjs.png
date: 2017-06-11T06:04:16-04:00
---

Diartikel sebelumnya saya sudah membahas [membuat grafik berbasis web dengan Chart.JS](/membuat-grafik-chart-dengan-chartjs/), [membuat grafik batang dengan PHP + MySql](/membuat-grafik-batang-dengan-chartjs-php-mysql/) dan [membuat grafik garis dengan PHP + MySql](/membuat-grafik-garis-line-chart-denga-chartjs-php-mysql/), dan di artikel ini saya akan membahas membuat grafik lingkaran dengan Chart.JS yang sumber datanya berasal dari database MySQL dengan menggunakan PHP (untuk bahasa pemrograman lain tinggal manyesuaikan saja).

### Tools yang digunakan

* PHP
* MySQL / MariaDB
* Chart.JS

## Buat tabel

```sql
CREATE TABLE smartphone (
  ID INT NOT NULL AUTO_INCREMENT,
  Merk VARCHAR(45) NOT NULL,
  Penjualan INT NOT NULL,
  PRIMARY KEY ('ID'));

```


## Insert Data


```sql
INSERT INTO `smartphone` (`Merk`, `Penjualan`) VALUES ('Samsung', '100');
INSERT INTO `smartphone` (`Merk`, `Penjualan`) VALUES ('Apple', '89');
INSERT INTO `smartphone` (`Merk`, `Penjualan`) VALUES ('Sony', '67');
INSERT INTO `smartphone` (`Merk`, `Penjualan`) VALUES ('Motorola', '72');
INSERT INTO `smartphone` (`Merk`, `Penjualan`) VALUES ('Oppo', '88');
INSERT INTO `smartphone` (`Merk`, `Penjualan`) VALUES ('Xiaomi', '80');

```

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## Load data

Berikutnya buat file PHP untuk menampilkan datanya dalam bentuk chart. Misal kita kasi nama filenya `index.php` :

```html

<?php
$koneksi     = mysqli_connect("localhost", "root", "xxxxxx", "latihan");
$penjualan      = mysqli_query($koneksi, "SELECT Penjualan FROM smartphone order by ID asc");
$merek = mysqli_query($koneksi, "SELECT Merk FROM smartphone order by ID asc");
 ?>
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Demo Grafik Lingkaran</title>
    <script src="js/Chart.js"></script>
    <style type="text/css">
            .container {
                width: 50%;
                margin: 15px auto;
            }
    </style>
  </head>
  <body>

    <div class="container">
            <canvas id="demobar" width="100" height="100"></canvas>
    </div>

      	<script  type="text/javascript">

    	  var ctx = document.getElementById("demobar").getContext("2d");
    	  var data = {
    	            labels: [<?php while ($p = mysqli_fetch_array($merek)) { echo '"' . $p['Merk'] . '",';}?>],
    	            datasets: [
    	            {
    	              label: "Penjualan Smartphone",
    	              data: [<?php while ($p = mysqli_fetch_array($penjualan)) { echo '"' . $p['Penjualan'] . '",';}?>],
                    backgroundColor: [
                      "rgba(59, 100, 222, 1)",
                      "rgba(203, 222, 225, 0.9)",
                      "rgba(102, 50, 179, 1)",
                      "rgba(201, 29, 29, 1)",
                      "rgba(81, 230, 153, 1)",
                      "rgba(246, 34, 19, 1)"]
    	            }
    	            ]
    	            };

    	  var myBarChart = new Chart(ctx, {
    	            type: 'pie',
    	            data: data,
    	            options: {
                    responsive: true
    	          }
    	        });
    	</script>

  </body>
</html>
```

Berikut hasilnya:

![Grafik Batang](/images/chartjs/chartpie.png)


<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

_Download Project : [DemoChartPie.zip](http://adf.ly/1mwuZx)_
