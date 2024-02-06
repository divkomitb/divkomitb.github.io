---
title: Tugas 2 - CSS
---

*Layouting* dapat dibagi menjadi dua langkah, yaitu:
* mendeklarasikan elemen dan struktur *webpage* di `index.html`
  * mendeklarasikan elemen-elemen seperti `p`, `a`, dan `img`
  * mengelompokkan dan memasukkan elemen-elemen HTML tersebut ke dalam subbagian, seperti `nav`, `header`, atau `div`
* mengatur posisi elemen-elemen tersebut di `stylesheet.css`
  * mengatur posisi terhadap elemen lain dan/atau melakukan konfigurasi pengaturan *box model* elemen tersebut (*margin, padding, border*)
  * mengatur posisi terhadap *window* browser ([*viewport*](https://en.wikipedia.org/wiki/Viewport)).

## Pendahuluan 
*Catatan*: Bacaan-bacaan berikut tidak wajib untuk dibaca semuanya (seperlunya saja), tetapi bisa dimanfaatkan sebagai *starting point* atau pemberi gambaran. 

Cari tahu tentang `<div>` dan apa perbedaannya terhadap `<section>`. Beberapa opsi/saran sumber yang dapat dibaca:
* [\<div>: The Content Division element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
* [\<section>: The Generic Section element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section)
* [Content categories - HTML](https://developer.mozilla.org/en-US/docs/Web/HTML/Content_categories)
* [HTML Living Standard - Grouping Content](https://html.spec.whatwg.org/multipage/sections.html)
* [Marie Chatfield Rivas | Don't Just Put a div on It - Use the Power of the Browser!](https://mariechatfield.com/blog/semantic-html)

Cari tahu tentang *property* CSS `display`.
* [The CSS Display Property](https://www.freecodecamp.org/news/the-css-display-property-display-none-display-table-inline-block-and-more/)
* [display - CSS: Cascading Style Sheets](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
* [Introduction to CSS layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Introduction)
* [Normal Flow - MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Normal_Flow)

## Spesifikasi
Buat sebuah *webpage* yang memperkenalkan dirimu. Format/isi dibebaskan selama mengikuti topik "perkenalan diri" tersebut.

Webpage tersebut harus memiliki
* penggunaan `div` dan `section` sesuai keperluan (perhatikan kapan menggunakan `div` dan kapan menggunakan `section`)
* penggunaan ketiga untuk berbagai kumpulan elemen yang berbeda:
  * `display: block;`
  * `display: inline;`
  * `display: inline-block;`
* ***jika*** berlaku/relevan/*applicable*, penggunaan tag seperti `header` dan `footer`
* *styling* CSS tambahan sesuai selera

## Submisi
Buat sebuah *repository* GitHub baru khusus Bootcamp Divisi Komputer. Nama dibebaskan. [Buat folder baru](https://medium.com/@kartikagrawal7196/how-to-create-a-folder-in-a-github-repository-36b0fd8f9bf8) untuk Tugas 2, lalu upload `index.html` dan `stylesheet.css` dari Tugas 2 ke folder tersebut.

Pada repository tersebut, buka "*Settings*" > "Pages" > "*Build and deployment*" > "*Branch*". Pilih *branch* "main" lalu simpan. Beberapa menit kemudian, cek apakah *webpage* yang telah kamu upload sudah *live*. Berikan link ke *webpage* ini saat mengisi form submisi tugas.

Jika username kamu adalah `DivKom`, nama repository kamu `tugas-divkom`, dan folder kamu adalah `tugas2`, maka `index.html` tersebut harusnya dapat dilihat pada `divkom.github.io/tugas-divkom/tugas2`.
