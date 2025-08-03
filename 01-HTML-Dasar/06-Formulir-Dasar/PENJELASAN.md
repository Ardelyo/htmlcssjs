# 1.6 - Formulir dalam HTML

Formulir (form) adalah cara untuk mengumpulkan data dari pengguna website.

## Struktur Dasar Form

### Tag `<form>`
- Membungkus seluruh elemen formulir
- Atribut penting:
  - `action`: URL tempat data akan dikirim
  - `method`: cara pengiriman data (GET/POST)

### Tag `<label>` dan `<input>`
- `<label>`: Label untuk input
- `<input>`: Tempat user memasukkan data
- Selalu hubungkan dengan atribut `for` dan `id`

## Jenis-jenis Input

### 1. Input Teks
```html
<input type="text">      <!-- Teks biasa -->
<input type="password">  <!-- Password -->
<input type="email">     <!-- Email -->
<input type="number">    <!-- Angka -->
<input type="tel">       <!-- Nomor telepon -->
```

### 2. Input Pilihan
```html
<input type="checkbox">  <!-- Kotak centang -->
<input type="radio">     <!-- Pilihan radio -->
<select>                 <!-- Dropdown -->
  <option>Pilihan 1</option>
</select>
```

### 3. Input Khusus
```html
<input type="date">      <!-- Tanggal -->
<input type="file">      <!-- Upload file -->
<input type="color">     <!-- Pemilih warna -->
<textarea>               <!-- Teks panjang -->
```

## Pengelompokan Form

### Fieldset dan Legend
```html
<fieldset>
    <legend>Judul Grup</legend>
    <!-- elemen form -->
</fieldset>
```

## 💡 Tips Membuat Form

1. Selalu gunakan `<label>` untuk setiap input
2. Berikan atribut `name` pada setiap input
3. Validasi input dengan atribut:
   - `required`: wajib diisi
   - `pattern`: pola tertentu (regex)
   - `minlength`/`maxlength`: panjang teks
4. Gunakan `placeholder` untuk memberi contoh

---

### ✏️ **Tugas Kecil**

1. Buat form kontak dengan:
   - Input nama
   - Input email
   - Textarea untuk pesan
   - Tombol submit

2. Buat form pemesanan makanan dengan:
   - Dropdown untuk memilih menu
   - Radio button untuk ukuran porsi
   - Checkbox untuk tambahan
   - Input jumlah
   - Textarea untuk catatan khusus
