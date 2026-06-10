# Khalil Abdullahi Muhammad — Developer Portfolio

![Portfolio Preview](https://img.shields.io/badge/Status-Live-brightgreen?style=flat-square)
![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react&logoColor=black)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)
![Vercel](https://img.shields.io/badge/Deployed_on-Vercel-000000?style=flat-square&logo=vercel&logoColor=white)

> Full-Stack Developer & Engineer based in Abuja, Nigeria 🇳🇬 — building modern web systems, management platforms, and document solutions.

## 🌐 Live Demo

**[→ View Portfolio](https://khalil-portfolio.vercel.app)**

---

## ✨ Features

- 🎨 Modern dark/light mode UI with electric indigo & cyan palette
- ⚡ Animated particle canvas hero with typewriter role switcher
- 📱 Fully responsive — mobile, tablet, desktop
- 🌀 Scroll-triggered animations and smooth transitions
- 🧩 Interactive project cards with expandable feature lists
- 📊 Filterable skills section with animated progress bars
- 📬 Contact form with send animation
- 🔝 Active section navbar highlighting + scroll-to-top

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| UI Framework | React 18 (via CDN) |
| Styling | Tailwind CSS (via CDN) |
| Animations | CSS keyframes + Canvas API |
| Fonts | Space Grotesk · Inter · Fira Code |
| Deployment | Vercel |

## 📁 Project Structure

```
khalil-portfolio/
├── index.html          # Complete portfolio (single-file app)
├── vercel.json         # Vercel deployment config
├── .gitignore          # Git ignore rules
└── README.md           # This file
```

## 🚀 Local Development

No build tools needed. Just open the file:

```bash
# Option 1 — Open directly in browser
open index.html

# Option 2 — Serve with Python (recommended)
python3 -m http.server 3000
# Then visit: http://localhost:3000

# Option 3 — Use VS Code Live Server extension
# Right-click index.html → "Open with Live Server"
```

## 📦 Deployment (Vercel)

See [DEPLOYMENT.md](./DEPLOYMENT.md) for the full step-by-step guide.

**Quick deploy:**
1. Push this repo to GitHub
2. Import at [vercel.com/new](https://vercel.com/new)
3. Click **Deploy** — done ✓

## ✏️ Customization

Edit `index.html` and update these sections inside the `<script type="text/babel">` block:

| Section | What to Update |
|---|---|
| `PROJECTS` array | Your real project details |
| `SKILLS` array | Add/remove skills & proficiency levels |
| `contactLinks` | Your real email, LinkedIn, GitHub, phone |
| Hero bio text | Your personal introduction |
| CV download `href` | Link to your hosted CV/resume PDF |

## 📬 Contact Form Setup

The contact form UI is ready. To make it functional, connect one of:

- **[Formspree](https://formspree.io)** — Free, no backend needed
- **[EmailJS](https://emailjs.com)** — Send emails directly from JS
- **[Web3Forms](https://web3forms.com)** — Simple & free

See [DEPLOYMENT.md](./DEPLOYMENT.md) for Formspree setup instructions.

## 📄 License

MIT © 2025 Khalil Abdullahi Muhammad
