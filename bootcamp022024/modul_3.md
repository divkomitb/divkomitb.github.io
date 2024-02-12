---
title: Modul 3 - Speedrun Perkenalan JavaScript
---

Dalam *web development*, kamu mendapatkan HTML, CSS, dan JavaScript (JS). Sederhananya, HTML adalah untuk konten web, CSS untuk *layout* dan *style* web, dan JavaScript untuk BERINTERAKSI dengan web.

Saat kamu nge-*hover* *thumbnail* di YouTube, sehingga nge-*play* *preview* kecil-kecilan? Itu semua adalah JavaScript.


## Sejarah dan Perkembangan JavaScript

JavaScript dibuat dengan tujuan awal agar website dapat dibuat menjadi lebih interaktif. JavaScript termasuk ke dalam kategori *scripting language*, sehingga kode tidak perlu dikompilasi agar bisa dijalankan. Terdapat *interpreter* untuk menginterpretasi kode -- browser yang nge-*render* website yang kita lihat dan gunakan sehari-hari.

Jika program Python dijalankan saat `python program.py` dijalankan di *command line*, program JavaScript dijalankan tiap suatu *webpage* di-*refresh*.

Terdapat dua lingkungan umum untuk menjalankan JavaScript, yaitu browser dan Node.js. Modul ini hanya membahas JavaScript di browser.


## Bagaimana JavaScript berinteraksi dengan Konten

Salah satu dari sekian banyak *HTML method* di JavaScript adalah `getElementById()`. 

Pada contoh di bawah, JavaScript "mencari" elemen HTML (dengan `id="demo"`), lalu mengubah konten elemen (`innerHTML`) menjadi "Hello JavaScript":

```javascript
document.getElementById("demo").innerHTML = "Hello JavaScript";
```

Ia juga dapat berinteraksi dengan atribut, contohnya:

```html
<button onclick="document.getElementById('myImage').src='lampu_nyala.gif'">
  Nyalakan lampu
</button>

<img id="myImage" src="lampu_mati.gif" style="width:100px">

<button onclick="document.getElementById('myImage').src='lampu_mati.gif'">
  Matikan lampu
</button>
```

Dengan JavaScript, kamu dapat berinteraksi dengan web untuk mengubah *styling*-nya (konfigurasi CSS).

```html
<p id="iniText">
  Iya betul ini text.
</p>
```

Contohnya, untuk berinteraksi dengan `<p>` di atas,

```javascript
document.getElementById("iniText").style.fontSize = "35px";
```

atau untuk menyembunyikan

```javascript
document.getElementById("iniText").style.display = "none";
```

## Menambahkan JavaScript ke Dokumen HTML
Ketika mengimplementasikan JavaScript ke dalam dokumen HTML, masukkan ke dalam tag `script` di `head` atau `body`. Jika menggunakan `<script>`, disarankan untuk menaruhnya di bagian paling bawah `body` untuk meningkatkan kecepatan *rendering*, karena proses *rendering* browser akan menjadi lebih lama apabila mesti menginterpretasi isi `script` terlebih dahulu. 

Secara umum, dokumen HTML akan berbentuk seperti

```html
<!DOCTYPE HTML>
<html>
  <head>
    <title>Title</title>
    ...
  </head>
  <body>
    ...
    ...

    <script>
      ...
    </script>
  </body>
</html>
```

Untuk menulis *script* di file terpisah, contohnya yang file-nya bernama `myScript.js`, ganti `<script> ... </script>` dengan:

```html
<script src="myScript.js"></script>
```

Untuk mencoba contoh `getElementById()` dari atas:

```html
<!DOCTYPE HTML>
<html>
  <head>
    <title>Hello, HTML!</title>
  </head>
  <body>
    <h1 id="demo">Hello, HTML!</h1>
    <p>Lorem ipsum ...<p>

    <h1>Goodbye!</h1>

    <script>
      document.getElementById("demo").innerHTML = "Hello JavaScript";
    </script>
  </body>
</html>
```

## Menjalankan JavaScript menggunakan *Inspect Element*
Buka *Inspect Element* lalu cari tab *Console*. Masukkan kode yang ingin dijalankan.

***Warning***: [Salah satu bentuk penipuan adalah menyuruh seseorang untuk menjalankan kode *harmful* via *console* ini](https://en.wikipedia.org/wiki/Self-XSS), jadi jangan mudah percaya.

## Variabel JavaScript
Saat menulis program, kita menginstruksikan komputer tentang cara memproses informasi, seperti menampilkan teks di layar atau melakukan operasi perhitungan. Untuk mempermudah pengelolaan dan pengambilan data, variabel digunakan untuk menyimpan nilai atau informasi dalam program.

Dalam bahasa pemrograman JavaScript, ada tiga cara untuk mendeklarasikan variabel, yaitu dengan menggunakan kata kunci var, let, dan const. Pada versi ECMAScript 2015 (ES6), metode deklarasi variabel dengan `let` dan `const` diperkenalkan sebagai pengganti `var`, yang dianggap kontroversial dan dapat menyebabkan *bug*.

```javascript
let x;
x = 6;
const y = 100;
y = 200; // error
```

Variabel yang dideklarasikan menggunakan `var` selalu memiliki *scope* global.
Variabel yang dideklarasikan dengan `var` TIDAK bisa memiliki *block scope*, contohnya:

```javascript
function myFunction(a, b) {
  var iniVar = 1;
  let iniLet = 2;
  const iniConst = 3;

  return a * b;
}

const x = iniVar; // var bisa diakses walau diluar block function, yg laen kagak
```

## Fungsi (*Functions*)
Di JavaScript, kita dapat menggunakan fungsi atau *functions* (sama seperti di Python dan C). Kita bisa memanggil mereka sesuai keperluan dan memanfaatkan mereka untuk menulis kode yang lebih *compact*, sehingga programnya menjadi lebih kecil (dan bisa jadi lebih cepat.

Fungsi JavaScript dibuat dengan menggunakan keyword `function` yang diikuti nama dan tanda kurung `()`. Tanda kurung ini dapat berisi nama parameter yang dipisahkan oleh tanda koma: `(parameter1, parameter2, ...)`

Kode yang akan dieksekusi oleh fungsi ditempatkan di dalam *curly brackets*: `{}`

Berikut adalah deklarasi fungsi JavaScript secara umum:

```javascript
function name(parameter1, parameter2, parameter3) {
  // code to be executed
}
```

Fungsi dapat di-*trigger* oleh *event* (seperti nge-*hover* *thumbnail*), dipanggil oleh *script*, atau diinisiasi secara otomatis dengan memanggil dirinya sendiri.

Ketika ditemukan pernyataan `return` di JavaScript, eksekusi fungsi dihentikan. Nilai yang dispesifikan pada pernyataan `return` dikembalikan ke "*caller*".

```javascript
// Fungsi dipanggil, nilai return bakal berakhir di x
let x = myFunction(4, 3);
document.getElementById("iniText").innerHTML = x;

function myFunction(a, b) {
// Fungsi mengembalikan hasil perkalian a dan b
  return a * b;
}
```

## *Further reading*
[Tutorial JavaScript sebagai bahasa pemrograman] yang lebih general di Mozilla Developer Network. Lebih ke menjelaskan *pure JavaScript* daripada menjelaskan JavaScript sebagai alat untuk memanipulasi elemen HTML.

[Dokumentasi JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference) di Mozilla Developer Network.
