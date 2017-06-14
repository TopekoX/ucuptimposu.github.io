---
layout: article
title: Membuat Grafik Garis (Line Chart) Dengan Chartjs + PHP + MySQL
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
date: 2017-06-11T05:52:44-04:00
---

Diartikel sebelumnya saya sudah membahas [membuat grafik berbasis web dengan Chart.JS](/membuat-grafik-chart-dengan-chartjs/), dan [membuat grafik batang dengan PHP + MySql](/membuat-grafik-batang-dengan-chartjs-php-mysql/) di artikel ini saya akan membahas membuat grafik garis dengan Chart.JS yang sumber datanya berasal dari database MySQL dengan menggunakan PHP (untuk bahasa pemrograman lain tinggal manyesuaikan saja).

### Tools yang digunakan

* PHP
* MySQL / MariaDB
* Chart.JS

## Buat tabel

```sql
CREATE TABLE "Penjualan" (
  "NamaProduk" VARCHAR(45) NULL,
  "Quartal1" INT NOT NULL,
  "Quartal2" INT NOT NULL,
  "Quartal3" INT NOT NULL);

```

## Insert Data

```sql

 INSERT INTO `Penjualan` VALUES 
 ("Samsung",100,200,80),
 ("Apple",60,150,180),
 ("Motorola",50,90,120);

```

 <center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


## Load data

Berikutnya buat file PHP untuk menampilkan datanya dalam bentuk chart. Misal kita kasi nama filenya `index.php` :

```html
<html>
  <head>
    <meta charset="utf-8">
    <title>Demo Grafik Garis</title>
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

    <?php
    $koneksi     = mysqli_connect("localhost", "root", "xxxxxx", "bdi");
    $penjualan      = mysqli_query($koneksi, "SELECT NamaProduk, Quartal1, Quartal2, Quartal3 FROM Penjualan");
    $samsung      = mysqli_query($koneksi, "SELECT NamaProduk, Quartal1, Quartal2, Quartal3 FROM Penjualan WHERE NamaProduk='Samsung'");
    $apple      = mysqli_query($koneksi, "SELECT NamaProduk, Quartal1, Quartal2, Quartal3 FROM Penjualan WHERE NamaProduk='Apple'");
    $motorola      = mysqli_query($koneksi, "SELECT NamaProduk, Quartal1, Quartal2, Quartal3 FROM Penjualan WHERE NamaProduk='Motorola'");

     ?>

      	<script  type="text/javascript">

    	  var ctx = document.getElementById("demobar").getContext("2d");
    	  var data = {
    	            labels: ["Quartal1","Quartal2","Quartal3"],
    	            datasets: [
    	            {
    	              label: "Samsung",
                    fill: false,
                    lineTension: 0.1,
                    backgroundColor: "rgba(59, 100, 222, 1)",
                    borderColor: "rgba(59, 100, 222, 1)",
                    pointHoverBackgroundColor: "rgba(59, 100, 222, 1)",
						        pointHoverBorderColor: "rgba(59, 100, 222, 1)",
    	              data: [<?php while ($p = mysqli_fetch_array($samsung)) { echo '"' . $p['Quartal1'] . '","' . $p['Quartal2'] . '","' . $p['Quartal3'] . '",';}?>]
    	            },
                  {
    	              label: "Apple",
                    fill: false,
                    lineTension: 0.1,
                    backgroundColor: "rgba(203, 222, 225, 0.9)",
                    borderColor: "rgba(203, 222, 225, 0.9)",
                    pointHoverBackgroundColor: "rgba(203, 222, 225, 0.9)",
						        pointHoverBorderColor: "rgba(203, 222, 225, 0.9)",
    	              data: [<?php while ($p = mysqli_fetch_array($apple)) { echo '"' . $p['Quartal1'] . '","' . $p['Quartal2'] . '","' . $p['Quartal3'] . '",';}?>]
    	            },
                  {
    	              label: "Motorola",
                    fill: false,
                    lineTension: 0.1,
                    backgroundColor: "rgba(201, 29, 29, 1)",
                    borderColor: "rgba(201, 29, 29, 1)",
                    pointHoverBackgroundColor: "rgba(201, 29, 29, 1)",
						        pointHoverBorderColor: "rgba(201, 29, 29, 1)",
						        data: [<?php while ($p = mysqli_fetch_array($motorola)) { echo '"' . $p['Quartal1'] . '","' . $p['Quartal2'] . '","' . $p['Quartal3'] . '",';}?>]
    	            }
    	            ]
    	            };

    	  var myBarChart = new Chart(ctx, {
    	            type: 'line',
    	            data: data,
    	            options: {
    	            barValueSpacing: 20,
    	            scales: {
    	              yAxes: [{
    	                  ticks: {
    	                      min: 0,
    	                  }
    	              }],
    	              xAxes: [{
    	                          gridLines: {
    	                              color: "rgba(0, 0, 0, 0)",
    	                          }
    	                      }]
    	              }
    	          }
    	        });
    	</script>

  </body>
</html>
```

Hasilnya :

![Grafik Line](/images/chartjs/linechart.png)

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

_Download Project : [DemoChartLine.zip](http://j.gs/97ht)_