---
comments: true
date: 2015-10-15 13:43:33+00:00
layout: article
slug: contoh-aplikasi-ajax-penggunaan-xmlhttprequest
title: Contoh Aplikasi AJAX ( Penggunaan XMLHttpRequest)
categories: artikel
tags: [artikel, ajax, javascript]
ads: true
---

Setelah sedikit mengenal [apa itu AJAX ](/blog/2015/10/14/apa-itu-ajax/)di articleingan ini saya akan memberikan tutorial bagaimana AJAX meload file tanpa melakukan refresh page. Di dalam AJAX kata kuncinya adalah objek XMLHttpRequest. Semua jenis browser modern saat ini mendukung XMLHttpRequest, kecuali browser jadul IE5 dan IE6 (itupun kalo masih ada yang pake).

<!-- more -->


### Fungsi XMLHttpRequest

Nah.. objek XMLHttpRequest ini bekerja untuk melakukan pertukaran data dengan server dibelakang layar dengan tidak mempengaruhi bagian keseluruhan dari halaman web, jadi yang diproses hanya bagian tertentu dari halaman web sehingga tidak melakukan proses reload dari keseluruhan halaman web.



### Membuat XMLHttpRequest

AJAX biasanya disisipkan dalam tag Javascript, karena sesuai namanya AJAX adalah Javasript, atau bisa dibuat di file yang berbeda kemudian di load. Semua jenis browser modern (Chrome, Firefox, Internet Explorer 7+, Safari dan Opera) mendukung XMLHttpRequest.


Cara membuat objek XMLHttpRequest :
`var http = new XMLHttpRequest();`

Untuk browser jadul Internet Explorer 5 dan 6 pake ActiveXObject
`var http = new ActiveXObject("Microsoft.XMLHTTP");`

buat file txt dengan nama _file.txt_, saya tulis dengan kalimat dibawah ini



    Hallooo... BRO....!!!!



Buat file html yang akan meload file text di atas  dengan AJAX .. dengan kode dibawah ini :



``` html
<!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Latihan Ajax</title>
    </head>
    <body>
        Klik tombol untuk load datanya....
        <br/>
            <br/>
                <button onclick="loadFile()">Load data</button>
            <br/>
        <p id="isifile"></p>

        <script>
        function loadFile(){
            var xload;
            if(window.XMLHttpRequest){
                xload = new XMLHttpRequest(); // untuk browser moderen
            }else{
                xload = new ActiveXObject("Microsoft.XMLHTTP"); // untuk browser jadul
            }
            xload.onreadystatechange = function (){
                if(xload.readyState == 4 && xload.status == 200){
                    document.getElementById("isifile").innerHTML = xload.responseText;
                }
            }
            xload.open("GET", "file.txt", true);
            xload.send();
        }
        </script>
    </body>
</html>
```



Kebetulan pada tutorial ini  kedua file di atas saya simpan di folder yang sama pada folder server apache.



Sebaiknya ketika menjalankan aplikasi AJAX  dijalankan di  dalam server.. contoh server apache, tomcat dll.


Download kode [ajax-example.zip](https://dl.dropboxusercontent.com/u/50889496/project/ajax-example.zip)
