# 1.4 - Link dan Gambar

Link dan gambar adalah elemen penting yang membuat web menjadi interaktif dan menarik secara visual.

## Link (Hyperlink)

### Tag `<a>` (Anchor)
- Membuat link ke halaman web lain, file, atau lokasi dalam halaman yang sama
- Atribut penting:
  - `href`: URL tujuan link
  - `target`: cara membuka link (`_blank` untuk tab baru)

### Jenis-jenis Link
1. Link Eksternal
   ```html
   <a href="https://www.google.com">Google</a>
   ```

2. Link Internal (ke bagian halaman)
   ```html
   <a href="#bagian-1">Ke Bagian 1</a>
   ```

3. Link Email
   ```html
   <a href="mailto:email@contoh.com">Email Kami</a>
   ```

## Gambar

### Tag `<img>`
- Tag untuk menampilkan gambar
- Tag ini tidak memiliki tag penutup
- Atribut penting:
  - `src`: sumber/lokasi gambar
  - `alt`: teks alternatif jika gambar tidak dapat ditampilkan
  - `width`: lebar gambar
  - `height`: tinggi gambar

### Tips Penggunaan Gambar
1. Selalu sertakan atribut `alt` untuk aksesibilitas
2. Sesuaikan ukuran gambar untuk performa
3. Gunakan format gambar yang tepat:
   - JPG: untuk foto
   - PNG: untuk gambar dengan transparansi
   - SVG: untuk logo dan ikon

### Gambar dengan Caption
Gunakan tag `<figure>` dan `<figcaption>` untuk memberi caption pada gambar:
```html
<figure>
    <img src="gambar.jpg" alt="Deskripsi">
    <figcaption>Caption gambar</figcaption>
</figure>
```

---

### ✏️ **Tugas Kecil**

1. Buat halaman profil sederhana dengan:
   - Link ke media sosial Anda (gunakan target="_blank")
   - Foto profil (gunakan gambar placeholder jika tidak ada)
   - Caption di bawah foto
2. Buat daftar gambar produk dengan:
   - Minimal 3 gambar
   - Setiap gambar bisa diklik menuju halaman detail (gunakan #)
