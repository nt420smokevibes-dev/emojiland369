# Game Design Template

Use this template when designing a new game for Emojiland369.

---

## 📋 Game Overview

**Title:** [Game Name]  
**Emoji Pun:** [Creative name/reference]  
**Genre:** [Action/Puzzle/Shooter/etc]  
**Difficulty:** Easy / Medium / Hard  
**Target Audience:** Casual / Hardcore / Everyone  
**Play Time:** 1-5 min per round  
**Release Date:** [When you plan to submit]

---

## 🎮 Core Mechanics

### Primary Control
- Movement: [Joystick/Keys]
- Jump/Action: [A Button]
- Secondary: [B Button]

### Game Loop
1. [What happens every frame]
2. [How does player interact]
3. [What's the objective]

### Win Condition
- [How does player win?]
- [Points/Goals needed]
- [Difficulty progression]

### Lose Condition
- [How does player lose?]
- [Health system?]
- [Lives system?]

---

## 🎨 Visual Design

### Emoji Palette
- **Player:** 🎮 (or your choice)
- **Enemy:** 👾 (or your choice)
- **Collectible:** 💎 (or your choice)
- **Background Color:** #000000 (hex)
- **Accent Color:** #FF00FF (hex)

### Screen Layout
```
[Status Bar - Score/Lives/Name]
[              ]
[  Game Area   ]
[   (Canvas)   ]
[              ]
[Status Bar 2  ]
```

### Sprite/Emoji Sizes
- Player emoji: 22-26px
- Enemy emoji: 18-24px
- Collectible: 12-18px
- Background: Full canvas

---

## 🎯 Game Rules

### Scoring System
| Action | Points |
|--------|--------|
| Collect item | +10 |
| Defeat enemy | +50-100 |
| [Custom] | +??? |

### Difficulty Scaling
- **Wave 1:** [Easier]
- **Wave 2:** [Moderate]
- **Wave 3+:** [Hard]

### Special Mechanics
- [Power-ups?]
- [Boss fights?]
- [Levels?]

---

## 💻 Technical Specs

### Canvas Usage
- Resolution: Dynamic (scales to container)
- Render: Canvas 2D context
- FPS: 60 (using requestAnimationFrame)

### Normalized Coordinates
- X axis: 0.0 (left) to 1.0 (right)
- Y axis: 0.0 (top) to 1.0 (bottom)
- Player start: (0.5, 0.5)

### Collision Detection
- Type: Distance-based or AABB
- Collision radius: 0.06-0.08 units
- Hit accuracy: Frame-perfect

### Performance Budget
- Max objects: ~50 (enemies + projectiles)
- Max particles: ~100
- Target FPS: 60 locked
- File size: Keep index.html < 200KB

---

## 🎮 Input Binding

| Input | Action |
|-------|--------|
| Joystick Left | Move left |
| Joystick Right | Move right |
| Joystick Up | Move up / Jump |
| Joystick Down | Move down |
| A Button (Red) | Primary action |
| B Button (Orange) | Secondary action |
| X Button (Blue) | Tertiary action (optional) |
| Y Button (Green) | Tertiary action (optional) |

### Mobile Optimization
- Joystick should be 60px+ diameter
- Action buttons should be 40px+ diameter
- Tap area should be generous (thumb-friendly)
- No hover states (mobile doesn't have hover)

---

## 🧪 Testing Checklist

### Before Submission

**Functionality:**
- [ ] Game initializes without errors
- [ ] All controls respond immediately
- [ ] Score updates correctly
- [ ] Lives display correctly
- [ ] Win condition triggers properly
- [ ] Lose condition triggers properly
- [ ] Retry (A button) restarts cleanly

**Performance:**
- [ ] Maintains 60 FPS throughout
- [ ] No stutters or frame drops
- [ ] No console errors (F12)
- [ ] Smooth joystick movement
- [ ] No memory leaks (Dev Tools)

**Compatibility:**
- [ ] Works on Chrome 90+
- [ ] Works on Firefox 88+
- [ ] Works on Safari 14+
- [ ] Works on iOS Safari
- [ ] Works on Android Chrome
- [ ] Works with keyboard
- [ ] Works with touchscreen
- [ ] Responsive to window resize

**Gameplay:**
- [ ] Difficulty feels balanced
- [ ] Game is fun (or satisfying)
- [ ] Controls feel responsive
- [ ] Visual feedback is clear
- [ ] Win/lose states are obvious
- [ ] Game loop is engaging

---

## 📊 Example Game: Sac-Man

```
Title: Sac-Man
Genre: Maze
Mechanic: Collect dots, avoid ghosts

Controls:
  Arrow Keys = Navigate maze
  A Button = (N/A)
  B Button = (N/A)

Score: +10 per dot, +50 power pellet, +200 scared ghost
Lives: 3
Win: Eat all dots
Lose: Hit ghost 3 times
Emojis: 🟡 (player), 💀 (ghost), 🟡 (dot)

Canvas: 13x11 grid
Collision: Pixel-perfect maze collision
```

---

## 🚀 Development Workflow

1. **Design Phase** (Day 1)
   - Sketch game on paper
   - Write down all rules
   - Plan emoji/colors
   - Fill out this template

2. **Implementation Phase** (Day 2-3)
   - Code GAME_INITS function
   - Code GAME_LOOPS function
   - Add to GAMES array
   - Test controls

3. **Polish Phase** (Day 3-4)
   - Tweak difficulty
   - Add visual effects
   - Test on multiple devices
   - Fix bugs

4. **Submission Phase** (Day 5)
   - Fill PR template
   - Add screenshots
   - Request review
   - Iterate on feedback

---

## 📝 Code Template

```javascript
// Initialization
GAME_INITS.yourgame = () => {
  const s = gameState = {};
  s.x = 0.5;
  s.y = 0.5;
  s.tick = 0;
  s.score = 0;
  s.gameOver = false;
  // Add more state variables...
};

// Game Loop
GAME_LOOPS.yourgame = () => {
  const s = gameState;
  const cw = W(), ch = H();
  s.tick++;
  
  // Handle input
  if(keys.left) s.x -= 0.02;
  if(keys.right) s.x += 0.02;
  
  // Update logic
  s.x = Math.max(0.04, Math.min(0.96, s.x));
  
  // Render
  cls('#07080f');  // Clear
  emo('🎮', s.x * cw, s.y * ch, 24);  // Draw
  
  // Game over condition
  if(s.gameOver) {
    cls('rgba(0,0,0,.7)');
    txt('GAME OVER', cw/2 - 40, ch/2, '#ff4040', 16);
    if(keys.a) { keys.a = false; GAME_INITS.yourgame(); }
  }
};

// Register
const GAMES = [
  // ... existing ...
  {id:'yourgame', name:'Your Game', icon:'🎮✨', genre:'ACTION', color:'#FF00FF'}
];
```

---

## 🎓 Tips & Tricks

### Make it Fun
- Clear feedback for actions
- Rewarding progression
- Increasing difficulty
- Compelling visuals

### Make it Balanced
- Easy to learn, hard to master
- Not too easy (boring)
- Not too hard (frustrating)
- Test with friends

### Make it Fast
- Keep code clean
- Minimize calculations
- Cache common values
- Profile with DevTools

### Make it Pretty
- Consistent color scheme
- Thematic emoji choices
- Clear UI feedback
- Smooth animations

---

Good luck making your game! 🚀🎮
