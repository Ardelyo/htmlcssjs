# 3.2 - Tipe Data dan Operator JavaScript

JavaScript memiliki beberapa tipe data dasar dan berbagai operator untuk memanipulasi data.

## Tipe Data

### 1. Number
```javascript
let bilangan = 42;          // Integer
let desimal = 3.14;        // Float
let negatif = -10;        // Negative
let infinity = Infinity;   // Infinity
let notNumber = NaN;      // Not a Number
```

### 2. String
```javascript
let nama = "Budi";                    // Double quotes
let pesan = 'Halo Dunia';            // Single quotes
let template = `Nama saya ${nama}`;   // Template literal
```

### 3. Boolean
```javascript
let benar = true;
let salah = false;
```

### 4. Null dan Undefined
```javascript
let kosong = null;         // Nilai kosong yang disengaja
let tidakAda;             // Undefined (belum diberi nilai)
```

### 5. Array
```javascript
let angka = [1, 2, 3, 4, 5];
let campuran = [1, "dua", true, null];
```

### 6. Object
```javascript
let orang = {
    nama: "Budi",
    umur: 25,
    aktif: true
};
```

## Operator

### 1. Operator Aritmatika
```javascript
let a = 10;
let b = 3;

a + b   // Penjumlahan (13)
a - b   // Pengurangan (7)
a * b   // Perkalian (30)
a / b   // Pembagian (3.333...)
a % b   // Modulus/Sisa Bagi (1)
a ** b  // Eksponen (1000)
```

### 2. Operator Perbandingan
```javascript
5 == "5"    // true (sama dengan)
5 === "5"   // false (identik - tipe data harus sama)
5 != 6      // true (tidak sama dengan)
5 !== "5"   // true (tidak identik)
5 > 3       // true (lebih besar dari)
5 < 3       // false (lebih kecil dari)
5 >= 5      // true (lebih besar atau sama dengan)
5 <= 6      // true (lebih kecil atau sama dengan)
```

### 3. Operator Logika
```javascript
true && false   // AND (false)
true || false   // OR (true)
!true           // NOT (false)
```

### 4. Operator Assignment
```javascript
let x = 5;      // Assignment biasa
x += 3;         // x = x + 3
x -= 2;         // x = x - 2
x *= 4;         // x = x * 4
x /= 2;         // x = x / 2
x %= 3;         // x = x % 3
```

### 5. Operator Ternary
```javascript
let nilai = 75;
let hasil = nilai >= 70 ? "Lulus" : "Tidak Lulus";
```

## Type Coercion

JavaScript akan otomatis mengkonversi tipe data dalam operasi tertentu:

```javascript
// String + Number = String
"5" + 1     // "51"

// String - Number = Number
"5" - 1     // 4

// Boolean + Number = Number
true + 1    // 2

// Number + null = Number
5 + null    // 5

// Number + undefined = NaN
5 + undefined   // NaN
```

## 💡 Tips Penggunaan

1. **Perbandingan yang Aman**
   ```javascript
   // ❌ Hindari ==
   5 == "5"    // true
   
   // ✅ Gunakan ===
   5 === "5"   // false
   ```

2. **Konversi Tipe Data**
   ```javascript
   // String ke Number
   Number("123")      // 123
   parseInt("123")    // 123
   parseFloat("3.14") // 3.14
   
   // Number ke String
   String(123)        // "123"
   (123).toString()   // "123"
   ```

3. **Pengecekan Tipe Data**
   ```javascript
   typeof 42          // "number"
   typeof "hello"     // "string"
   Array.isArray([])  // true
   ```

---

### ✏️ **Tugas Kecil**

1. Buat kalkulator BMI:
   - Input berat (kg) dan tinggi (m)
   - Hitung BMI (berat / tinggi²)
   - Gunakan operator aritmatika
   - Tampilkan kategori (kurus/normal/gemuk) dengan ternary

2. Buat validator password:
   - Cek panjang password (minimal 8 karakter)
   - Cek ada huruf dan angka
   - Gunakan operator logika
   - Tampilkan pesan sesuai hasil validasi

3. Buat konverter:
   - Input string angka
   - Konversi ke number
   - Lakukan operasi aritmatika
   - Konversi hasil ke string
   - Tampilkan semua proses konversi
