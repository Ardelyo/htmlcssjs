# 1.7 - Elemen Semantik HTML

Elemen semantik adalah elemen HTML5 yang memberikan makna pada struktur website, tidak hanya untuk tampilan.

## Elemen Semantik Utama

### 1. `<header>`
- Bagian pembuka dari website atau artikel
- Biasanya berisi judul, logo, navigasi utama
- Bisa digunakan di level website atau artikel

### 2. `<nav>`
- Bagian navigasi website
- Berisi menu atau daftar link
- Bisa di header atau di tempat lain

### 3. `<main>`
- Konten utama website
- Hanya boleh ada satu per halaman
- Tidak termasuk header, footer, sidebar

### 4. `<article>`
- Konten yang berdiri sendiri
- Bisa dibaca terpisah dari konten lain
- Contoh: posting blog, berita, komentar

### 5. `<section>`
- Bagian yang tematik dari konten
- Biasanya memiliki heading
- Mengelompokkan konten terkait

### 6. `<aside>`
- Konten yang berhubungan tapi terpisah
- Contoh: sidebar, iklan, quotes
- Bisa di dalam article atau di luar

### 7. `<footer>`
- Bagian penutup website atau artikel
- Berisi info tambahan
- Contoh: copyright, kontak, sitemap

### 8. Elemen Semantik Lainnya
- `<figure>` dan `<figcaption>`: untuk gambar dengan caption
- `<time>`: untuk tanggal dan waktu
- `<address>`: untuk informasi kontak
- `<mark>`: untuk teks yang disorot
- `<details>` dan `<summary>`: untuk konten yang bisa dibuka/tutup

## 💡 Keuntungan Menggunakan Elemen Semantik

1. SEO yang lebih baik
2. Aksesibilitas yang lebih baik
3. Kode lebih mudah dibaca dan dipelihara
4. Struktur dokumen lebih jelas

## Perbandingan dengan Non-Semantik

### Non-Semantik:
```html
<div class="header">
    <div class="nav">
        <div class="menu-item">
```

### Semantik:
```html
<header>
    <nav>
        <ul>
```

---

### ✏️ **Tugas Kecil**

1. Buat halaman artikel blog sederhana dengan:
   - Header website dengan navigasi
   - Artikel utama dengan beberapa section
   - Sidebar dengan widget
   - Footer dengan informasi kontak

2. Ubah struktur div yang ada di file sebelumnya menjadi elemen semantik yang sesuai
