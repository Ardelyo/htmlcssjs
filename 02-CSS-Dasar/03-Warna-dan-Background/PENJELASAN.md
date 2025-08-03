# 2.3 - Warna dan Background dalam CSS

Warna dan background adalah elemen dasar dalam desain web yang membuat halaman lebih menarik dan informatif.

## Warna dalam CSS

### 1. Format Penulisan Warna

#### Named Colors
```css
color: red;
color: skyblue;
color: gold;
```
- Mudah dibaca
- Terbatas (140 nama warna)
- Tidak presisi

#### Hexadecimal (#)
```css
color: #FF0000;  /* Merah */
color: #0000FF;  /* Biru */
color: #FFF;     /* Putih (shorthand) */
```
- Format paling umum
- 16 juta warna
- Sulit dibaca manusia

#### RGB/RGBA
```css
color: rgb(255, 0, 0);        /* Merah */
color: rgba(255, 0, 0, 0.5);  /* Merah transparan */
```
- Mudah dipahami (0-255)
- RGBA untuk transparansi
- Lebih panjang dari hex

#### HSL/HSLA
```css
color: hsl(0, 100%, 50%);        /* Merah */
color: hsla(0, 100%, 50%, 0.5);  /* Merah transparan */
```
- Intuitif (Hue, Saturation, Lightness)
- Mudah untuk variasi warna
- Kurang umum digunakan

## Background dalam CSS

### 1. Background Color
```css
background-color: #f0f0f0;
background-color: rgba(255, 0, 0, 0.5);
```

### 2. Background Image
```css
background-image: url('gambar.jpg');
```

#### Background Properties
- `background-repeat`
  ```css
  background-repeat: repeat;    /* Default */
  background-repeat: no-repeat;
  background-repeat: repeat-x;
  background-repeat: repeat-y;
  ```

- `background-position`
  ```css
  background-position: center;
  background-position: top left;
  background-position: 50% 50%;
  ```

- `background-size`
  ```css
  background-size: cover;
  background-size: contain;
  background-size: 100% auto;
  ```

### 3. Gradients

#### Linear Gradient
```css
background: linear-gradient(to right, #ff0000, #00ff00);
background: linear-gradient(45deg, red, blue);
```

#### Radial Gradient
```css
background: radial-gradient(circle, red, blue);
background: radial-gradient(ellipse, #ff0000, #00ff00);
```

### 4. Multiple Backgrounds
```css
background: 
    linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
    url('gambar.jpg');
```

## 💡 Tips Penggunaan

1. **Konsistensi Warna**
   - Tentukan palet warna
   - Gunakan variabel CSS untuk warna utama
   - Pertahankan kontras yang baik

2. **Background Image**
   - Optimasi ukuran gambar
   - Gunakan `background-size: cover` untuk responsif
   - Sediakan fallback color

3. **Performance**
   - Hindari gambar background yang terlalu besar
   - Gunakan format gambar yang tepat (jpg/webp)
   - Pertimbangkan gradient sebagai alternatif gambar

---

### ✏️ **Tugas Kecil**

1. Buat kartu profil dengan:
   - Warna background gradient
   - Warna teks yang kontras
   - Background image dengan overlay

2. Buat section dengan:
   - Pattern background yang berulang
   - Teks yang mudah dibaca
   - Minimal 3 variasi warna yang harmonis
