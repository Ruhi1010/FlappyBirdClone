# FLAPPY BIRD

A visually enhanced Flappy Bird clone using **Pygame**, featuring:
- Neon aesthetic with animated backgrounds and particles
- Smooth bird animation and glowing UI
- Scoring and collision system
- Restart and game over logic

---

## 📦 Modules Used

```python
import pygame
import random
import math
```

- **pygame**: Main game engine for graphics and input.
- **random**: For generating random values (e.g., pipe gaps, particles).
- **math**: For trigonometric animations and smooth transitions.

---

## 🎨 Color Scheme

Defined in a dictionary for consistency, using vibrant neon tones.

```python
COLORS = {
  'bg_start': (20, 20, 40),       # Background gradient start
  'bg_end': (80, 40, 120),        # Background gradient end
  ...
}
```

---

## 🌀 Particle Class

Represents floating background or action particles (e.g., jump sparks, score effect).

### Methods:

- `__init__`: Initializes particle with velocity, color, and lifetime.
- `update()`: Moves particle and applies gravity.
- `draw(screen)`: Draws with fading opacity over time.

---

## 🐦 Bird Class

Controls bird movement, animation, physics, glow, trail, and particle effects.

### Attributes:

- `x`, `y`: Position
- `velocity`: Vertical speed affected by gravity
- `trail_points`: For tail effect
- `particles`: Jump/spark particles
- `rotation`: For tilt effect during motion
- `glow_size`: For pulse animation

### Methods:

- `update()`: Handles gravity, movement, glow animation, trail trimming.
- `jump()`: Resets velocity upwards and spawns burst particles.
- `draw(screen)`: Renders the bird with layered elements (glow, body, beak, eye, wing).
- `get_rect()`: Returns collision rectangle.

---

## 🧱 Pipe Class

Represents a pair of top and bottom pipes the bird must avoid.

### Attributes:

- `x`: Horizontal position
- `gap_y`: Vertical center of pipe gap
- `passed`: Used to track scoring
- `glow_intensity`: Used to create pulsating neon effects

### Methods:

- `update()`: Moves pipe left; updates glow pulse.
- `draw(screen)`: Draws both pipes with glow, border, and cap.
- `get_rects()`: Returns two collision rectangles.

---

## 🕹️ Game Class

Main controller for logic, UI, background, and game loop.

### Key Functions:

#### `__init__()`
- Sets up the window, clock, fonts, and initial state.

#### `reset_game()`
- Resets bird, pipes, background particles, score, and game state.

#### `draw_animated_background()`
- Draws vertical color gradient with particles in the background.

#### `draw_glowing_text(text, font, color, glow_color, pos)`
- Renders text with a glowing multi-layer shadow effect.

#### `draw_ui()`
- Shows title, instructions, score, or game over screens depending on game state.

#### `update()`
- Handles:
  - Bird movement
  - Pipe updates
  - Collision checks
  - Score tracking
  - Spawning new pipes

#### `draw()`
- Calls all draw methods: background, pipes, bird, UI.

#### `handle_events()`
- Keyboard input:
  - `SPACE`: Flap/start game
  - `R`: Restart
  - `ESC`: Quit

#### `run()`
- Main game loop handling updates, events, and drawing at a fixed `FPS`.

---

## 📈 Game Flow Summary

1. Title screen waits for player to press `SPACE`.
2. Game starts:
   - Pipes scroll left
   - Bird flaps upward on space
   - Colliding with pipe or floor ends game
   - Player scores by passing pipes
3. After death:
   - "Game Over" appears
   - Press `R` to restart or `ESC` to quit

---

## 🧠 Design Highlights

- **Neon aesthetic** using layered glows, animated gradients, and vibrant colors.
- **Animated UI elements** (title float, pulsing instructions).
- **Particle systems** for dynamic feedback on jump/score.
- **Smooth physics and visual polish** using trigonometric easing.

---

## 🧪 Running the Game

Make sure `pygame` is installed:

```bash
pip install pygame
```

Then run:

```bash
python neon_flappy_bird.py
```

---

## 🏁 Controls

| Key       | Action             |
|-----------|--------------------|
| `SPACE`   | Flap / Start Game  |
| `R`       | Restart after death|
| `ESC`     | Exit game          |

---

## 📸 Screenshots (Optional)

- **Title screen**
- **Gameplay with particles**
- **Game Over screen with overlay**

---

## ✅ Future Enhancements

- Add sound effects
- High score tracking
- Difficulty scaling
- Touch support (mobile)

---
