# 2.4 - Text Styling dengan CSS

CSS menyediakan banyak properti untuk mengontrol tampilan teks, dari font hingga dekorasi.

## Font Properties

### 1. Font Family
```css
/* Single font */
font-family: Arial;

/* Font stack (fallback) */
font-family: Arial, Helvetica, sans-serif;
```

#### Jenis Font
- **Serif**: Font dengan kait (Times New Roman, Georgia)
- **Sans-serif**: Font tanpa kait (Arial, Helvetica)
- **Monospace**: Font dengan lebar karakter sama (Courier, Monaco)
- **Cursive**: Font menyerupai tulisan tangan
- **Fantasy**: Font dekoratif

### 2. Font Size
```css
/* Absolute sizes */
font-size: 16px;
font-size: 12pt;

/* Relative sizes */
font-size: 1.2em;    /* Relatif terhadap parent */
font-size: 1.2rem;   /* Relatif terhadap root */
font-size: 120%;     /* Persentase dari parent */
```

### 3. Font Weight
```css
font-weight: normal;
font-weight: bold;
font-weight: 400;    /* 100-900 */
```

### 4. Font Style
```css
font-style: normal;
font-style: italic;
font-style: oblique;
```

## Text Properties

### 1. Text Alignment
```css
text-align: left;
text-align: right;
text-align: center;
text-align: justify;
```

### 2. Line Height
```css
line-height: 1.5;       /* Recommended */
line-height: 20px;
line-height: 120%;
```

### 3. Text Decoration
```css
text-decoration: none;
text-decoration: underline;
text-decoration: overline;
text-decoration: line-through;
```

### 4. Text Transform
```css
text-transform: none;
text-transform: uppercase;
text-transform: lowercase;
text-transform: capitalize;
```

### 5. Letter & Word Spacing
```css
letter-spacing: 2px;
word-spacing: 4px;
```

### 6. Text Shadow
```css
text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
/* offset-x | offset-y | blur-radius | color */
```

## 💡 Tips Typography

1. **Readability**
   - Gunakan line-height 1.5-1.6 untuk paragraf
   - Pilih font yang mudah dibaca
   - Perhatikan kontras dengan background

2. **Font Stacks**
   ```css
   font-family: 
     -apple-system,      /* iOS Safari, macOS Safari */
     BlinkMacSystemFont, /* Chrome macOS */
     "Segoe UI",        /* Windows */
     Roboto,            /* Android, Chrome */
     "Helvetica Neue",  /* Older macOS */
     Arial,             /* Windows fallback */
     sans-serif;        /* Generic fallback */
   ```

3. **Responsive Text**
   ```css
   html {
     font-size: 16px;
   }
   
   @media (max-width: 768px) {
     html {
       font-size: 14px;
     }
   }
   ```

4. **Performance**
   - Batasi jumlah font yang digunakan
   - Gunakan font system jika memungkinkan
   - Optimalkan loading web fonts

---

### ✏️ **Tugas Kecil**

1. Buat artikel sederhana dengan:
   - Judul dengan custom font dan shadow
   - Paragraf dengan line height yang nyaman
   - Pull quote dengan styling khusus
   - Footer text yang lebih kecil

2. Buat card profil dengan:
   - Nama dengan font dekoratif
   - Deskripsi dengan font yang mudah dibaca
   - Social links dengan hover effect
   - Spacing yang seimbang
