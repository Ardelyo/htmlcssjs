# 1.5 - Tabel dalam HTML

Tabel digunakan untuk menampilkan data dalam format baris dan kolom.

## Struktur Dasar Tabel

### Tag-tag Utama
- `<table>`: Membungkus seluruh tabel
- `<tr>`: Table Row (baris tabel)
- `<td>`: Table Data (sel data)
- `<th>`: Table Header (sel header)

### Bagian-bagian Tabel
- `<thead>`: Kelompok baris header
- `<tbody>`: Kelompok baris isi
- `<tfoot>`: Kelompok baris footer
- `<caption>`: Judul tabel

## Fitur Tabel Lanjutan

### Penggabungan Sel
1. `colspan`: Menggabungkan sel secara horizontal
   ```html
   <td colspan="2">Sel yang digabung horizontal</td>
   ```

2. `rowspan`: Menggabungkan sel secara vertikal
   ```html
   <td rowspan="2">Sel yang digabung vertikal</td>
   ```

### Atribut Tabel
- `border`: Menambahkan garis tepi (contoh: `border="1"`)
- `width`: Mengatur lebar tabel
- `cellpadding`: Mengatur jarak dalam sel
- `cellspacing`: Mengatur jarak antar sel

## 💡 Tips Membuat Tabel

1. Gunakan `<thead>`, `<tbody>`, dan `<tfoot>` untuk struktur yang lebih baik
2. Selalu sertakan header (`<th>`) untuk aksesibilitas
3. Hindari penggunaan tabel untuk layout halaman
4. Gunakan `<caption>` untuk memberikan judul tabel

---

### ✏️ **Tugas Kecil**

1. Buat tabel jadwal kegiatan harian dengan:
   - Minimal 5 baris
   - Kolom: Waktu, Kegiatan, Lokasi
   - Gunakan `<thead>` dan `<tbody>`

2. Buat tabel nilai siswa dengan:
   - Header: Nama, Matematika, Bahasa, IPA, Rata-rata
   - Minimal 3 siswa
   - Gunakan `colspan` untuk membuat header "Nilai Pelajaran"
   - Tambahkan baris total di `<tfoot>`
