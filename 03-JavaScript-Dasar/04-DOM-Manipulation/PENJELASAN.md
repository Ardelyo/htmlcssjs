# 3.4 - DOM Manipulation

DOM (Document Object Model) adalah representasi dari struktur halaman web dalam bentuk pohon objek. DOM Manipulation memungkinkan kita untuk mengubah konten, struktur, dan style halaman web secara dinamis menggunakan JavaScript.

## 1. Memilih Elemen

### getElementById
```javascript
const element = document.getElementById('myId');
```

### getElementsByClassName
```javascript
const elements = document.getElementsByClassName('myClass');
```

### getElementsByTagName
```javascript
const elements = document.getElementsByTagName('div');
```

### querySelector & querySelectorAll
```javascript
// Memilih elemen pertama yang cocok
const element = document.querySelector('.myClass');

// Memilih semua elemen yang cocok
const elements = document.querySelectorAll('.myClass');
```

## 2. Mengubah Konten

### textContent
```javascript
element.textContent = 'Teks Baru';
```

### innerHTML
```javascript
element.innerHTML = '<strong>Teks Bold</strong>';
```

### value (untuk input)
```javascript
inputElement.value = 'Nilai Baru';
```

## 3. Mengubah Atribut

### Mengatur Atribut
```javascript
element.setAttribute('src', 'image.jpg');
element.setAttribute('class', 'highlight');
```

### Membaca Atribut
```javascript
const src = element.getAttribute('src');
```

### Menghapus Atribut
```javascript
element.removeAttribute('class');
```

### Atribut Langsung
```javascript
element.id = 'newId';
element.className = 'newClass';
element.src = 'newImage.jpg';
```

## 4. Mengubah Style

### Style Langsung
```javascript
element.style.backgroundColor = 'red';
element.style.fontSize = '20px';
element.style.margin = '10px';
```

### Classes
```javascript
// Menambah class
element.classList.add('highlight');

// Menghapus class
element.classList.remove('highlight');

// Toggle class
element.classList.toggle('active');

// Cek class
if (element.classList.contains('active')) {
    // lakukan sesuatu
}
```

## 5. Membuat & Menghapus Elemen

### Membuat Elemen
```javascript
const newDiv = document.createElement('div');
newDiv.textContent = 'Elemen Baru';
```

### Menambah ke DOM
```javascript
// Tambah di akhir parent
parentElement.appendChild(newDiv);

// Tambah sebelum elemen tertentu
parentElement.insertBefore(newDiv, referenceElement);
```

### Menghapus Elemen
```javascript
// Hapus diri sendiri
element.remove();

// Hapus child
parentElement.removeChild(childElement);
```

## 6. Navigasi DOM

### Parent & Children
```javascript
// Ke parent
const parent = element.parentElement;

// Ke children
const children = element.children;
const firstChild = element.firstElementChild;
const lastChild = element.lastElementChild;
```

### Siblings
```javascript
const next = element.nextElementSibling;
const previous = element.previousElementSibling;
```

## 💡 Tips DOM Manipulation

1. **Performa**
   ```javascript
   // Buruk (banyak reflow)
   for (let i = 0; i < 100; i++) {
       document.body.appendChild(document.createElement('div'));
   }

   // Baik (satu reflow)
   const fragment = document.createDocumentFragment();
   for (let i = 0; i < 100; i++) {
       fragment.appendChild(document.createElement('div'));
   }
   document.body.appendChild(fragment);
   ```

2. **Event Delegation**
   ```javascript
   // Buruk (banyak event listener)
   document.querySelectorAll('.button').forEach(button => {
       button.addEventListener('click', handleClick);
   });

   // Baik (satu event listener)
   document.addEventListener('click', e => {
       if (e.target.matches('.button')) {
           handleClick(e);
       }
   });
   ```

3. **Caching DOM Elements**
   ```javascript
   // Buruk (query berulang)
   function update() {
       document.getElementById('result').textContent = 'Updated';
   }

   // Baik (cache reference)
   const resultElement = document.getElementById('result');
   function update() {
       resultElement.textContent = 'Updated';
   }
   ```

---

### ✏️ Tugas Kecil

1. Buat Todo List sederhana:
   - Input untuk menambah todo
   - Button untuk menambah
   - List untuk menampilkan todo
   - Kemampuan untuk menghapus todo

2. Buat Image Gallery:
   - Grid dari thumbnail images
   - Klik thumbnail untuk menampilkan gambar besar
   - Tombol next/previous untuk navigasi

3. Buat Form Validation:
   - Input untuk nama, email, dan password
   - Validasi realtime saat input berubah
   - Tampilkan pesan error jika input tidak valid
