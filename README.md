# 🎮 Emojiland369

A fully playable emoji-based handheld gaming console built with pure HTML5, Canvas, and JavaScript. No dependencies, no build process—just raw gaming goodness in a retro handheld form factor.

## 🕹️ Games Included

| Game | Genre | Description |
|------|-------|-------------|
| **Sac-Man** | Maze | Navigate the maze, eat dots, avoid 💀 ghosts. Power pellets turn the tables! |
| **Zong** | Sports | Pong-style ball game. Play left paddle vs. AI robot opponent. |
| **Trogdorf** | Action | Be the dragon 🐉 and burninate the countryside with fireballs. |
| **Muscle Birds** | Fighting | Eagle 🦅 vs. Parrot 🦜 one-on-one brawler. Block, punch, dominate. |
| **Super Nario** | Platform | Side-scrolling platformer—collect 🍄, dodge enemies, reach the flag 🚩. |
| **Phonix the Daahog** | Speed | Speedy hedgehog 🦔 runner—grab 💍 rings, roll through spikes with B. |
| **Betroid** | Explore | Top-down sci-fi shooter 🤖. Blast 👾 aliens, collect ⚡ power-ups. |
| **Omega Man** | Shoot | Space Invaders–style wave shooter 🦸. Survive wave after wave. |
| **Dirby's Adventure** | Cute | Float with B, puff up 🎈, collect ⭐ stars, reach the 🌀 portal. |

## 🎯 Controls

### On-Screen
- **Joystick** — Move / Navigate
- **A Button** (red) — Jump / Shoot / Action
- **B Button** (orange) — Block / Roll / Puff / Special
- **X Button** (blue) — Secondary action
- **Y Button** (green) — Primary action
- **L1 / R1** — Shoulder buttons
- **SEL** — Return to menu
- **HOME** — Return to menu

### Keyboard
- **Arrow Keys** — Move / Navigate
- **Z** — A Button
- **X** — B Button

## 🚀 Quick Start

### Play Online
Simply open `index.html` in any modern web browser. No server needed!

```bash
# Clone the repo
git clone https://github.com/yourusername/emojiland369.git
cd emojiland369

# Open in browser (Mac)
open index.html

# Open in browser (Linux)
xdg-open index.html

# Or just drag index.html into your browser
```

### Self-Host
Drop `index.html` on any static web host (GitHub Pages, Netlify, Vercel, etc.).

```bash
# GitHub Pages example
git push origin main
# Then enable Pages in repo settings, pointing to main branch
```

## 🏗️ Project Structure

```
emojiland369/
├── index.html           # Single-file game console (all games included)
├── README.md           # This file
├── LICENSE             # MIT License
├── .gitignore          # Git ignore patterns
└── package.json        # Project metadata (optional)
```

## 💻 Technical Details

### No Dependencies
- Pure HTML5 Canvas rendering
- Vanilla JavaScript (ES6)
- CSS3 with CSS variables for theming
- Responsive design with dvh/dvw units
- Touch + mouse + keyboard support

### Performance
- 60 FPS game loop with requestAnimationFrame
- Pixel-perfect emoji rendering
- Optimized collision detection
- Lightweight file size (~80KB total)

### Browser Support
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

## 🎨 Visual Design

- **Retro Handheld Aesthetic** — Inspired by Game Boy, Sega Game Gear
- **Emoji-Based Graphics** — No sprite sheets needed
- **Dark Theme** — Easy on the eyes, great battery life
- **Responsive UI** — Scales perfectly from phones to desktops

## 🔧 Customization

### Add a New Game

1. Create an init function in `GAME_INITS`:
```javascript
GAME_INITS.newgame = () => {
  const s = gameState = {};
  s.x = 0.5;
  s.y = 0.5;
  // ... initialize game state
};
```

2. Create a loop function in `GAME_LOOPS`:
```javascript
GAME_LOOPS.newgame = () => {
  const s = gameState;
  const cw = W(), ch = H();
  
  // Game logic here
  cls('#07080f');  // Clear screen
  emo('🎮', s.x * cw, s.y * ch, 24);  // Draw emoji
};
```

3. Add to the GAMES array:
```javascript
{id:'newgame', name:'New Game', icon:'🎮✨', genre:'TYPE', color:'#...'};
```

### Change Theme Colors

Edit the CSS variables at the top of `<style>`:
```css
:root {
  --c-body: #1c1c2e;
  --c-accent: #7c5cfc;
  --c-btn-a: #e0344a;
  /* ... etc */
}
```

## 📱 Mobile Optimization

The console adapts to all screen sizes:
- Joystick is touch-friendly and responsive
- Buttons scale with viewport
- Portrait orientation is optimized for 100dvh
- No horizontal scrolling

## 🎮 Game Mechanics Reference

### Collision Detection
All games use simple distance-based collision:
```javascript
const dx = s.x - enemy.x;
const dy = s.y - enemy.y;
if (Math.abs(dx) < 0.07 && Math.abs(dy) < 0.07) {
  // Collision!
}
```

### Scoring System
Points are tracked and displayed in HUD:
- Eat dots: +10 pts (Sac-Man)
- Power pellet: +50 pts
- Enemy defeat: +100-200 pts
- Level clear: +500 pts

### Lives System
Default 3 lives. Lose all → Game Over. Press A to retry.

## 🐛 Known Limitations

- Single-player only (no multiplayer)
- No persistent high scores (browser storage not implemented)
- No sound effects (audio API can be added)
- Fixed 9-game library (can be extended)
- Emoji rendering varies by OS/font (fallbacks work well)

## 📝 License

MIT License — Free to use, modify, and distribute.

## 🤝 Contributing

Want to add more games or improve the console?

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/amazing-game`)
3. Add your game following the pattern above
4. Test thoroughly on mobile and desktop
5. Submit a Pull Request

## 🎓 Learning Resources

### Canvas Basics
- Game state management
- 2D rendering with ctx.fillRect, ctx.arc
- Collision detection math
- Game loop with requestAnimationFrame

### Emoji Rendering
- Using `ctx.font = 'sizepx serif'` for emoji
- Centering emoji with text metrics
- Cross-platform emoji compatibility

### Mobile Touch Events
- touchstart / touchmove / touchend
- Preventing default behaviors
- Passive listeners for performance

## 🌟 Credits

- Inspired by classic Game Boy, Sega Game Gear, and arcade games
- Built with vanilla web technologies
- Emoji from Unicode Consortium

## 🚀 Future Ideas

- [ ] Add WebGL for advanced graphics
- [ ] Multiplayer via WebSockets
- [ ] Local high scores with IndexedDB
- [ ] Level editor
- [ ] Custom game cartridge loader
- [ ] Haptic feedback on mobile
- [ ] Dark/Light theme toggle
- [ ] Chiptune audio with Tone.js
- [ ] Leaderboard integration

## 📧 Support

Found a bug? Have an idea? Open an issue on GitHub!

---

**Emojiland369** — Play. Create. Share. 🎮✨
