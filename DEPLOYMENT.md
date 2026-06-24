# 🚀 Deployment Guide

Deploy Emojiland369 in seconds to any platform.

## GitHub Pages (Recommended - Free Forever)

### Setup

1. Go to your repo **Settings** → **Pages**
2. Under "Build and deployment":
   - **Source**: Deploy from a branch
   - **Branch**: `main` / `root`
3. Save and wait ~2 minutes
4. Your site is live at `https://yourusername.github.io/emojiland369`

### Auto-Deploy with GitHub Actions

A workflow file (`.github/workflows/pages.yml`) is included. It auto-deploys on every `push` to `main`.

```bash
git push origin main
# Automatically deploys!
```

---

## Netlify (Free + Custom Domain)

### Option 1: Drag & Drop
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag `index.html` into the drop zone
3. Instant deploy at random URL
4. Claim with email to get custom domain

### Option 2: Connect GitHub
1. Go to [app.netlify.com](https://app.netlify.com)
2. Click "New site from Git"
3. Connect your GitHub repo
4. Netlify auto-deploys on push
5. Get instant HTTPS and custom domain

---

## Vercel (Free + Super Fast)

1. Go to [vercel.com](https://vercel.com)
2. Click "New Project"
3. Import your GitHub repo
4. Hit Deploy
5. Get a live URL instantly

Vercel provides:
- Automatic HTTPS
- Global CDN
- Lightning-fast response times
- Free tier forever

---

## Self-Hosted (Your Own Server)

### Node.js + Express

```javascript
// server.js
const express = require('express');
const app = express();
app.use(express.static('.'));
app.listen(3000, () => console.log('Live on :3000'));
```

```bash
npm install express
node server.js
# Open http://localhost:3000
```

### Python SimpleHTTPServer

```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000

# Open http://localhost:8000
```

### Nginx

```nginx
server {
    listen 80;
    server_name example.com;
    
    root /var/www/emojiland369;
    index index.html;
    
    location / {
        try_files $uri $uri/ =404;
    }
}
```

```bash
sudo systemctl restart nginx
```

### Docker

```dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
EXPOSE 80
```

```bash
docker build -t emojiland369 .
docker run -p 8080:80 emojiland369
# Open http://localhost:8080
```

---

## AWS S3 + CloudFront

1. Create S3 bucket
2. Enable "Static website hosting"
3. Upload `index.html`
4. Create CloudFront distribution
5. Point to S3 bucket

Free tier covers the first 12 months!

---

## Firebase Hosting (Google)

```bash
npm install -g firebase-tools
firebase login
firebase init hosting
# Choose current folder
firebase deploy
```

Instant global CDN with free tier.

---

## itch.io (Game Hosts)

1. Go to [itch.io](https://itch.io)
2. Create account
3. Click "New Project"
4. Upload `index.html`
5. Mark as "HTML" game
6. Get instant link

Great for game jams and sharing with gamedev community!

---

## Custom Domain Setup

### Point Domain to GitHub Pages
```
NameServer 1: ns-123.awsdns-12.com
NameServer 2: ns-456.awsdns-34.org
```

### Add CNAME
Create `CNAME` file in root:
```
yourdomain.com
```

### Netlify Custom Domain
1. In Netlify dashboard: Domain settings
2. Add your domain
3. Point nameservers to Netlify
4. Automatic SSL cert!

---

## Performance Tips

### Minify (Optional)
```bash
# Minify HTML/CSS/JS in one file
npm install -g minify
minify index.html > index.min.html
```

### CDN Headers
```
Cache-Control: max-age=31536000
Content-Encoding: gzip
```

### Lazy Load
Not needed for this project—it's tiny and instant!

---

## SEO + Sharing

Add this to `<head>` in index.html:

```html
<meta name="description" content="Play 9 emoji-based games on a retro handheld console">
<meta name="keywords" content="games, console, emoji, arcade, retro">
<meta property="og:title" content="Emojiland369 - Handheld Console">
<meta property="og:description" content="Play emoji games on a virtual handheld">
<meta property="og:image" content="screenshot.png">
<meta property="og:url" content="https://yourdomain.com">
```

---

## Monitoring

### GitHub Pages
- Deployment status in Actions tab
- Auto rollback on build failure

### Netlify
- Status page included
- 100% uptime SLA
- Free HTTPS

### Vercel
- Real-time analytics
- Automatic rollback
- Edge functions available

---

## Troubleshooting

### 404 Errors
- Ensure `index.html` is in root
- Check file permissions (644 for files, 755 for dirs)
- Clear browser cache (Ctrl+Shift+Delete)

### HTTPS Not Working
- Wait 5-10 minutes after deploy
- Check DNS propagation
- Force refresh (Ctrl+F5)

### Performance Slow
- Enable gzip compression
- Use a CDN (Vercel, Netlify, CloudFront)
- Minimize redirects
- Check with Lighthouse (DevTools)

---

## Recommended Setup

**For Most Users:**
→ GitHub Pages (free, simple, automatic)

**For Best Performance:**
→ Vercel or Netlify (global CDN, instant)

**For Learning:**
→ Docker on DigitalOcean ($5/month)

**For Maximum Reach:**
→ itch.io (game community)

---

Good luck with your deployment! 🚀
