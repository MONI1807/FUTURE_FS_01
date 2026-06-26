# 🌸 Monika — Developer Portfolio

A clean, responsive, single-file portfolio website built with vanilla HTML, CSS, and JavaScript.

**Live site:** [your-username.github.io/portfolio](https://your-username.github.io/portfolio)

---

## ✨ Features

- **Responsive design** — works on mobile, tablet, and desktop
- **Pixel-art avatar** — custom SVG character coded in CSS
- **Scroll-reveal animations** — elements fade in as you scroll
- **Animated skills ticker** — auto-scrolling tech stack strip
- **Projects section** — showcases all portfolio-grade work
- **Timeline** — education & experience at a glance
- **Contact form** — with client-side validation (ready for Formspree)
- **SEO meta tags** — Open Graph + description tags included
- **Single file** — no build tools, no dependencies, no frameworks

---

## 🛠️ Tech Stack

| Layer      | Tech                        |
|------------|-----------------------------|
| Markup     | HTML5 (semantic)            |
| Styling    | CSS3 (custom properties, grid, flexbox, animations) |
| Scripting  | Vanilla JavaScript (ES6+)   |
| Fonts      | Google Fonts (Space Grotesk, Inter, JetBrains Mono) |

---

## 🚀 Deployment (GitHub Pages — Free)

1. **Fork or clone this repo**
   ```bash
   git clone https://github.com/your-username/portfolio.git
   cd portfolio
   ```

2. **Personalise the content** (see section below)

3. **Push to GitHub**
   ```bash
   git add .
   git commit -m "My portfolio"
   git push origin main
   ```

4. **Enable GitHub Pages**
   - Go to your repo → Settings → Pages
   - Source: `Deploy from a branch` → `main` → `/ (root)`
   - Your site goes live at `https://your-username.github.io/portfolio`

---

## ✏️ Personalising Your Content

Open `index.html` and find these sections to update:

| What to change | Where to find it |
|---|---|
| Your name | `<title>`, `.nav-logo`, `hero h1` |
| Hero description | `.hero-desc` paragraph |
| About text | Three `.about-text` paragraphs in the About section |
| Skills list | `.skills-list` divs + `.skills-scroll` chips |
| Projects | Each `.project-card` in the Projects section |
| Timeline | Each `.timeline-item` in the Experience section |
| Contact links | Three `.contact-link-item` anchors |
| Social links | `.footer-socials` anchors + contact section |
| GitHub links | All `href="https://github.com"` — replace with your real URLs |

---

## 📧 Making the Contact Form Actually Send Emails

The form is wired up with validation but needs a backend to send emails. The easiest free option:

1. Sign up at [formspree.io](https://formspree.io) (free tier: 50 submissions/month)
2. Create a new form — you'll get an endpoint like `https://formspree.io/f/xabc1234`
3. In `index.html`, replace the `handleSubmit()` function's setTimeout block:

```javascript
async function handleSubmit() {
  // ... validation code stays the same ...
  
  const response = await fetch('https://formspree.io/f/YOUR_FORM_ID', {
    method: 'POST',
    headers: { 'Accept': 'application/json' },
    body: JSON.stringify({
      name: first,
      email: email,
      subject: document.getElementById('subject').value,
      message: message
    })
  });
  
  if (response.ok) {
    document.getElementById('successMsg').style.display = 'block';
    document.querySelector('.form-submit').style.display = 'none';
  }
}
```

---

## 📁 Project Structure

```
portfolio/
└── index.html      # Everything — HTML, CSS, and JS in one file
└── README.md       # This file
```

---

## 📝 License

Feel free to use this as a starting point for your own portfolio. If you do, a star on the repo would be appreciated! ⭐

---

*Built as Task 1 of the Future Interns Full Stack Web Development program — 2026*