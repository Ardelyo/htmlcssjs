# 1.1 - Struktur Dasar HTML

Setiap file HTML memiliki struktur dasar atau "kerangka" yang wajib ada. Anggap saja ini seperti fondasi sebuah rumah.

## Tag-tag Utama

- `<!DOCTYPE html>`: Ini adalah deklarasi, bukan tag. Fungsinya untuk memberitahu browser bahwa dokumen ini adalah HTML5 (versi HTML terbaru). Wajib ada di baris paling atas.
- `<html>`: Ini adalah tag pembuka dari seluruh dokumen. Semua elemen lain berada di dalam tag ini.
- `<head>`: Bagian "kepala" dari dokumen. Isinya adalah informasi *tentang* halaman web, seperti judul, metadata (informasi untuk mesin pencari), dan link ke file CSS. Konten di sini **tidak terlihat** di halaman.
- `<title>`: Menentukan judul halaman yang muncul di tab browser.
- `<body>`: Bagian "tubuh" dari dokumen. Semua konten yang ingin kamu tampilkan kepada pengunjung (teks, gambar, video, dll.) diletakkan di sini.

## 💡 Analogi Sederhana

- `<html>` = Seluruh badan mobil.
- `<head>` = Mesin dan sistem kelistrikan (penting tapi tidak terlihat dari luar).
- `<body>` = Kabin dan eksterior mobil (semua yang dilihat dan digunakan penumpang).

---

### ✏️ **Tugas Kecil**

1. Buka file `index.html` di browser Anda (klik kanan -> Open with -> Chrome/Firefox).
2. Ubah teks di dalam tag `<title>` menjadi nama Anda. Simpan file, lalu refresh browser. Lihat apa yang berubah di tab browser!
3. Ubah teks di dalam tag `<h1>` dan `<p>`.
