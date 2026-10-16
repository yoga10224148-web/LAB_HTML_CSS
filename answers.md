# Jawaban Praktikum: Luthfi Isa Majid (10223051)

## Bagian 1: Pemanasan
1. 
   - Selector: nav a.active:hover
   - Deklarasi: { color: red; }
   - Property: color
   - Value: red
   - Pseudo-class: :hover (dan .active sebagai class selector)
2. 
   - Block: <p>, <li>, <h2>
   - Inline: <span>, <a>, <strong>
3. Jawab: A dan B.
   - Alasan: Aturan `.box p` memilih semua elemen `<p>` yang berada di dalam elemen ber-class `box` (descendant selector), sehingga paragraf A dan paragraf B (meskipun di dalam `<section>`) terkena dampaknya.
4. Jawab: Merah (red).
   - Alasan: Spesifisitas ID selector (`#title`) memiliki nilai yang lebih tinggi daripada Class selector (`.heading`) maupun Element selector (`h1`).
5. Kesalahan: Tag penutup tidak berurutan dengan benar (overlapping / unclosed tags). Tag `<strong>` dibuka di dalam `<p>`, tetapi ditutup di luar `</p>`.
   - Perbaikan: `<p>Hello <strong>world</strong></p>`

## Bagian 3: Prediksi Selector Golf
P1.
(a) "Weekly hack nights.": green
(b) "Bring your own laptop.": orange
(c) "© 2026 Student Affairs": blue

P2.
Urutan specificity dari tertinggi ke terendah:
1. `#tech p` (1 ID, 1 Element = 0,1,0,1)
2. `.club p` (1 Class, 1 Element = 0,0,1,1)
3. `main section p` (3 Elements = 0,0,0,3)
4. `p` (1 Element = 0,0,0,1)

Setelah diuji (hasil sebenarnya):
(Sesuai dengan prediksi di atas).

## Bagian 4: Box model
Q1 (content-box): 334px
Perhitungan: Width (300px) + Padding kiri/kanan (16px + 16px) + Border kiri/kanan (1px + 1px) = 334px.

Q2 (border-box): Lebar total yang terlihat tetap 300px.
Perhitungan: Ukuran content menyusut otomatis menjadi 266px agar total lebar (Content + Padding + Border) pas 300px.

Pengecekan DevTools:
- Content: 928px x ...
- Padding: 16px
- Border: 1px
- Margin: 0px (atau 0px 0px 24px 0px)

## Bagian 5: Tabel debug
| # | Baris | Bug | Perbaikan | Cara menemukannya |
|---|-------|-----|-----------|-------------------|
| 1 | 9 | Atribut CSS `colour` menggunakan ejaan tidak baku | Ganti `colour:` menjadi `color:` | DevTools menunjukkan property tidak valid |
| 2 | 12 | Titik koma `;` hilang pada aturan `background: #dbe7f3` | Tambahkan titik koma di akhir baris | Membaca kode & syntax highlighting |
| 3 | 15 | Nama class `.Card` diawali huruf kapital (case-sensitive) | Ubah `.Card` menjadi `.card` agar cocok dengan HTML | Membaca kode / DevTools |
| 4 | 20 | Terdapat spasi pada nilai unit `18 px` | Ubah `18 px` menjadi `18px` | DevTools menunjukkan value invalid |
| 5 | 23 | Atribut CSS `centre` salah eja | Ubah `centre` menjadi `center` | DevTools |
| 6 | 28 | Penutup tag `<h1>` menggunakan `</h2>` | Ubah `</h2>` menjadi `</h1>` | W3C Validator |
| 7 | 31 | Tanda petik penutup pada `href="about.html>` hilang | Tambahkan tanda petik: `href="about.html"` | Syntax highlighting VS Code |
| 8 | 36 | Tag `<img>` tidak memiliki atribut `alt` | Tambahkan atribut `alt="..."` | W3C Validator |
| 9 | 37 | ID pada HTML (`newsList`) berbeda kapitalisasi dengan CSS (`#news-list`) | Samakan ID HTML menjadi `id="news-list"` | Membaca kode |

## Bagian 6: Tabel Code Review
| # | Baris | Masalah | Mengapa penting | Perbaikan saya |
|---|-------|---------|-----------------|----------------|
| 1 | 1 | Tidak ada `<!DOCTYPE html>` dan struktur `<head>` dasar | Membuat browser masuk ke Quirks Mode dan merusak render | Tambahkan doctype dan meta viewport |
| 2 | 10 | Penggunaan `<div>` untuk header dan navigasi (Non-semantik) | Merusak aksesibilitas (screen reader) dan SEO | Gunakan `<header>` dan `<nav>` |
| 3 | 10 | Judul menggunakan `<b>` dalam `<div>` bukan `<h1>` | Penting untuk hierarki heading dokumen | Gunakan `<h1>` |
| 4 | 6 | Penggunaan `!important` pada CSS | Menyulitkan maintenance kode dan overriding style | Hapus `!important` dan sesuaikan selector |
| 5 | 17 | Teks judul section menggunakan inline style pada `<div>` | Melanggar pemisahan konten dan style, merusak semantik | Gunakan `<h2>` dan styling lewat CSS external/internal |
| 6 | 18 | Penggunaan tag `<br>` berulang untuk spacing | Merusak tata letak responsif dan tidak rapi | Gunakan `margin` atau `padding` CSS |
| 7 | 21 | Gambar `<img>` tidak memiliki atribut `alt` | Aksesibilitas buruk bagi pengguna screen reader | Tambahkan atribut `alt` yang deskriptif |
| 8 | 24 | Input formulir tanpa elemen `<label>` | Pengguna tidak tahu konteks input & masalah aksesibilitas | Tambahkan `<label for="...">` pada tiap input |

Refleksi:
1. Masalah semantik HTML (seperti penggunaan `<div>` menggantikan `<header>` atau `<h2>`). Di browser tampilannya terlihat sama saja, tetapi struktur dokumennya menjadi buruk untuk SEO dan aksesibilitas.
2. Meskipun terlihat berfungsi, kode yang tidak rapi dan tidak semantik akan sangat menyulitkan pengembangan jangka panjang, memicu bug layout di perangkat lain, dan tidak ramah bagi penyandang disabilitas.
3. Selalu mengecek kode menggunakan W3C Validator dan memeriksa tampilan elemen melalui DevTools Browser sebelum mengumpulkan tugas.

## Bagian 7: Exit ticket
1. Anatomi aturan CSS terdiri dari **Selector** (penunjuk elemen yang ingin dihias) dan **Block Deklarasi** `{}` yang berisi pasangan **Property** (sifat yang diubah) dan **Value** (nilai dari sifat tersebut).
2. Konsep perhitungan spesifisitas selector yang lebih kompleks.
3. Membuat struktur HTML semantik dasar seperti `<header>`, `<nav>`, `<main>`, `<section>`, dan `<footer>`.