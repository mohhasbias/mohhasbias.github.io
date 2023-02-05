---
title: "Apa itu VueJS?"
description: "Berkenalan dengan VueJS"
pubDate: "Jan 06 2019"
# heroImage: "/placeholder-hero.jpg"
---

# Prasyarat

1.  Pengetahuan dan pengalaman tentang [dasar-dasar HTML](https://www.w3schools.com/html/html_basic.asp)
2.  Pengetahuan dan pengalaman tentang [Web Server](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server)
3.  Pengetahuan dan pengalaman tentang [dasar-dasar Javascript](http://rachelnabors.com/javascript-for-designers/)

# Tools

1.  [Visual Studio Code (ver 1.30.1)](https://www.w3schools.com/html/html_basic.asp)
2.  [Fenix Web Server (ver 2.0)](https://github.com/coreybutler/fenix) or [live-server](https://www.npmjs.com/package/live-server)

# TLDR

VueJS posisinya seperti [jQuery](https://jquery.com/). Berfungsi sebagai DOM Manipulator.  
Berbeda dengan jQuery, dimana jQuery merupakan library sedangkan VueJS adalah framework.

Bertujuan untuk menyediakan fitur-fitur yang belum disediakan oleh vanilla javascript.  
Vanilla Javascript adalah istilah untuk javascript bawaan browser.

# Mengapa VueJS

VueJS lahir karena sebuah kebutuhan. Kebutuhan untuk membuat custom User Interface (UI). Untuk bisa memahami kebutuhan yang dimaksud, kembali pada bentuk dasar web.

# Bagaimana bentuk dasar web?

Bentuk dasar web adalah berupa sebuah file dan sebuah aplikasi.  
File yang dimaksud adalah file yang berakhiran `.html`.  
Aplikasi yang dimaksud adalah browser.

berikut adalah contoh dasar file `.html`

`index.html`
```html
<!DOCTYPE html>  
<html>  
<head>  
  <meta charset="utf-8" >  
  <title>Hello</title>  
</head>  
<body>  
  <div>  
    Hello World  
  </div>  
</body>  
</html>  
```

Ini adalah bentuk dasar dari file .html. Salah satu ciri khasnya adalah tidak ada perubahan dari isi selama file ini ditampilkan di browser. Meskipun di reload bolak-balik.

Sifat ini disebut dengan halaman statis.

Dengan adanya javascript, sebuah file html bisa berubah menjadi dinamis. Contohnya kode berikut  

`current-time.html`
```html
<!DOCTYPE html>  
<html>  
<head>  
  <meta charset\="utf-8" />  
  <title>Hello</title>  
</head>  
<body>  
  <div>  
    Hello World<br>  
    Current Time is <span id="current-time"></span>  
  </div>  
  <script>  
    function getCurrentTime() {  
      return (new Date()).toUTCString()  
    }  
  
    document.getElementById('current-time')  
        .innerHTML = getCurrentTime()  
  </script>  
</body>  
</html>  
```

Di kode ini, digunakan elemen html `span` untuk menampilkan “current time”. berpasangan dengan perintah html `innerHTML`. Jadi di sini, Javascript digunakan untuk meng-update html element, biasanya disebut juga dengan DOM element.

setiap kali di-reload, file ini akan menampilkan perubahan konten sesuai perubahan waktu.

dengan javascript, tampilan waktu bisa di-update sesuai interval tertentu tanpa harus reload browser.  
berikut contoh kodenya  

current-time-auto-update.html

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  
17  
18  
19  
20  
21  
22  
23  

<!DOCTYPE html>  
<html\>  
<head\>  
  <meta charset\="utf-8" />  
  <title\>Hello</title\>  
</head\>  
<body\>  
  <div\>  
    Hello World  
    Current Time is <span id\="current-time"\></span\>  
  </div\>  
  <script\>  
    function getCurrentTime() {  
      return (new Date()).toUTCString()  
    }  
  
    setInterval(() => {  
      document.getElementById('current-time')  
        .innerHTML = getCurrentTime()  
    }, 1000)  
  </script\>  
</body\>  
</html\>  

Di kondisi kode seperti inilah, VueJS bisa memberikan bentuk kode dari perspektif yang berbeda, seperti kode berikut  

current-time-vuejs.html

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  
17  
18  
19  
20  
21  
22  
23  
24  
25  
26  
27  
28  
29  
30  
31  
32  
33  
34  
35  

<!DOCTYPE html>  
<html\>  
<head\>  
  <meta charset\="utf-8" />  
  <title\>Hello</title\>  
</head\>  
<body\>  
  <div id\="app"\>  
    Hello World  
    Current Time is <span\>{{ currentTime }}</span\>  
  </div\>  
  <script src\="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"\></script\>  
  <script\>  
    function getCurrentTime() {  
      return (new Date()).toUTCString()  
    }  
  
    const app = new Vue({  
      el: '#app',  
      data: {  
        currentTime: getCurrentTime()  
      },  
      methods: {  
        updateTime: function() {  
          this.currentTime = getCurrentTime()  
        }   
      }  
    })  
  
    setInterval(() => {  
      app.updateTime()  
    }, 1000)  
  </script\>  
</body\>  
</html\>  

secara hasil atau tampilan di browser, keduanya menghasilkan output yang sama.  
perbedaannya terdapat pada kode yang dibuat. perhatikan saat kedua kode tersebut dibandingkan.

![Komparasi JS dengan VueJS](/assets/js-vs-vuejs.png)
*Komparasi JS dengan VueJS*

Secara jumlah baris menjadi lebih banyak. Tapi secara struktur pemograman, bagian-bagian dari kode tersebut terlihat lebih jelas. Kodenya menjadi lebih mudah dipahami.

Dengan struktur yang baru ini, terdapat cara baca dari kode tersebut seperti gambar berikut.  
[![Cara baca VueJS](/2019/01/06/Apa-itu-VueJS-1/cara-baca-vuejs.png)](https://mohhasbias.github.io/2019/01/06/Apa-itu-VueJS-1/cara-baca-vuejs.png "Cara baca VueJS")Cara baca VueJS  
![Cara baca VueJS](/assets/cara-baca-vuejs.png)
*Cara baca VueJS*

Cara bacanya sebagai berikut:

1.  VueJS diminta untuk mengelola DOM element dengan id `app`.  
    pemilihan DOM element dilakukan menggunakan CSS Selector, dalam hal ini `#app`. yang artinya, apapun yang ada di dalam element tersebut diperlakukan sebagai template.
2.  Salah satu elemen dari `#app` berisi elemen `span` yang memiliki konten berupa teks dengan dua kurawal keriting (curly braces). Ini artinya, Vue diminta untuk menampilkan isi dari data `currentTime`
3.  Terdapat perintah `app.updateTime()`. `app` di sini merujuk pada elemen yang dikelola oleh Vue. Dan melalui `app`, fungsi apapun yang tertulis di `methods` bisa dipanggil.
4.  Fungsi yang didaftarkan di `methods` bisa digunakan untuk mengutak-atik data dengan menggunakan perintah `this`. Dalam hal ini `this.currentTime` merujuk pada variable `currentTime` pada bagian `data`.

4 hal tersebut mewakili konsep [enkapsulasi](https://www.thoughtco.com/data-encapsulation-2034263), yaitu mengumpulkan beberapa hal yang berbeda tapi berkaitan dalam satu tempat. Ada 3 hal utama yang dikumpulkan oleh VueJS, yaitu `el`, `data`, dan `methods`. Hal ini mewakili 3 bagian utama dari halaman web ini. `el` mewakili DOM element dalam hal ini ada element dengan id `app` yang diwakili oleh css selector `#app`. Data mewakili data yang bisa ditampilkan di html. Diwakili oleh `{{ currentTime }}` pada html. Bentuk `{{ }}` merupakan perintah untuk menampilkan data. Adanya bentuk ini merupakan ciri khas dari [HTML template](https://colorlib.com/wp/top-templating-engines-for-javascript/) Kemudian ada `methods` dalam hal ini adalah fungsi `updateTime`.
