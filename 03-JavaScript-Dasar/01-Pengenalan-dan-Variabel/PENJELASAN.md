# 3.1 - Pengenalan JavaScript dan Variabel

JavaScript adalah bahasa pemrograman yang membuat website menjadi interaktif.

## Cara Menambahkan JavaScript

### 1. Internal JavaScript
```html
<script>
    // Kode JavaScript di sini
    console.log("Hello World!");
</script>
```

### 2. External JavaScript
```html
<script src="script.js"></script>
```

### 3. Inline JavaScript
```html
<button onclick="alert('Hello!')">Klik Saya</button>
```

## Variabel dan Nilai

### Deklarasi Variabel
```javascript
let nama = "Budi";              // String
let umur = 25;                  // Number
let aktif = true;               // Boolean
let hobi = ["Membaca", "Menulis"]; // Array
let orang = {                   // Object
    nama: "Budi",
    umur: 25
};
```

### Jenis Deklarasi

#### 1. let
- Bisa diubah nilainya
- Block scope
- Tidak bisa dideklarasi ulang
```javascript
let skor = 10;
skor = 20; // OK

let skor = 30; // Error
```

#### 2. const
- Tidak bisa diubah nilainya
- Block scope
- Tidak bisa dideklarasi ulang
```javascript
const PI = 3.14;
PI = 3.15; // Error
```

#### 3. var (Hindari Penggunaan)
- Bisa diubah nilainya
- Function scope
- Bisa dideklarasi ulang
```javascript
var x = 1;
var x = 2; // OK, tapi tidak disarankan
```

## Scope Variabel

### 1. Block Scope
```javascript
if (true) {
    let x = 10;    // Hanya bisa diakses di dalam block
    const y = 20;  // Hanya bisa diakses di dalam block
    var z = 30;    // Bisa diakses di luar block
}
// console.log(x); // Error
// console.log(y); // Error
console.log(z);    // OK
```

### 2. Function Scope
```javascript
function test() {
    var fungsi = "Halo";    // Function scope
    let blok = "Hi";        // Block scope
    
    if (true) {
        let blok2 = "Hey";  // Block scope
        console.log(blok);  // OK
    }
    // console.log(blok2); // Error
}
```

## 💡 Best Practices

1. **Gunakan const sebagai default**
   ```javascript
   // Jika nilai tidak akan berubah
   const API_KEY = "abc123";
   const WARNA_TEMA = "#ff0000";
   ```

2. **Gunakan let jika perlu diubah**
   ```javascript
   // Untuk nilai yang akan berubah
   let skor = 0;
   let namaUser = "";
   ```

3. **Hindari var**
   ```javascript
   // ❌ Jangan gunakan var
   var x = 10;
   
   // ✅ Gunakan let atau const
   let x = 10;
   const y = 20;
   ```

4. **Penamaan yang Jelas**
   ```javascript
   // ❌ Buruk
   let x = "Budi";
   
   // ✅ Baik
   let namaPengguna = "Budi";
   ```

5. **Gunakan camelCase**
   ```javascript
   let namaLengkap = "Budi Santoso";
   let umurPengguna = 25;
   ```

---

### ✏️ **Tugas Kecil**

1. Buat script yang menggunakan:
   - Minimal 3 variabel dengan let
   - Minimal 2 konstanta dengan const
   - Tampilkan semua nilai di console

2. Buat program kalkulator sederhana:
   - Deklarasikan variabel untuk angka1 dan angka2
   - Buat konstanta untuk operasi matematika
   - Tampilkan hasil perhitungan di halaman

3. Eksperimen dengan scope:
   - Buat fungsi dengan variabel lokal
   - Buat block dengan let dan const
   - Coba akses variabel dari luar scope
   - Catat apa yang bisa dan tidak bisa diakses
