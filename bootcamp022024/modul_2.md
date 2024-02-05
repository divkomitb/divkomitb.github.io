---
title: Modul 2 - CSS
---

## Pendahuluan
Informasi website yang di-load dari server biasanya tidak di-load secara serentak, dan seringkali browser mendapatkan informasi HTML suatu website (yang mengatur struktur dan konten) sebelum ia mendapatkan informasi CSS (yang mengatur penampilan). Fenomena di mana browser terkadang sejenak me-render website berdasarkan informasi HTML sebelum memiliki informasi lengkap CSS memiliki istilahnya tersendiri: [*flash of unstyled content* atau FOUC](https://en.wikipedia.org/wiki/Flash_of_unstyled_content). Sejenak, pada jaringan internet yang tidak begitu cepat, user melihat bagaimana suatu website terlihat tanpa CSS.

HTML memberitahu browser elemen apa saja yang ada pada suatu website, tetapi tidak memberikan informasi tentang penampilan visual website tersebut. Untuk mendikte browser bagaimana konten website seharusnya di-render (warna, ukuran, posisi, dan lain sebagainya), perlu digunakan Cascading Style Sheets (CSS). CSS digunakan dengan cara melakukan seleksi kepada aspek-aspek yang ingin diatur, lalu menulis spesifikasi penampilan (*style*) untuk aspek tersebut. 

## Dengan dan Tanpa CSS
Untuk membandingkan bagaimana suatu website terlihat dengan dan tanpa CSS, dapat kembali digunakan *Developer Tools* (Inspect Element dan kawan-kawan) yang ada pada browser. Pada Firefox, klik-kanan > Inspect > Style Editor lalu toggle icon mata di bagian kiri untuk "mematikan" suatu file sumber CSS. Pada Chrome, klik-kanan > Inspect > Sources lalu cari file .css pada bagian kiri, pilih, lalu hapus semua teks. 

![Website XKCD dengan CSS vs tanpa CSS.](https://github.com/divkomitb/divkomitb.github.io/blob/main/assets/xkcd-css.png?raw=true)

Pada gambar di atas, bagian kiri menunjukkan penampilan website dengan CSS (kiri) dan setelah CSS "dimatikan" (kanan).

Dengan "mematikan" CSS, dapat dilihat bahwa webpage xkcd ini terdiri dari navigasi (yang dibuat dengan unordered list ul), gambar logo, deretan teks, sekumpulan link dalam sebuah ul lagi, gambar strip komik xkcd, lalu ul lagi.

Namun, dengan menggunakan CSS, perancang website ini berhasil mengatur ulang posisi tiap elemen sesuai layout yang diinginkan, mengubah warna dan formatting link, membuat item list yang sebelumnya menjalar dari atas ke bawah menjadi menjalar dari kiri ke kanan, dan seterusnya.

## Menambahkan CSS
Ada tiga cara untuk menambahkan CSS, tetapi cara yang paling direkomendasikan adalah menulis kode CSS di file terpisah (contohnya `stylesheet.css`). Lalu, di file HTML utama (sebut saja `index.html`), tambahkan "*link*" ke `stylesheet.css`. 

Untuk melakukan ini, tambahkan kode berikut ke `head` dari `index.html`:

```html
<link rel="stylesheet" href="stylesheet.css" />
```

## Menulis CSS
Diberikan suatu file `index.html` sebagai berikut:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Halo Halo Dunia</title>
    <link rel="stylesheet" href="stylesheet.css" />
  </head>
  <body>

    <header>
      <h1>Halo Halo Dunia</h1>
    </header>

    <nav>
      <ul>
        <li><a href="#">Tentang Dunia</a></li>
        <li><a href="#">Lokasi Dunia</a></li>
      </ul>
    </nav>

    <main>
      <p>
        <a href="https://en.wikipedia.org/wiki/Lorem_ipsum">Lorem ipsum</a> dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
      </p>
      <p>
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
      </p>
      <p>
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </p>
    </main>

    <footer>
      copyleft 2024
    </footer>

  </body>
</html>
```

Karena pada bagian `head` sudah ada kode `<link rel="stylesheet" href="stylesheet.css" />` yang nge-*link* `index.html` ke `stylesheet.css`, kita dapat langsung membuat file `stylesheet.css` dan menulis isinya.

*Syntax* dasar CSS adalah sebagai berikut:

```css
selector {
  property1: value;
  property2: value;
}
```

Menulis CSS meliputi:
* menentukan *selector* (elemen yang mana yang sedang ditulis spesifikasinya?)
* menentukan *property* (aspek apa yang sedang diatur?)
* menentukan *value* (bagaimana aspek dari elemen tersebut diatur?)

### Selector dasar
Untuk melakukan seleksi terhadap semua `a` di `index.html`, contohnya untuk mengubah warna teks menjadi `rebeccapurple`, dapat ditulis

```css
a { color: rebeccapurple; }
```

Untuk melakukan seleksi terhadap semua `a` *tetapi* hanya yang di dalam `nav`, modifikasi menjadi

```css
nav a { color: rebeccapurple; }
```

Dengan demikian, seleksi terhadap semua `a` yang ada di dalam `li` yang ada di dalam `ul` yang ada di dalam `nav` adalah

```css
nav ul li a { color: rebeccapurple; }
```

*Syntax* `elemen { ... }` akan melakukan seleksi terhadap *semua* elemen jenis tersebut (jenis *selector* ini memiliki istilah: *type selector*). Bagaimana bila hanya ingin dipilih satu saja? Misalnya, hanya `p` yang pertama. 

Untuk mengidentifikasi dan melakukan seleksi terhadap *satu elemen unik* itu saja, label elemen tersebut dengan suatu `id` pada `index.html`. 

```html
<p id="special"><a href="https://en.wikipedia.org/wiki/Lorem_ipsum">Lorem ipsum</a> dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
```
Lalu pada `stylesheet.css`:

```css
#special { color: orangered; }
```

*Labelling* dengan cara seperti ini adalah teknik yang cukup berguna, tetapi perlu diingat bahwa tiap `id` hanya boleh digunakan untuk memberikan label ke satu elemen dan hanya satu elemen itu saja. Tidak boleh ada dua elemen dengan `id` yang sama. Apabila ingin menerapkan metode *labelling* seperti demikian tetapi untuk lebih dari satu elemen dengan label yang sama, gunakan `class`.

```html
      <p>
        <a href="https://en.wikipedia.org/wiki/Lorem_ipsum">Lorem ipsum</a> dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
      </p>
      <p class="highlight">
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
      </p>
      <p class="highlight">
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </p>
```

```css
.highlight { background-color: yellow; }
```

### *Property* dan *value* dasar
Ada banyak sekali pilihan *property* yang disediakan oleh CSS.

Mereka dapat dikelompokkan antara lain berdasarkan aspek yang diaturnya, seperti
* ukuran
* posisi
* warna
* bentuk

Berikut adalah beberapa contoh:
```css
/* mengatur warna background seluruh webpage */
body { background-color: #ccc; }

/* menambahkan margin 5 pixel ke sekeliling semua p */
p { margin: 5px; }

/* hilangkan underline pada link */
a { text-decoration: none; }
```

Mozilla Developer Network memiliki [dokumentasi](https://developer.mozilla.org/en-US/docs/Web/CSS) yang cukup lengkap.

## *CSS basic box model*
Untuk menulis CSS, terutama untuk *layouting*, penting untuk mempelajari prinsip *box model*. Prinsip *box model* dalam konteks CSS menjelaskan bagaimana browser me-render kode CSS berdasarkan spesifikasi seperti `margin`, `padding`, dan `border`.  Pada dasarnya, browser melihat tiap elemen sebagai sebuah persegi yang terdiri dari subbagian margin, border, padding, dan content. Spesifikasi tiap subbagian ini lalu dapat dikonfigurasi lebih lanjut menggunakan CSS. 

Anatomi ini dapat dilihat pada Firefox menggunakan *Developer Tools* dengan kembali memanfaatkan *Inspect Element*.

## *Further reading*
[Tulisan yang dipublikasikan W3C (World Wide Web Consortium) ini](https://www.w3.org/Style/CSS20/history.html) menjelaskan sejarah CSS secara sekilas.
