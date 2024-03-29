---
title: Modul 1 - HTML & GitHub
---

## Daftar Isi

* [Pendahuluan](#pendahuluan)
* [Apa yang terjadi saat sebuah webpage dibuka?](#apa-yang-terjadi-saat-sebuah-webpage-dibuka)
* [Struktur dasar dokumen HTML](#struktur-dasar-dokumen-html)
* [Dasar-dasar HTML](#dasar-dasar-html)
* [Melihat dan berinteraksi dengan source code HTML dari browser](#melihat-dan-berinteraksi-dengan-source-code-html-dari-browser)
* [GitHub](#melihat-dan-berinteraksi-dengan-source-code-html-dari-browser)
* [Further reading](#further-reading)
* [Changelog](#changelog)

## Pendahuluan
Langkah pertama dari melakukan *web development*, biasanya, adalah belajar HTML. Hypertext Markup Language (HTML) adalah fondasi dari tiap *webpage* [sejak Tim Berners-Lee mengembangkan versi pertama web browser pada tahun 1990an](https://www.w3.org/People/Raggett/book4/ch02.html). Pengertian konsep HTML tidak hanya digunakan oleh pengembang *front-end* website yang mengatur penampilan dan interaksi, tetapi juga developer *back-end* yang mesti memahami struktur dan aliran data suatu website.

Pengetahuan dasar HTML tetap dapat berguna untuk mereka yang tidak berencana membuat website, contohnya untuk melakukan *troubleshooting* saat *browsing* sebagai user.

## Apa yang terjadi saat sebuah webpage dibuka?
Saat kamu mengetik URL dan menekan *Enter*, browser membuat koneksi ke server yang adalah *host* (penyedia) dari website tersebut, lalu meminta informasi tentang website tersebut. Informasi ini digunakan untuk melakukan *rendering* website yang didapatkan user.

Modul 1-3 membahas tahap *rendering* yang dilakukan oleh browser. Modul 4 menyentuh sedikit tentang interaksi browser dan server. Keseluruhan proses kecuali bagian *rendering* oleh browser umumnya di bahas pada mata kuliah terkait Jaringan Komputer atau *Networking* (e.g. EL4120).

```
server --> informasi website --> browser
```

"Informasi website" yang diterima browser yang masuk ke cakupan Modul 1-3 adalah HTML, CSS, dan JavaScript. Singkatnya, HTML memberi tahu browser struktur website. Hal ini termasuk tetapi tidak terbatas pada judul website, elemen konten (teks, link, media) yang ada, dan pembagian subbagian (header, navigasi, footer).

Ini adalah peran HTML sebagai *markup language* - suatu bahasa yang digunakan untuk menjelaskan spesifikasi struktur, formatting, dan hubungan antarbagian suatu dokumen. Bandingkan dengan *programming language* yang menjelaskan urutan instruksi. 

> *To publish information for global distribution on the World Wide Web, you need a universally understood publishing language, a kind of mother tongue, which all computers on the Web can potentially understand. [...] The publishing language used by the Web is called HTML (HyperText Mark-up Language).* -[Dave Raggett](https://en.wikipedia.org/wiki/Dave_Raggett)

## Struktur dasar dokumen HTML
Berikut adalah dokumen "*Hello, world!*" versi HTML. Kode ini dapat di-render dengan melakukan *copy-paste* ke text editor, menyimpannya sebagai `.html`, lalu membukanya di browser (*Menu > File > Open File* ...).

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>
    <p><em>Lorem ipsum</em> ...</p>
  </body>
</html>
```

**Perhatikan bagaimana `<...>` mendeklarasikan permulaan dari suatu bagian (seperti `h1` untuk heading 1 atau `em` untuk teks yang italics) dan `</...>` menutupnya**. Kode `<...>` dan `</...>` disebut tag atau tag HTML. Lebih spesifiknya lagi, `<...>` adalah *opening tag* dan `</...>` sebuah *closing tag*.

`<!DOCTYPE html>` memberi tahu browser bahwa dokumen yang sedang dibuka browser adalah dokumen HTML, agar di-render dengan benar. Ini lalu dilanjutkan dengan `<html>` yang kemudian dibagi menjadi dua bagian, `head` dan `body`. 

`head` adalah bagian dokumen yang berisi informasi yang perlu diketahui browser, tetapi tidak di-render (ditampikan sebagai konten website). Contoh elemen yang masuk ke dalam bagian `head` adalah `<title>`, yang memberi tahu browser judul website yang akan ditampilkan pada Tab browser. 

`body` berisi konten website, seperti (dalam kasus ini), heading 1 "*Hello, world!*" dan sebuah paragraf.

![Penampilan rendering Hello, world! di browser vs source code-nya.](https://github.com/divkomitb/divkomitb.github.io/blob/main/bootcamp022024/hello-html.png?raw=true)

## Dasar-dasar HTML
Sebuah website biasanya memiliki bagian header, navigasi, footer, dan konten utama. Tag HTML untuk tiap komponen tersebut adalah `header`, `nav`, `footer`, dan `main`.  Contoh dokumen HTML "Hello, world!" sebelumnya belum memiliki header, navigasi, ataupun footer, tetapi konten "Hello, world!"-nya itu sendiri dapat dianggap sebagai konten utama.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello, world!</title>
  </head>
  <body>
    <main>
      <h1>Hello, world!</h1>
      <p><em>Lorem ipsum</em> ...</p>
    </main>
  </body>
</html>
```

Apa perubahan yang terjadi saat website ini di-render?

Secara langsung, untuk dokumen ini, tidak ada. `<main>` memberitahu browser di mana konten utama berada, tetapi respons browser untuk dokumen HTML ini tetap bakal sama dengan jika ia tidak diberitahu. 

Efek-efek kode seperti `<nav>` dan `<footer>` paling terlihat saat digunakan untuk membuat website yang lebih kompleks. Dengan memberi tahu informasi yang lebih lengkap tentang struktur dan aliran website, kode seperti ini memastikan *search engines* seperti Google menampilkan *snippet* website yang benar, membantu website beradaptasi pada ukuran layar yang berbeda (desktop vs mobile vs tablet), dan membuat kode lebih *readable*. 

Sebuah eksperimen yang dapat dilakukan adalah mencoba browsing tanpa menggunakan *cursor* - hanya bergantung pada tombol-tombol tab, space, enter, dan lainnya di keyboard. Beberapa website mudah dinavigasi dengan cara ini karena tombol Tab akan memindahkan "fokus" mengikuti aliran yang logis, tetapi beberapa website lain mungkin akan menghasilkan perilaku yang aneh dan agak *annoying*. Jika *source code* tipe website pertama dan website kedua dibandingkan, kemungkinan besar tipe website pertama menggunakan tag HTML seperti `<nav>`.

Tag seperti `<nav>` disebut dengan istilah *semantic HTML tags* - kode HTML yang didesain untuk memberitahu arti dan tujuan elemen, dan bagian dari "*good practice*" HTML dan web development modern.

Selain `<em>` (untuk *italics*) yang sudah ada pada dokumen HTML "Hello, world!" di atas, beberapa tag dasar lainnya adalah:

`<strong>` untuk teks bold

`<ul>` dan `<ol>` untuk list unordered dan ordered secara berturut-turut dan `<li>` untuk elemen list

`<img src="[USER SUMBER GAMBAR]" alt="[ALT TEXT]">` untuk gambar

dan `<a href="[DESTINATION URL]">` untuk link. 

Tiap tag HTML juga dapat ditambahkan "id", contohnya

`<h1 id="hello-world">Hello, world!</h1>`

sehingga `<a href="#hello-world">Lompat ke "Hello, world"</a>` akan menghasilkan link yang "melompat" ke elemen `h1` tersebut, seperti link yang ada pada bagian "Daftar Isi" atau "Table of Contents" di Wikipedia. Perhatikan bahwa ini berarti tiap `id` mesti unik - tidak boleh ada dua elemen HTML dengan atribut id yang sama.

## Melihat dan berinteraksi dengan *source code* HTML dari browser
Untuk melihat *source code* HTML suatu website yang sedang dibuka di browser, klik kanan dan cari opsi "*View Source*" atau "*View Source Code*". Ini akan menunjukkan kode HTML website tersebut.

Sebagai contoh, ini adalah *snippet* dari *source code* website SIX ITB.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8" />
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1">

        <title>SIX | Sistem Informasi Akademik ITB</title>
...
```

Saat kita menggunakan fitur "*View Source*", yang kita lihat adalah kode HTML yang diterima browser dari server. 

```
server -> informasi website (kode HTML) ------> diterima browser ----> kode dirender browser
                                         ^^^ kita mengintip di sini (View Source)
```

Namun, browser modern kebanyakan juga biasanya memberikan fitur yang memperbolehkan kita melakukan

```
server -> informasi website (kode HTML) ------> diterima browser ----> kode dirender browser
                                                                 ^^^ kita mengintip dan memodifikasi kode di sini
```

Sebagai dampaknya, kita dapat memodifikasi kode apa yang "dilihat" oleh browser (di-render) meski kode yang diterima browser tetap sama. Karena fitur ini didesain untuk digunakan oleh developer agar dapat bereksperimen langsung di browser, fitur ini di sebagian besar browser dikelompokkan ke *Developer Tools*. **Tool ini biasanya bernama Inspect Element**. Klik-kanan dan pilih "Inspect" atau pencet Ctrl+Shift+K dan pilih "Inspector". (Langkah dan istilah persisnya mungkin sedikit bervariasi dan tergantung versi dan jenis browser yang digunakan.)

Ingat bagian "*... akan menghasilkan link yang 'melompat' ke elemen h1 tersebut ,seperti link yang ada pada bagian 'Daftar Isi' atau 'Table of Contents' di Wikipedia ...*" dari bagian "Dasar-dasar HTML"?

![Melakukan Inspect Element terhadap Table of Contents di Wikipedia.](https://github.com/divkomitb/divkomitb.github.io/blob/main/assets/wikipedia-toc.png?raw=true)

Untuk melakukan *prank* seperti mengubah indeks di Status Mahasiswa SIX menjadi SSS+, klik-kanan pada bagian indeks, cari kode HTML yang memberi tahu browser apa indeks kamu (`<td class="text-center">sebuah indeks</td>`) lalu klik-kanan > Edit HTML untuk mengubahnya menjadi `<td class="text-center">SSS+</td>`. Perhatikan bahwa yang terjadi adalah memodifikasi kode HTML yang dirender oleh browser. 

Hal lain yang (mungkin) lebih berguna daripada mengubah indeks menjadi SSS+ adalah mengakses versi "*full image*" dari postingan di Instagram, misalnya yang ada di @stei.itb. Tulisannya kecil-kecil jadi kurang terbaca, atau mungkin ada yang disuruh dosen untuk nge-share ke teman-teman seangkatannya dan tidak ingin membagikan gambar *pixelated* hasil nge-screenshot? Metode ini dapat digunakan.

Klik-kanan pada gambar, Inspect Element, cari `<img>` ... dan buka URL yang ada pada `src="..."`. 

## GitHub
Jika NIM kamu berawalan 132 atau 183, kamu kemungkinan besar akan segera atau sudah pernah bertemu GitHub di EL2208. Atau, kamu mungkin sudah melakukannya di IF1210.

GitHub adalah website yang, singkatnya, digunakan untuk membagikan kode dan melakukan kolaborasi. GitHub berbeda dari Git, sebuah software *version control* yang digunakan untuk melacak perubahan pada dokumen sehingga kamu bisa dengan mudah "*time traveling*" ke versi kode sebelum-sebelumnya atau mencari tahu siapa yang menambahkan suatu *snippet* kode bermasalah yang menimbulkan *bug*. Namun, GitHub memang menggunakan prinsip-prinsip yang sama dengan Git (manajemen dan pelacakan perubahan kode, kolaborasi, dan lainnya).

Salah satu hal yang penting untuk bootcamp ini adalah GitHub Pages - layanan yang diberikan oleh GitHub yang memperbolehkanmu untuk nge-*hosting* website buatanmu secara gratis.

Setelah mendaftar dan membuat akun [di GitHub](https://github.com), buat repository bernama username.github.io dengan semua huruf kecil (jika username kamu adalah DivKomITB ... berarti nama repository adalah divkomitb.github.io). Ikuti instruksi no 1-6 [di tutorial ini](https://docs.github.com/en/pages/quickstart). Selanjutnya, jika kamu mengupload suatu dokumen HTML yang dinamakan `index.html`, dokumen tersebut bakal dapat dilihat di URL `username.github.io`. 

## *Further reading*
Mozilla Developer Network memiliki [tutorial HTML dasar](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics) dan [dokumentasi HTML](https://developer.mozilla.org/en-US/docs/Web/HTML).

FreeCodeCamp memiliki [The Beginner's Guide to Git and GitHub](https://www.freecodecamp.org/news/the-beginners-guide-to-git-github/).

[Bab "*Introduction to the World Wide Web*"](https://www.w3.org/People/Raggett/book4/ch01.html) dari buku *Raggett on HTML4* yang menjelaskan cara kerja World Wide Web.

["\<h1>-\<h6>: The HTML Section Heading elements"](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) di Mozilla Developer Network menjelaskan `<h1>` hingga `<h6>`.

## *Changelog*
05-02-2024: Menambahkan link ke post dan bagian *Further reading*, menambahkan gambar, perbaikan penulisan dan formatting minor
