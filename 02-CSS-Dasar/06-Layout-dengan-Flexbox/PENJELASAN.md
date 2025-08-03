# 2.6 - Layout dengan Flexbox

Flexbox adalah model layout CSS modern yang memudahkan pengaturan elemen dalam container.

## Konsep Dasar

### Container dan Items
- Container: Elemen parent dengan `display: flex`
- Items: Elemen child langsung dari container

```css
.container {
    display: flex;
}
```

## Properties Container

### 1. Flex Direction
```css
flex-direction: row;          /* Default */
flex-direction: row-reverse;
flex-direction: column;
flex-direction: column-reverse;
```

### 2. Justify Content
Mengatur align horizontal:
```css
justify-content: flex-start;    /* Default */
justify-content: flex-end;
justify-content: center;
justify-content: space-between;
justify-content: space-around;
justify-content: space-evenly;
```

### 3. Align Items
Mengatur align vertikal:
```css
align-items: stretch;      /* Default */
align-items: flex-start;
align-items: flex-end;
align-items: center;
align-items: baseline;
```

### 4. Flex Wrap
```css
flex-wrap: nowrap;        /* Default */
flex-wrap: wrap;
flex-wrap: wrap-reverse;
```

### 5. Gap
Jarak antar items:
```css
gap: 10px;               /* Sama untuk baris & kolom */
gap: 10px 20px;         /* Baris | Kolom */
```

## Properties Items

### 1. Flex Grow
Kemampuan item untuk membesar:
```css
flex-grow: 0;    /* Default */
flex-grow: 1;    /* Akan mengambil space tersisa */
```

### 2. Flex Shrink
Kemampuan item untuk mengecil:
```css
flex-shrink: 1;    /* Default */
flex-shrink: 0;    /* Tidak akan mengecil */
```

### 3. Flex Basis
Ukuran default sebelum distribusi space:
```css
flex-basis: auto;    /* Default */
flex-basis: 200px;
```

### 4. Order
Urutan item:
```css
order: 0;     /* Default */
order: 1;     /* Tampil setelah item dengan order lebih kecil */
```

### 5. Align Self
Override align-items untuk item spesifik:
```css
align-self: auto;      /* Default */
align-self: flex-start;
align-self: center;
align-self: flex-end;
```

## 💡 Tips Penggunaan

1. **Shorthand Properties**
   ```css
   /* flex: grow shrink basis */
   flex: 1 1 auto;
   
   /* Umum digunakan */
   flex: 1;         /* flex: 1 1 0 */
   flex: auto;      /* flex: 1 1 auto */
   flex: none;      /* flex: 0 0 auto */
   ```

2. **Responsive Design**
   ```css
   .container {
       display: flex;
       flex-wrap: wrap;
   }
   
   .item {
       flex: 1 1 300px;  /* Minimal 300px, bisa grow/shrink */
   }
   ```

3. **Centering Sempurna**
   ```css
   .center {
       display: flex;
       justify-content: center;
       align-items: center;
   }
   ```

4. **Navigation Bar**
   ```css
   .nav {
       display: flex;
       justify-content: space-between;
   }
   
   .nav-item {
       flex: 0 1 auto;  /* Tidak grow, bisa shrink */
   }
   ```

## Contoh Layout Umum

### 1. Holy Grail Layout
```css
.container {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}

header, footer {
    flex: 0 0 auto;
}

main {
    display: flex;
    flex: 1;
}

nav, aside {
    flex: 0 0 200px;
}

article {
    flex: 1;
}
```

### 2. Card Grid
```css
.card-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.card {
    flex: 1 1 300px;
}
```

---

### ✏️ **Tugas Kecil**

1. Buat navbar responsif dengan:
   - Logo di kiri
   - Menu di tengah
   - Button login di kanan
   - Responsive pada mobile

2. Buat grid kartu produk dengan:
   - 3 kolom pada desktop
   - 2 kolom pada tablet
   - 1 kolom pada mobile
   - Gap yang konsisten
   - Tinggi kartu yang sama
