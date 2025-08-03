# Todo List Project

Proyek Todo List ini adalah implementasi sederhana dari aplikasi manajemen tugas menggunakan HTML, CSS, dan JavaScript.

## Fitur

1. Menambah todo
2. Menandai todo sebagai selesai
3. Menghapus todo
4. Penyimpanan di localStorage
5. Responsive design

## Struktur Kode

### HTML
```html
<div class="container">
    <!-- Input Section -->
    <div class="input-section">
        <input type="text" id="todoInput">
        <button onclick="addTodo()">Tambah</button>
    </div>

    <!-- Todo List -->
    <ul id="todoList" class="todo-list">
        <!-- Todo items -->
    </ul>
</div>
```

### CSS
```css
/* Container styling */
.container {
    max-width: 600px;
    margin: 0 auto;
    background-color: white;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

/* Todo item styling */
.todo-item {
    display: flex;
    align-items: center;
    padding: 10px;
    background-color: #f9f9f9;
    margin-bottom: 10px;
    border-radius: 4px;
}

/* Completed todo styling */
.todo-item.completed .todo-text {
    text-decoration: line-through;
    color: #888;
}
```

### JavaScript

#### 1. Data Management
```javascript
// Load data from localStorage
let todos = JSON.parse(localStorage.getItem('todos')) || [];

// Save data to localStorage
localStorage.setItem('todos', JSON.stringify(todos));
```

#### 2. Render Function
```javascript
function renderTodos() {
    todoList.innerHTML = '';
    
    todos.forEach((todo, index) => {
        const li = document.createElement('li');
        li.className = `todo-item ${todo.completed ? 'completed' : ''}`;
        
        // Add todo content
        li.innerHTML = `
            <input type="checkbox" class="checkbox">
            <span class="todo-text">${todo.text}</span>
            <button class="delete-btn">Hapus</button>
        `;
    });
}
```

#### 3. CRUD Operations
```javascript
// Create
function addTodo() {
    const text = todoInput.value.trim();
    if (text) {
        todos.push({ text, completed: false });
        renderTodos();
    }
}

// Update
function toggleTodo(index) {
    todos[index].completed = !todos[index].completed;
    renderTodos();
}

// Delete
function deleteTodo(index) {
    todos.splice(index, 1);
    renderTodos();
}
```

## Konsep yang Digunakan

1. **DOM Manipulation**
   - createElement()
   - innerHTML
   - appendChild()
   - Event Listeners

2. **Array Methods**
   - push()
   - splice()
   - forEach()

3. **Local Storage**
   - setItem()
   - getItem()
   - JSON.parse()
   - JSON.stringify()

4. **Event Handling**
   - click events
   - change events
   - keypress events

5. **CSS Concepts**
   - Flexbox
   - Transitions
   - Box Shadow
   - Border Radius

## Pengembangan Lanjutan

1. **Fitur Tambahan**
   - Kategori untuk todo
   - Due date
   - Priority levels
   - Filter dan sorting

2. **Perbaikan UX**
   - Animasi
   - Drag and drop
   - Undo delete
   - Bulk actions

3. **Optimisasi**
   - Pagination untuk list panjang
   - Caching yang lebih baik
   - Validasi input

## Tips Pengembangan

1. **Struktur Data**
   ```javascript
   // Format data yang lebih kompleks
   const todo = {
       id: Date.now(),
       text: "Todo text",
       completed: false,
       createdAt: new Date(),
       category: "personal",
       priority: "high"
   };
   ```

2. **Validasi Input**
   ```javascript
   function validateInput(text) {
       if (!text) return "Text tidak boleh kosong";
       if (text.length < 3) return "Text terlalu pendek";
       return null; // valid
   }
   ```

3. **Error Handling**
   ```javascript
   try {
       const todos = JSON.parse(localStorage.getItem('todos'));
   } catch (error) {
       console.error('Error loading todos:', error);
       todos = [];
   }
   ```

---

### 🎯 Challenge

1. Tambahkan fitur:
   - Edit todo text
   - Due date untuk setiap todo
   - Filter berdasarkan status (complete/incomplete)

2. Improve UI:
   - Animasi saat add/delete
   - Konfirmasi sebelum delete
   - Dark mode toggle

3. Optimisasi:
   - Tambahkan validation
   - Implementasi error handling
   - Buat kode lebih modular
