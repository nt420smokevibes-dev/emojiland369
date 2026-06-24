# Quick Start Guide

## 🎮 Play Now

### Easiest: No Installation
1. Open [`index.html`](./index.html) directly in your web browser
2. That's it! Start playing.

### Deploy to GitHub Pages (Free Hosting)

1. Push to GitHub:
```bash
git push origin main
```

2. Go to repo Settings → Pages
3. Set source to `main` branch
4. Your game is live at `https://username.github.io/emojiland369`

### Deploy to Netlify (Also Free)

```bash
# Drag and drop index.html to https://app.netlify.com/drop
# Or connect your GitHub repo
```

## 🕹️ First Game: Phonix the Daahog

1. Click on the **Phonix the Daahog** cartridge
2. Use **Arrow Keys** (or **Joystick**) to jump
3. Grab **💍 rings** for points
4. Press **B** to roll through spikes
5. Survive as long as you can!

## 🎯 Controls Quick Ref

| Control | Action |
|---------|--------|
| **Arrow Keys** | Move / Navigate |
| **Z** | A Button (Jump/Shoot) |
| **X** | B Button (Block/Roll/Puff) |
| **Mouse + Drag** | Joystick |
| **Touch Joystick** | Mobile joystick |

## 💻 Local Development

### Simple HTTP Server

```bash
# Python 3
python -m http.server 8000

# Then open http://localhost:8000
```

### Live Reload with npm

```bash
npm install -g live-server
live-server .
```

## 🎮 Game Selection Menu

The main menu shows all 9 available games. Tap any cartridge to:
- See game preview
- Read description
- Press A to play

Press HOME or SEL to return to menu anytime.

## 💬 Tips & Tricks

### Sac-Man
- Eat all dots to win
- Power pellets let you chase ghosts
- Collect scared ghosts for 200 pts

### Super Nario
- Jump on enemies to defeat them
- Avoid standing enemies
- Collect all mushrooms for bonus points

### Phonix the Daahog
- B button creates a ball—roll to break spikes
- Grab rings for points
- Speed is constant, so precision matters

### Dirby's Adventure
- B to puff up and float
- Hold puff to stay airborne
- Grab stars, avoid purple enemies
- Reach the portal to win

## 🔧 Customize

### Change Console Color
Edit `index.html` line in `<style>`:
```css
:root {
  --c-accent: #7c5cfc;  /* Change this to #FF00FF, etc */
  --c-btn-a: #e0344a;   /* Change button colors */
}
```

### Add High Scores
The console currently doesn't save scores between sessions. You could add:
```javascript
// In startGame():
localStorage.setItem('emojiland369_score', score);
```

## 📱 Mobile Tips

- Tap the joystick and drag to move
- Tap action buttons clearly—they're designed for thumb control
- Rotate to landscape for better view (optional)
- Works on iPhone, Android, iPad

## 🐛 Troubleshooting

### Game won't load
- Check browser console (F12)
- Make sure you're opening `index.html` directly
- Try a different browser

### Joystick doesn't respond
- Try keyboard arrows instead (Z/X for buttons)
- Refresh page
- Check if browser has JavaScript enabled

### Score not updating
- This is normal—scores reset when you play again
- To keep high scores, we'd need localStorage

### Emojis look weird
- Different devices render emojis differently
- This is expected and games still work
- Try a different browser or device

## 🚀 Next Steps

1. **Play all 9 games** — Master each one
2. **Read CONTRIBUTING.md** — Add your own game
3. **Fork the repo** — Make it your own
4. **Share it** — Tell your friends!

## 📚 Learn More

- Full documentation: [README.md](./README.md)
- Contributing guide: [CONTRIBUTING.md](./CONTRIBUTING.md)
- Game development: See CONTRIBUTING.md → "Game Development Tips"

---

**Ready to create your own game?** Check out [CONTRIBUTING.md](./CONTRIBUTING.md)!

Have fun! 🎮✨
