# 3.5 - Event Handling

Event Handling adalah cara kita menangani interaksi pengguna dengan halaman web. Events adalah aksi yang terjadi di halaman web, seperti klik mouse, penekanan keyboard, atau loading halaman.

## 1. Mouse Events

### Event Dasar
```javascript
element.addEventListener('click', () => {
    // kode yang dijalankan saat klik
});

element.addEventListener('dblclick', () => {
    // kode yang dijalankan saat double klik
});
```

### Mouse Movement
```javascript
// Mouse masuk ke elemen
element.addEventListener('mouseenter', () => {});

// Mouse keluar dari elemen
element.addEventListener('mouseleave', () => {});

// Mouse bergerak di dalam elemen
element.addEventListener('mousemove', (event) => {
    console.log(event.clientX, event.clientY);
});
```

## 2. Keyboard Events

### Keydown & Keyup
```javascript
element.addEventListener('keydown', (event) => {
    console.log(`Key pressed: ${event.key}`);
});

element.addEventListener('keyup', (event) => {
    console.log(`Key released: ${event.key}`);
});
```

### Key Properties
```javascript
element.addEventListener('keydown', (event) => {
    // event.key: karakter yang ditekan
    // event.code: kode fisik tombol
    // event.shiftKey: true jika Shift ditekan
    // event.ctrlKey: true jika Ctrl ditekan
    // event.altKey: true jika Alt ditekan
});
```

## 3. Form Events

### Submit Event
```javascript
form.addEventListener('submit', (event) => {
    event.preventDefault(); // Mencegah form submit default
    // Proses form data
});
```

### Input Events
```javascript
// Saat nilai berubah dan fokus hilang
input.addEventListener('change', (event) => {
    console.log(event.target.value);
});

// Saat nilai berubah (realtime)
input.addEventListener('input', (event) => {
    console.log(event.target.value);
});

// Saat input mendapat fokus
input.addEventListener('focus', () => {});

// Saat input kehilangan fokus
input.addEventListener('blur', () => {});
```

## 4. Event Bubbling & Capturing

### Event Flow
1. Capturing Phase: Event turun dari parent ke target
2. Target Phase: Event mencapai target
3. Bubbling Phase: Event naik dari target ke parent

```javascript
// Bubbling (default)
element.addEventListener('click', handler);

// Capturing
element.addEventListener('click', handler, true);
```

### Stop Propagation
```javascript
element.addEventListener('click', (event) => {
    event.stopPropagation(); // Hentikan bubbling
});
```

## 5. Event Delegation

Pattern untuk menangani events pada multiple elements dengan satu event listener:

```javascript
// Tanpa delegation (tidak efisien)
document.querySelectorAll('.button').forEach(button => {
    button.addEventListener('click', handleClick);
});

// Dengan delegation (lebih efisien)
document.addEventListener('click', (event) => {
    if (event.target.matches('.button')) {
        handleClick(event);
    }
});
```

## 6. Custom Events

### Membuat Custom Event
```javascript
const event = new CustomEvent('userLogin', {
    detail: { userId: 123 }
});

// Dispatch event
element.dispatchEvent(event);
```

### Mendengarkan Custom Event
```javascript
element.addEventListener('userLogin', (event) => {
    console.log(event.detail.userId);
});
```

## 💡 Tips Event Handling

1. **Debouncing Events**
   ```javascript
   function debounce(func, wait) {
       let timeout;
       return function executedFunction(...args) {
           const later = () => {
               clearTimeout(timeout);
               func(...args);
           };
           clearTimeout(timeout);
           timeout = setTimeout(later, wait);
       };
   }

   // Penggunaan
   const debouncedSearch = debounce(() => {
       // search logic
   }, 300);

   input.addEventListener('input', debouncedSearch);
   ```

2. **Throttling Events**
   ```javascript
   function throttle(func, limit) {
       let inThrottle;
       return function(...args) {
           if (!inThrottle) {
               func.apply(this, args);
               inThrottle = true;
               setTimeout(() => inThrottle = false, limit);
           }
       }
   }

   // Penggunaan
   const throttledScroll = throttle(() => {
       // scroll logic
   }, 100);

   window.addEventListener('scroll', throttledScroll);
   ```

3. **Pembersihan Event Listener**
   ```javascript
   const handler = () => {
       console.log('Event handled');
   };

   element.addEventListener('click', handler);

   // Hapus event listener saat tidak diperlukan
   element.removeEventListener('click', handler);
   ```

---

### ✏️ Tugas Kecil

1. Buat Drag and Drop:
   - Buat beberapa kotak yang bisa di-drag
   - Area target untuk drop
   - Visual feedback saat drag dan drop

2. Buat Form dengan Validasi Real-time:
   - Validasi saat user mengetik
   - Tampilkan pesan error
   - Disable submit button jika form tidak valid

3. Buat Simple Game:
   - Kotak yang bisa digerakkan dengan keyboard
   - Deteksi collision dengan obstacles
   - Hitung score
