# Image Gallery Project

Proyek Image Gallery ini adalah implementasi galeri foto interaktif menggunakan HTML, CSS, dan JavaScript.

## Fitur

1. Grid layout responsif
2. Modal view untuk gambar besar
3. Navigasi next/previous
4. Keyboard shortcuts
5. Animasi transisi
6. Caption untuk setiap gambar

## Struktur Kode

### HTML
```html
<div class="container">
    <!-- Gallery Grid -->
    <div id="gallery" class="gallery">
        <!-- Thumbnails -->
    </div>

    <!-- Modal -->
    <div id="modal" class="modal">
        <div class="modal-content">
            <img id="modalImage">
            <div class="image-caption"></div>
            <!-- Navigation buttons -->
        </div>
    </div>
</div>
```

### CSS

#### 1. Gallery Grid
```css
.gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 20px;
}

.thumbnail {
    position: relative;
    padding-bottom: 100%;
    overflow: hidden;
}

.thumbnail img {
    position: absolute;
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

#### 2. Modal Styling
```css
.modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.9);
}

.modal-content {
    max-width: 90%;
    max-height: 90vh;
    margin: 40px auto;
}
```

### JavaScript

#### 1. Data Structure
```javascript
const images = [
    {
        url: 'image-url',
        caption: 'Image Caption'
    }
    // ...more images
];
```

#### 2. Gallery Creation
```javascript
function createGallery() {
    images.forEach((image, index) => {
        const thumbnail = document.createElement('div');
        thumbnail.className = 'thumbnail';
        thumbnail.innerHTML = `
            <img src="${image.url}" alt="${image.caption}">
        `;
        thumbnail.addEventListener('click', () => openModal(index));
    });
}
```

#### 3. Modal Functions
```javascript
function openModal(index) {
    currentImageIndex = index;
    modal.style.display = 'block';
    updateModalImage();
}

function updateModalImage() {
    const image = images[currentImageIndex];
    modalImg.src = image.url;
    captionText.textContent = image.caption;
}
```

#### 4. Navigation
```javascript
function showPrevImage() {
    currentImageIndex = (currentImageIndex - 1 + images.length) % images.length;
    updateModalImage();
}

function showNextImage() {
    currentImageIndex = (currentImageIndex + 1) % images.length;
    updateModalImage();
}
```

## Konsep yang Digunakan

1. **CSS Grid**
   - auto-fill dan minmax
   - responsive layout
   - gap property

2. **Position & Layout**
   - Fixed positioning untuk modal
   - Absolute positioning untuk thumbnail images
   - Z-index management

3. **DOM Manipulation**
   - createElement
   - addEventListener
   - style manipulation

4. **Event Handling**
   - Click events
   - Keyboard events
   - Event delegation

5. **Array Methods**
   - forEach
   - Array indexing
   - Modulo operation for cycling

## Pengembangan Lanjutan

1. **Fitur Tambahan**
   - Lazy loading untuk gambar
   - Filter dan kategori
   - Zoom functionality
   - Slideshow mode
   - Touch swipe support

2. **Optimisasi**
   - Image optimization
   - Loading indicators
   - Error handling
   - Progressive loading

3. **UX Improvements**
   - Smooth transitions
   - Gesture controls
   - Accessibility features
   - Loading states

## Tips Implementasi

1. **Image Loading**
   ```javascript
   function preloadImage(url) {
       return new Promise((resolve, reject) => {
           const img = new Image();
           img.onload = () => resolve(img);
           img.onerror = reject;
           img.src = url;
       });
   }
   ```

2. **Lazy Loading**
   ```javascript
   // Using Intersection Observer
   const observer = new IntersectionObserver((entries) => {
       entries.forEach(entry => {
           if (entry.isIntersecting) {
               const img = entry.target;
               img.src = img.dataset.src;
               observer.unobserve(img);
           }
       });
   });
   ```

3. **Touch Events**
   ```javascript
   let touchStartX = 0;
   
   modal.addEventListener('touchstart', e => {
       touchStartX = e.touches[0].clientX;
   });

   modal.addEventListener('touchend', e => {
       const touchEndX = e.changedTouches[0].clientX;
       const diff = touchStartX - touchEndX;

       if (Math.abs(diff) > 50) {
           if (diff > 0) showNextImage();
           else showPrevImage();
       }
   });
   ```

---

### 🎯 Challenge

1. Tambahkan fitur:
   - Zoom in/out pada modal view
   - Filter berdasarkan tag/kategori
   - Slideshow otomatis
   - Download button

2. Improve UI:
   - Loading animations
   - Transisi antar gambar
   - Tema gelap/terang
   - Responsive grid settings

3. Optimisasi:
   - Lazy loading
   - Image compression
   - Cache management
   - Error handling
