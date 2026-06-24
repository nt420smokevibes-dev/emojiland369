# ⚙️ Initial Setup Guide

Welcome to **Emojiland369**! Here's how to set up your GitHub repository.

## 📋 Pre-Flight Checklist

- [ ] Create new GitHub repository named `emojiland369`
- [ ] Clone this template
- [ ] Update repository settings
- [ ] Enable GitHub Pages
- [ ] Customize package.json

---

## 🚀 Setup Steps

### 1. Create GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Repository name: `emojiland369`
3. Description: "A fully playable emoji-based handheld gaming console. 9 games, zero dependencies."
4. Public / Private (your choice)
5. **DO NOT** initialize with README (we have one)
6. Create repository

### 2. Clone This Template

```bash
git clone https://github.com/yourusername/emojiland369.git
cd emojiland369
```

### 3. Update Git Remote

```bash
# If cloning from another source, update origin
git remote set-url origin https://github.com/yourusername/emojiland369.git
```

### 4. Customize `package.json`

Replace the placeholders:

```json
{
  "author": "Your Name",
  "repository": {
    "url": "https://github.com/yourusername/emojiland369.git"
  },
  "bugs": {
    "url": "https://github.com/yourusername/emojiland369/issues"
  },
  "homepage": "https://github.com/yourusername/emojiland369#readme"
}
```

### 5. Update `README.md`

Optional personalization:
- Add your name
- Add preview screenshots
- Add badges (see below)
- Add custom sections

### 6. Enable GitHub Pages

1. Go to repo **Settings** → **Pages**
2. **Source:** Deploy from a branch
3. **Branch:** main / root
4. **Save**
5. Wait 2 minutes
6. Your site is live! 🎉

Link: `https://yourusername.github.io/emojiland369`

### 7. Push to GitHub

```bash
git add .
git commit -m "Initial commit: Emojiland369 handheld console"
git push origin main
```

### 8. Enable Discussions (Optional)

Settings → Features → **Discussions** ✅
Great for community feedback!

---

## 🏷️ GitHub Badges

Add these to your README for visual flair:

### Status Badges
```markdown
![GitHub Pages](https://github.com/yourusername/emojiland369/actions/workflows/pages.yml/badge.svg)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Version 1.0.0](https://img.shields.io/badge/Version-1.0.0-blue.svg)
```

### Stats Badges
```markdown
[![GitHub Stars](https://img.shields.io/github/stars/yourusername/emojiland369?style=social)](https://github.com/yourusername/emojiland369)
[![GitHub Forks](https://img.shields.io/github/forks/yourusername/emojiland369?style=social)](https://github.com/yourusername/emojiland369/fork)
```

### Feature Badges
```markdown
![HTML5](https://img.shields.io/badge/HTML5-E34C26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![No Dependencies](https://img.shields.io/badge/Dependencies-0-brightgreen)
```

---

## 📸 Add Screenshots

1. Play the game and take screenshots
2. Place in root or `docs/` folder
3. Add to README:

```markdown
## 🎮 Screenshots

![Menu](docs/menu.png)
![Sac-Man Gameplay](docs/sacman.png)
![Mobile View](docs/mobile.png)
```

---

## 🔐 Repo Settings

### Branch Protection (Optional)

**Settings** → **Branches** → **Add rule**:

- Branch name pattern: `main`
- ✅ Require pull request reviews before merging
- ✅ Require status checks to pass

This prevents accidental broken deploys.

### Labels (Optional)

Create custom issue labels:
- `bug` (red)
- `enhancement` (blue)
- `game-submission` (purple)
- `documentation` (green)
- `good first issue` (gold)

### Code Owners (Optional)

Create `.github/CODEOWNERS`:

```
# Default owners for everything
* @yourusername

# Game code
GAME_INITS.* @yourusername
```

---

## 👥 Collaboration Setup

### For Team Projects

1. **Add collaborators:** Settings → Collaborators
2. **Create teams** if 3+ people
3. **Set permissions:**
   - Maintain (PR review required)
   - Write (direct push)
   - Read (issues only)

### Code Review Workflow

1. Create feature branch: `git checkout -b feature/new-game`
2. Make changes and commit
3. Push: `git push origin feature/new-game`
4. Open Pull Request on GitHub
5. Request reviews
6. Merge after approval

---

## 🔗 Links to Update

After setup, save these links:

- **Live Game:** `https://yourusername.github.io/emojiland369`
- **Repository:** `https://github.com/yourusername/emojiland369`
- **Issues:** `https://github.com/yourusername/emojiland369/issues`
- **Discussions:** `https://github.com/yourusername/emojiland369/discussions`

---

## 📈 Growth Checklist

After launch:

- [ ] Share on Twitter/X
- [ ] Post on Reddit (r/gamedev, r/javascript)
- [ ] Submit to itch.io
- [ ] Share on product communities
- [ ] Blog post about making it
- [ ] Tutorial on game development
- [ ] Promote contributor issues

---

## 🎓 Documentation Links

- **Start Playing:** [QUICKSTART.md](QUICKSTART.md)
- **Deploy Anywhere:** [DEPLOYMENT.md](DEPLOYMENT.md)
- **Add Your Game:** [CONTRIBUTING.md](CONTRIBUTING.md)
- **Game Design:** [GAME_DESIGN.md](GAME_DESIGN.md)
- **Full Docs:** [README.md](README.md)

---

## 💡 Pro Tips

### Local Development
```bash
# Simple server for testing
python -m http.server 8000
# Open http://localhost:8000
```

### Live Reload
```bash
npm install -g live-server
live-server .
```

### GitHub CLI (Optional)
```bash
# Install: https://cli.github.com/
gh repo create emojiland369 --public --source=. --remote=origin --push
```

---

## 🎉 You're Ready!

Your Emojiland369 repository is set up and ready for the world!

**Next Steps:**
1. ✅ Verify live at your GitHub Pages URL
2. ✅ Share with friends
3. ✅ Accept game contributions
4. ✅ Build a community

---

Questions? Check the [README](README.md) or open an issue!

Happy gaming! 🎮✨
