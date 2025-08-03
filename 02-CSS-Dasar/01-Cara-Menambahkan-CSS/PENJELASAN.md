# 2.1 - Cara Menambahkan CSS

CSS (Cascading Style Sheets) dapat ditambahkan ke dokumen HTML dengan tiga cara berbeda.

## Tiga Cara Menambahkan CSS

### 1. CSS Inline
- Ditambahkan langsung pada elemen HTML menggunakan atribut `style`
- Contoh:
  ```html
  <p style="color: red; font-size: 16px;">Teks merah</p>
  ```
- Kelebihan:
  - Prioritas tertinggi
  - Berguna untuk override style
  - Baik untuk testing cepat
- Kekurangan:
  - Sulit maintenance
  - Tidak reusable
  - Mencampur konten dan style

### 2. CSS Internal
- Ditulis dalam tag `<style>` di bagian `<head>`
- Contoh:
  ```html
  <style>
    p {
      color: blue;
      font-size: 14px;
    }
  </style>
  ```
- Kelebihan:
  - Tidak perlu file eksternal
  - Baik untuk halaman unik
  - Lebih terorganisir dari inline
- Kekurangan:
  - Meningkatkan ukuran HTML
  - Tidak dapat digunakan ulang di halaman lain
  - Loading time lebih lama

### 3. CSS External
- Ditulis dalam file `.css` terpisah
- Dihubungkan dengan tag `<link>`
- Contoh:
  ```html
  <link rel="stylesheet" href="styles.css">
  ```
- Kelebihan:
  - Pemisahan konten dan style
  - File CSS bisa di-cache
  - Mudah maintenance
  - Reusable
- Kekurangan:
  - Perlu request tambahan ke server
  - Halaman mungkin tampil tanpa style sebelum CSS load

## 💡 Prioritas CSS (Specificity)

Urutan prioritas dari tinggi ke rendah:
1. CSS Inline (`style="..."`)
2. ID Selector (`#id`)
3. Class Selector (`.class`)
4. Tag Selector (`p`, `div`, dll)

## Tips Penggunaan

1. **Untuk Website Kecil:**
   - Gunakan CSS Internal jika hanya beberapa halaman
   - Hindari CSS Inline kecuali untuk testing

2. **Untuk Website Besar:**
   - Selalu gunakan CSS External
   - Organisasikan CSS dalam beberapa file sesuai fungsi
   - Gunakan naming convention yang konsisten

3. **Best Practices:**
   - Hindari penggunaan CSS Inline
   - Pisahkan struktur (HTML) dan style (CSS)
   - Manfaatkan teknik CSS reuse

---

### ✏️ **Tugas Kecil**

1. Buat file HTML baru dan terapkan ketiga metode CSS:
   - Inline style untuk mengubah warna teks
   - Internal style untuk mengubah ukuran font
   - External style untuk mengubah background

2. Buat contoh prioritas CSS:
   - Buat elemen dengan class dan id
   - Styling sama dengan ketiga metode CSS
   - Amati style mana yang diterapkan
