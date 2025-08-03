# Mini Game Project

Proyek Mini Game ini adalah implementasi sederhana dari game berbasis Canvas menggunakan HTML, CSS, dan JavaScript.

## Fitur

1. Player movement dengan keyboard
2. Collision detection
3. Scoring system
4. Spawn coins dan obstacles
5. Game over state
6. Restart functionality

## Struktur Kode

### HTML & CSS
```html
<div class="game-container">
    <canvas id="gameCanvas"></canvas>
    <div class="game-info">
        <!-- Score dan controls -->
    </div>
    <div class="game-over">
        <!-- Game over screen -->
    </div>
</div>
```

```css
.game-canvas {
    border: 2px solid #333;
    background-color: white;
}

.game-info {
    margin-top: 20px;
    padding: 20px;
    background-color: white;
}
```

### JavaScript

#### 1. Game Objects
```javascript
const player = {
    x: 50,
    y: canvas.height / 2,
    width: 30,
    height: 30,
    speed: 5,
    color: '#3498db'
};

const coins = [];
const obstacles = [];
```

#### 2. Movement Control
```javascript
const keys = {
    left: false,
    right: false,
    up: false,
    down: false
};

function handleKeyDown(e) {
    switch(e.key) {
        case 'ArrowLeft':
        case 'a':
            keys.left = true;
            break;
        // ... handle other keys
    }
}
```

#### 3. Game Loop
```javascript
function updateGame() {
    // Update player position
    if (keys.left) player.x -= player.speed;
    // ... handle other movements

    // Spawn objects
    spawnCoins();
    spawnObstacles();

    // Update objects
    updateCoins();
    updateObstacles();

    // Check collisions
    checkCollisions();

    // Draw everything
    drawGame();
}
```

## Konsep yang Digunakan

1. **Canvas API**
   - Drawing shapes
   - Clearing canvas
   - Animation frame

2. **Event Handling**
   - Keyboard events
   - Game loop
   - Collision detection

3. **Object-Oriented Programming**
   - Game objects
   - Properties dan methods
   - State management

4. **Game Development Concepts**
   - Game loop
   - Sprite movement
   - Collision detection
   - Scoring system

## Pengembangan Lanjutan

1. **Fitur Gameplay**
   - Power-ups
   - Different enemies
   - Levels system
   - High score

2. **Visual Improvements**
   - Sprite graphics
   - Animations
   - Particle effects
   - Background

3. **Game Mechanics**
   - Different movement patterns
   - Multiple lives
   - Special abilities
   - Boss battles

## Tips Implementasi

1. **Sprite Animation**
   ```javascript
   class Sprite {
       constructor(options) {
           this.image = options.image;
           this.frameWidth = options.frameWidth;
           this.frameHeight = options.frameHeight;
           this.currentFrame = 0;
       }

       animate() {
           ctx.drawImage(
               this.image,
               this.currentFrame * this.frameWidth,
               0,
               this.frameWidth,
               this.frameHeight,
               this.x,
               this.y,
               this.width,
               this.height
           );
       }
   }
   ```

2. **Particle System**
   ```javascript
   class Particle {
       constructor(x, y) {
           this.x = x;
           this.y = y;
           this.velocity = {
               x: (Math.random() - 0.5) * 5,
               y: (Math.random() - 0.5) * 5
           };
           this.radius = Math.random() * 3;
           this.life = 1;
       }

       update() {
           this.x += this.velocity.x;
           this.y += this.velocity.y;
           this.life -= 0.01;
       }

       draw() {
           ctx.beginPath();
           ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2);
           ctx.fill();
       }
   }
   ```

3. **Power-up System**
   ```javascript
   class PowerUp {
       constructor(type) {
           this.type = type;
           this.duration = 5000; // 5 seconds
           this.active = false;
       }

       activate() {
           this.active = true;
           setTimeout(() => {
               this.deactivate();
           }, this.duration);
       }

       deactivate() {
           this.active = false;
       }
   }
   ```

---

### 🎯 Challenge

1. Tambahkan fitur:
   - Multiple levels
   - Power-ups
   - Different enemies
   - Boss battles

2. Improve gameplay:
   - Smooth animations
   - Sound effects
   - Background music
   - Particle effects

3. Add features:
   - High score system
   - Different player characters
   - Achievement system
   - Mobile controls
