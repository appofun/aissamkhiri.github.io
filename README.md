# Aissam Khiri — AissamKhiri.com

Private minimal personal domain page.  
Built with pure HTML, CSS, and vanilla JavaScript. No framework. No build step.

---

## Tech Stack

| Layer | Tech |
|-------|------|
| Markup | HTML5 (semantic) |
| Styles | CSS3 (variables, glassmorphism, animations) |
| Scripts | Vanilla JavaScript (ES6+, Canvas particles, IntersectionObserver) |
| Fonts | Google Fonts (Space Grotesk + Inter) |
| Hosting | GitHub Pages |
| DNS / SSL | Cloudflare |

---

## Project Files

| File | Purpose |
|------|---------|
| `index.html` | Main page |
| `style.css` | Dark theme, glassmorphism, animations |
| `script.js` | Particles, fade-in, form handler, scroll |
| `CNAME` | Custom domain (`aissamkhiri.com`) |
| `README.md` | This file |

---

## Deployment

### 1 — Upload Files to GitHub

```bash
git init
git branch -m main
git add .
git commit -m "Initial commit — aissamkhiri.com"
gh repo create YOUR_USERNAME/aissamkhiri --public --source=. --remote=origin --push
```

### 2 — Enable GitHub Pages

1. Go to your repository → **Settings → Pages**
2. **Source** → Deploy from a branch
3. **Branch** → main → / (root)
4. Click **Save**

### 3 — Connect the Custom Domain

1. In Settings → Pages, enter `aissamkhiri.com` in **Custom domain** → Save
2. Confirm `CNAME` file contains: `aissamkhiri.com`
3. Wait 15–60 minutes for DNS propagation
4. Enable **Enforce HTTPS**

### 4 — Cloudflare Setup

**Add DNS records (point to GitHub Pages):**

| Type | Name | Content | Proxy |
|------|------|---------|-------|
| A | @ | 185.199.108.153 | DNS only (grey) |
| A | @ | 185.199.109.153 | DNS only (grey) |
| A | @ | 185.199.110.153 | DNS only (grey) |
| A | @ | 185.199.111.153 | DNS only (grey) |
| CNAME | www | YOUR_USERNAME.github.io | DNS only (grey) |

**SSL/TLS settings:**
- SSL mode: Full
- Always Use HTTPS: On
- Automatic HTTPS Rewrites: On

### 5 — Contact Form (Static Hosting)

The form is UI only by default and shows a JavaScript alert.

**To connect a real form service:**

| Service | Free tier | Setup |
|---------|-----------|-------|
| [Formspree](https://formspree.io) | 50/month | `action="https://formspree.io/f/YOUR_ID"` + `method="POST"` |
| [Getform](https://getform.io) | 50/month | `action="https://getform.io/f/YOUR_ID"` + `method="POST"` |
| [Web3Forms](https://web3forms.com) | 250/month | `action` + hidden `access_key` input |
| [Tally](https://tally.so) | Unlimited | Replace form with Tally embed |
| [Basin](https://usebasin.com) | 50/month | `action="https://usebasin.com/f/YOUR_ID"` + `method="POST"` |

**Steps for Formspree:**
1. Sign up at formspree.io → create form → copy endpoint URL
2. In `index.html`, update `<form>`:
   ```html
   <form class="contact-form glass-card" action="https://formspree.io/f/YOUR_ID" method="POST">
   ```
3. Remove or comment out `initForm()` in `script.js`

---

*© 2026 AissamKhiri.com*
