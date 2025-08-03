# 2.5 - Box Model CSS

Box Model adalah konsep fundamental dalam CSS yang menjelaskan bagaimana setiap elemen HTML diberi ruang dan dibatasi.

## Komponen Box Model

### 1. Content
- Area dimana konten aktual ditampilkan
- Diatur dengan:
  ```css
  width: 200px;
  height: 100px;
  ```

### 2. Padding
- Ruang kosong di sekitar konten
- Transparan
```css
/* Semua sisi */
padding: 10px;

/* Atas | Kanan | Bawah | Kiri */
padding: 10px 20px 15px 25px;

/* Individual */
padding-top: 10px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 25px;
```

### 3. Border
- Garis di sekitar padding
- Dapat diatur style, width, dan color
```css
/* Shorthand */
border: 1px solid black;

/* Individual properties */
border-width: 1px;
border-style: solid;
border-color: black;

/* Per sisi */
border-top: 1px solid red;
border-right: 2px dashed blue;
border-bottom: 3px dotted green;
border-left: 4px double orange;
```

### 4. Margin
- Ruang kosong di luar border
- Transparan
```css
/* Semua sisi */
margin: 10px;

/* Vertikal | Horizontal */
margin: 10px auto;

/* Individual */
margin-top: 10px;
margin-right: 20px;
margin-bottom: 15px;
margin-left: 25px;
```

## Box Sizing

### Content Box (Default)
```css
box-sizing: content-box;
/* width/height hanya untuk content */
```

### Border Box
```css
box-sizing: border-box;
/* width/height termasuk padding dan border */
```

## Konsep Penting

### 1. Margin Collapse
- Margin vertikal antar elemen akan collapse
- Margin terbesar yang digunakan
```css
/* Margin 30px, bukan 50px */
.box1 { margin-bottom: 30px; }
.box2 { margin-top: 20px; }
```

### 2. Margin Auto
- Untuk centering horizontal
```css
.center {
    width: 200px;
    margin: 0 auto;
}
```

### 3. Negative Margins
- Bisa digunakan untuk overlapping
```css
.overlap {
    margin-top: -20px;
}
```

## 💡 Tips Penggunaan

1. **Reset Default Margins**
   ```css
   * {
       margin: 0;
       padding: 0;
       box-sizing: border-box;
   }
   ```

2. **Gunakan Border Box**
   ```css
   html {
       box-sizing: border-box;
   }
   *, *:before, *:after {
       box-sizing: inherit;
   }
   ```

3. **Spacing Konsisten**
   ```css
   .container {
       width: 80%;
       max-width: 1200px;
       margin: 0 auto;
       padding: 20px;
   }
   ```

4. **Responsive Design**
   ```css
   .box {
       width: 90%;
       max-width: 600px;
       margin: auto;
   }
   ```

---

### ✏️ **Tugas Kecil**

1. Buat kartu profil dengan:
   - Width dan height yang tetap
   - Padding yang nyaman
   - Border yang menarik
   - Margin untuk spacing antar kartu

2. Buat layout sederhana dengan:
   - Header dengan padding dan border bottom
   - Main content dengan margin auto
   - Sidebar dengan border dan padding
   - Footer dengan border top
