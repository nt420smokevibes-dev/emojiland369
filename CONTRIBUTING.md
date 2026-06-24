# Contributing to Emojiland369

Thanks for your interest in contributing! This project welcomes all kinds of contributions.

## How to Contribute

### 1. Report Bugs
Found a bug? Open an issue with:
- Clear title and description
- Steps to reproduce
- Expected vs. actual behavior
- Browser/device info
- Screenshot if visual issue

### 2. Suggest Features
Have an idea? Open an issue with:
- Use case description
- Why it would be useful
- Any reference implementations

### 3. Add a New Game

#### Step 1: Plan Your Game
- Choose a name (creative emoji-based pun welcome!)
- Pick a genre (Maze, Shooter, Platformer, etc.)
- Sketch game mechanics on paper

#### Step 2: Implement Game State (GAME_INITS)

```javascript
GAME_INITS.yourgame = () => {
  const s = gameState = {};
  
  // Initialize all game variables here
  s.x = 0.5;           // Player X (0-1 normalized coords)
  s.y = 0.5;           // Player Y
  s.vx = 0;            // Velocity X
  s.vy = 0;            // Velocity Y
  s.tick = 0;          // Frame counter
  s.enemies = [];      // Array of enemies
  s.score = 0;         // Internal score
  s.gameOver = false;  // Game state
  
  // Populate enemies/obstacles/collectibles
  for(let i = 0; i < 5; i++) {
    s.enemies.push({x: Math.random(), y: Math.random(), alive: true});
  }
};
```

#### Step 3: Implement Game Loop (GAME_LOOPS)

```javascript
GAME_LOOPS.yourgame = () => {
  const s = gameState;
  const cw = W(), ch = H();  // Canvas width/height
  s.tick++;
  
  // Handle input
  if(keys.left) s.x -= 0.015;
  if(keys.right) s.x += 0.015;
  if(keys.a && s.tick % 12 === 0) {
    // Fire bullet or action
  }
  
  // Update game logic
  s.enemies.forEach(e => {
    e.x += Math.sin(s.tick * 0.01) * 0.001;  // Wavy movement
  });
  
  // Collision detection
  s.enemies.forEach(e => {
    if(Math.abs(s.x - e.x) < 0.07 && Math.abs(s.y - e.y) < 0.07) {
      e.alive = false;
      setScore(score + 100);
    }
  });
  
  // Clear screen
  cls('#07080f');
  
  // Draw game
  s.enemies.forEach(e => {
    if(e.alive) emo('👾', e.x * cw, e.y * ch, 20);
  });
  emo('🎮', s.x * cw, s.y * ch, 24);
  
  // Win/loss condition
  if(s.gameOver) {
    cls('rgba(0,0,0,.7)');
    txt('GAME OVER', cw/2 - 40, ch/2, '#ff4040', 16);
    txt('A to retry', cw/2 - 32, ch/2 + 18, '#a080ff', 11);
    if(keys.a) {
      keys.a = false;
      GAME_INITS.yourgame();
    }
  }
};
```

#### Step 4: Register Game in GAMES Array

```javascript
const GAMES = [
  // ... existing games ...
  {
    id: 'yourgame',
    name: 'Your Game Name',
    icon: '🎮✨',
    genre: 'ACTION',
    color: '#FF00FF'
  }
];
```

#### Step 5: Test

- Play on desktop (Chrome, Firefox, Safari)
- Test on mobile (iOS Safari, Android Chrome)
- Test all buttons and joystick
- Check score/lives display
- Verify win/loss conditions
- Ensure A to retry works

### 4. Improve Existing Code

- Bug fixes
- Performance optimization
- Accessibility improvements
- Code cleanup
- Documentation

### 5. Submit Your Contribution

1. Fork the repository
2. Create a feature branch:
   ```bash
   git checkout -b feature/your-game-name
   ```
3. Make your changes
4. Test thoroughly
5. Commit with clear messages:
   ```bash
   git commit -m "Add: YourGame - [genre] game with [mechanic]"
   ```
6. Push to your fork:
   ```bash
   git push origin feature/your-game-name
   ```
7. Open a Pull Request with:
   - Description of changes
   - Screenshots/GIFs if visual
   - How to test
   - Browser/device tested on

## Code Style Guidelines

### Naming
- Games: lowercase, no spaces (e.g., `yourgame`)
- Variables: camelCase (e.g., `playerScore`)
- Constants: UPPERCASE (e.g., `GRAVITY`)
- Emojis: Use as asset names (e.g., `emo('🐉', ...)`)

### Formatting
- Use 2-space indentation
- Keep functions under 200 lines
- Add comments for complex logic
- Use descriptive variable names

### Game Conventions
- Use normalized 0-1 coordinates
- Collision size ~0.06-0.08 units
- Emoji size 16-30px
- Score updates with `setScore()`
- Lives updates with `setLives()`

## Game Development Tips

### Collision Detection
```javascript
// Simple circle collision
const dist = Math.sqrt((x1-x2)**2 + (y1-y2)**2);
if(dist < 0.07) { /* hit */ }

// Rectangular (AABB)
if(x1 < x2+w2 && x1+w1 > x2 &&
   y1 < y2+h2 && y1+h1 > y2) { /* hit */ }
```

### Smooth Movement
```javascript
// Lerp toward target
const speed = 0.02;
x += (targetX - x) * speed;
y += (targetY - y) * speed;
```

### Animation
```javascript
// Sine wave
const offset = Math.sin(tick * 0.05) * 0.1;
emo('👾', x * cw, (y + offset) * ch, 20);
```

### Random Generation
```javascript
// Random position
const x = Math.random() * 0.8 + 0.1;  // 0.1 to 0.9
const y = Math.random() * 0.6 + 0.2;  // 0.2 to 0.8

// Random from array
const choice = array[Math.floor(Math.random() * array.length)];
```

## Testing Checklist

Before submitting:
- [ ] Game runs without console errors
- [ ] Joystick controls work
- [ ] All buttons respond
- [ ] Score updates correctly
- [ ] Lives display accurately
- [ ] Win condition works
- [ ] Lose/retry works
- [ ] Tested on mobile
- [ ] Tested on desktop
- [ ] No lag at 60 FPS

## Questions?

Open an issue with the label `question` and we'll help!

## Code of Conduct

- Be respectful and inclusive
- Help others learn
- Give constructive feedback
- Have fun! 🎮

---

Happy coding! 🚀
