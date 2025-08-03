# Form Validator Project

Proyek Form Validator ini adalah implementasi validasi form secara real-time menggunakan HTML, CSS, dan JavaScript.

## Fitur

1. Validasi real-time
2. Password strength meter
3. Custom error messages
4. Visual feedback
5. Form submission handling
6. Responsive design

## Struktur Kode

### HTML
```html
<form id="validationForm" novalidate>
    <div class="form-group">
        <label>Label</label>
        <input type="text">
        <div class="error"></div>
    </div>
    <!-- More form groups -->
</form>
```

### CSS

#### 1. Form Styling
```css
.form-group {
    margin-bottom: 20px;
}

input {
    width: 100%;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 4px;
    transition: border-color 0.3s;
}

.error {
    color: #ff4444;
    font-size: 14px;
    margin-top: 5px;
    display: none;
}
```

#### 2. Validation States
```css
input.valid {
    border-color: #4CAF50;
}

input.invalid {
    border-color: #ff4444;
}

.success-message {
    color: #4CAF50;
    background-color: #e8f5e9;
    padding: 10px;
    border-radius: 4px;
}
```

### JavaScript

#### 1. Validation Patterns
```javascript
const patterns = {
    name: /^[a-zA-Z\s]{3,}$/,
    email: /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/,
    password: /^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$/
};
```

#### 2. Field Validation
```javascript
function validateField(input, pattern, errorElement, messages) {
    const value = input.value.trim();
    
    if (!value) {
        showError(errorElement, messages.empty);
        return false;
    }
    
    if (!pattern.test(value)) {
        showError(errorElement, messages.invalid);
        return false;
    }
    
    hideError(errorElement);
    return true;
}
```

#### 3. Password Strength
```javascript
function checkPasswordStrength(password) {
    let strength = 0;
    
    if (password.length >= 8) strength++;
    if (password.match(/[a-zA-Z]/)) strength++;
    if (password.match(/[0-9]/)) strength++;
    if (password.match(/[^a-zA-Z0-9]/)) strength++;

    return strength;
}
```

## Konsep yang Digunakan

1. **Regular Expressions**
   - Pattern matching
   - Email validation
   - Password requirements

2. **Form Validation**
   - Real-time validation
   - Custom validation messages
   - Form submission handling

3. **DOM Manipulation**
   - Adding/removing classes
   - Showing/hiding elements
   - Event handling

4. **CSS Transitions**
   - Smooth color changes
   - Error message animations
   - Password strength meter

## Pengembangan Lanjutan

1. **Fitur Tambahan**
   - Password visibility toggle
   - Custom validation rules
   - Form data persistence
   - AJAX submission

2. **UX Improvements**
   - Better error highlighting
   - Tooltip messages
   - Keyboard navigation
   - Accessibility features

3. **Validasi Tambahan**
   - Phone number format
   - Username availability
   - Complex password rules
   - File upload validation

## Tips Implementasi

1. **Custom Validation Rules**
   ```javascript
   const validators = {
       minLength: (value, min) => value.length >= min,
       maxLength: (value, max) => value.length <= max,
       pattern: (value, regex) => regex.test(value),
       required: value => value.trim().length > 0
   };
   ```

2. **Async Validation**
   ```javascript
   async function checkUsername(username) {
       try {
           const response = await fetch(`/api/check-username?username=${username}`);
           const data = await response.json();
           return data.available;
       } catch (error) {
           console.error('Error:', error);
           return false;
       }
   }
   ```

3. **Form Data Handling**
   ```javascript
   const formData = new FormData(form);
   const data = Object.fromEntries(formData.entries());

   // Kirim data
   async function submitForm(data) {
       try {
           const response = await fetch('/api/submit', {
               method: 'POST',
               headers: {
                   'Content-Type': 'application/json'
               },
               body: JSON.stringify(data)
           });
           return await response.json();
       } catch (error) {
           console.error('Error:', error);
       }
   }
   ```

---

### 🎯 Challenge

1. Tambahkan validasi untuk:
   - Nomor telepon
   - Username (cek ketersediaan)
   - Upload file (size & type)
   - Tanggal lahir

2. Improve UX dengan:
   - Password visibility toggle
   - Autocomplete suggestions
   - Better error animations
   - Progress indicator

3. Tambah fitur:
   - Multi-step form
   - Data persistence
   - AJAX submission
   - Social media integration
