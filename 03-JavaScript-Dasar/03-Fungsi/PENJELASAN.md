# 3.3 - Fungsi dalam JavaScript

Fungsi adalah blok kode yang dapat digunakan kembali (reusable) yang melakukan tugas tertentu. Fungsi adalah salah satu konsep fundamental dalam JavaScript yang memungkinkan kita untuk mengorganisir dan menyederhanakan kode.

## 1. Deklarasi Fungsi (Function Declaration)

Cara paling umum untuk membuat fungsi:

```javascript
function namaFungsi(parameter1, parameter2) {
    // kode yang akan dijalankan
    return hasil;
}
```

Contoh:
```javascript
function sayHello(nama) {
    return `Hello, ${nama}!`;
}

// Memanggil fungsi
sayHello('Budi'); // Output: "Hello, Budi!"
```

## 2. Expression Fungsi (Function Expression)

Fungsi yang disimpan dalam variabel:

```javascript
const namaFungsi = function(parameter1, parameter2) {
    // kode yang akan dijalankan
    return hasil;
};
```

Contoh:
```javascript
const hitungLuas = function(panjang, lebar) {
    return panjang * lebar;
};

// Memanggil fungsi
hitungLuas(5, 3); // Output: 15
```

## 3. Arrow Function

Cara modern dan singkat untuk menulis fungsi:

```javascript
// Bentuk dasar
const fungsi = (param1, param2) => {
    return hasil;
};

// Bentuk singkat (implicit return)
const fungsi = (param1, param2) => hasil;
```

Contoh:
```javascript
const tambah = (a, b) => a + b;
const kali = (a, b) => a * b;

tambah(5, 3); // Output: 8
kali(4, 2);   // Output: 8
```

## 4. Parameter dan Return

### Parameter
- Nilai yang dikirim ke fungsi
- Bisa memiliki banyak parameter
- Urutan parameter penting

```javascript
function hitungTotal(harga, jumlah, diskon) {
    const total = harga * jumlah;
    const potongan = total * (diskon / 100);
    return total - potongan;
}

hitungTotal(10000, 2, 10); // 2 barang @10000, diskon 10%
```

### Return
- Nilai yang dikembalikan fungsi
- Fungsi berhenti setelah return
- Jika tidak ada return, fungsi mengembalikan undefined

```javascript
function cekUmur(umur) {
    if (umur < 17) {
        return "Belum cukup umur";
    }
    return "Sudah cukup umur";
}
```

## 5. Parameter Default

Parameter bisa memiliki nilai default jika tidak ada nilai yang diberikan:

```javascript
function sapa(nama = 'Tamu') {
    return `Selamat datang, ${nama}!`;
}

sapa();        // Output: "Selamat datang, Tamu!"
sapa('Ani');   // Output: "Selamat datang, Ani!"
```

## 6. Callback Function

Fungsi yang dikirim sebagai parameter ke fungsi lain:

```javascript
// Contoh dengan array methods
const angka = [1, 2, 3, 4, 5];

// filter() menggunakan callback
const lebihDariDua = angka.filter(num => num > 2);

// map() menggunakan callback
const kaliDua = angka.map(num => num * 2);
```

## 💡 Tips Penggunaan Fungsi

1. **Gunakan Nama yang Jelas**
   ```javascript
   // Buruk
   function f(x, y) { return x + y; }
   
   // Baik
   function hitungTotal(harga, jumlah) { return harga * jumlah; }
   ```

2. **Satu Fungsi, Satu Tugas**
   ```javascript
   // Buruk
   function prosesData(data) {
       // Filter data
       // Sortir data
       // Tampilkan data
   }
   
   // Baik
   function filterData(data) { ... }
   function sortirData(data) { ... }
   function tampilkanData(data) { ... }
   ```

3. **Gunakan Arrow Function untuk Kode Pendek**
   ```javascript
   // Sebelum
   const tambah = function(a, b) { return a + b; };
   
   // Sesudah
   const tambah = (a, b) => a + b;
   ```

4. **Validasi Parameter**
   ```javascript
   function hitungLuas(panjang, lebar) {
       if (typeof panjang !== 'number' || typeof lebar !== 'number') {
           throw new Error('Parameter harus berupa angka');
       }
       return panjang * lebar;
   }
   ```

---

### ✏️ Tugas Kecil

1. Buat fungsi untuk menghitung nilai rata-rata dari array:
   ```javascript
   function hitungRataRata(nilai) {
       // Tulis kode di sini
   }
   ```

2. Buat fungsi untuk membalik string:
   ```javascript
   function balikString(text) {
       // Tulis kode di sini
   }
   ```

3. Buat fungsi untuk mencari nilai terbesar dan terkecil dalam array:
   ```javascript
   function minMax(arr) {
       // Return object dengan min dan max
       // Contoh: { min: 1, max: 10 }
   }
   ```

4. Buat arrow function untuk mengubah celcius ke fahrenheit:
   ```javascript
   const celciusToFahrenheit = /* Tulis kode di sini */
   ```
