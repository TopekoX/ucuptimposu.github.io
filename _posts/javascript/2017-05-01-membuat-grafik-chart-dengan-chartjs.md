---
layout: article
title: Membuat Grafik Chart Dengan Chart.js
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
date: 2017-05-01T00:16:21-04:00
---
Ada banyak library yang bisa digunakan untuk membuat chart berbasis javascript misalnya [morrisjs](http://morrisjs.github.io/morris.js/), [flotcharts](http://www.flotcharts.org/), [chart.js](http://www.chartjs.org/),[highcharts](https://www.highcharts.com/) dan masih banyak yang lainnya. Salah satu yang saya sarankan adalah Chart.js.

## Kenapa Harus Chart.js

Beberapa alasan memilih Chart.js

1. Opensource.
2. Sampai posting ini dibuat chart.js sudah mendukung 8 jenis chart dan dapat dikombinasi di antaranya:
   * Line Chart
   * Bar Chart
   * Radar Chart
   * Polar Area Chart
   * Pie & Doughnut Chart
   * Bubble Chart
   * Scatter
   * Horizontal Bar
3. Ukurannya ringan.
4. Berbasis HTML5  Canvas sehingga tidak perlu plugin tambahan dibrowser.
5. Responsive.
6. Interaktif.

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

Untuk dokumentasi library bisa anda lihat di [chartjs.org/docs/](http://www.chartjs.org/docs/).

## Install Chart.js

Cara install Chart.js sangat mudah, cek update terbaru dari [Github project chart.js](https://github.com/chartjs/Chart.js).

Cara pasangnya cukup 2 cara :

a. Panggil librarynya atau menggunakan CDN

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.1.4/Chart.min.js"></script>
```

b.  Panggil data chart di elemen HTML5 `<canvas>`

```html
<canvas id="myChart"></canvas>
```

## Grafik Batang / Bar Chart

Masukan kode Javascript dibawah ini ke tag `<body>` dan jangan lupa panggil di tag `<canvas>` :

```javascript
<canvas id="grafikBatang"></canvas>

<script>
var ctx = document.getElementById("grafikBatang").getContext('2d');
var myChart = new Chart(ctx, {
    type: 'bar',
    data: {
        labels: ["Red", "Blue", "Yellow", "Green", "Purple", "Orange"],
        datasets: [{
            label: '# Jumlah Survei',
            data: [12, 19, 3, 5, 2, 3],
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)',
                'rgba(54, 162, 235, 0.2)',
                'rgba(255, 206, 86, 0.2)',
                'rgba(75, 192, 192, 0.2)',
                'rgba(153, 102, 255, 0.2)',
                'rgba(255, 159, 64, 0.2)'
            ],
            borderColor: [
                'rgba(255,99,132,1)',
                'rgba(54, 162, 235, 1)',
                'rgba(255, 206, 86, 1)',
                'rgba(75, 192, 192, 1)',
                'rgba(153, 102, 255, 1)',
                'rgba(255, 159, 64, 1)'
            ],
            borderWidth: 1
        }]
    },
    options: {
        scales: {
            yAxes: [{
                ticks: {
                    beginAtZero:true
                }
            }]
        }
    }
});
</script>
```

Perhatikan id `canvas` harus sama dengan nama element yang ada di kode Javascript

kode `type: 'bar'` ada jenis grafiknya

kode `labels` pada bagian `data` adalah nama judul datanya

kode `data` pada bagian `data` adalah nilai dari datanya

![Grafik Batang](/images/chartjs/chartjs1.png)

Dokumentasi lengkapnya [disini](http://www.chartjs.org/docs/latest/charts/bar.html)

## Grafik garis / Line

Caranya sama dengan grafik batang yang diubah cukup tipenya 

`type: line`

Contoh

```javascript
<canvas id="grafikBatang"></canvas>

<script>
var ctx = document.getElementById("grafikBatang").getContext('2d');
var myChart = new Chart(ctx, {
    type: 'line',
    data: {
        labels: ["Red", "Blue", "Yellow", "Green", "Purple", "Orange"],
        datasets: [{
            label: '# of Votes',
            data: [12, 19, 3, 5, 2, 3],
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)',
                'rgba(54, 162, 235, 0.2)',
                'rgba(255, 206, 86, 0.2)',
                'rgba(75, 192, 192, 0.2)',
                'rgba(153, 102, 255, 0.2)',
                'rgba(255, 159, 64, 0.2)'
            ],
            borderColor: [
                'rgba(255,99,132,1)',
                'rgba(54, 162, 235, 1)',
                'rgba(255, 206, 86, 1)',
                'rgba(75, 192, 192, 1)',
                'rgba(153, 102, 255, 1)',
                'rgba(255, 159, 64, 1)'
            ],
            borderWidth: 1
        }]
    },
    options: {
        scales: {
            yAxes: [{
                ticks: {
                    beginAtZero:true
                }
            }]
        }
    }
});
</script>
```

![Grafik Batang](/images/chartjs/chartjs2.png)

Demikian beberapa contoh penggunaan Chart.js untuk Contoh lain bisa di lihat [disini](http://www.chartjs.org/docs/latest/getting-started/) 

### Referensi 

[http://www.chartjs.org/](http://www.chartjs.org/)

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>

## Selanjutnya

* [Membuat Grafik Batang Dengan Chartjs + PHP + MySQL](/membuat-grafik-batang-dengan-chartjs-php-mysql/)

* [Membuat Grafik Garis (Line Chart) Dengan Chartjs + PHP + MySQL](/membuat-grafik-garis-line-chart-denga-chartjs-php-mysql/)