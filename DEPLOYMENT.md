# 🚀 Complete Deployment Guide
## Khalil Abdullahi Muhammad — Portfolio on Vercel

**For beginners — every step explained clearly.**

---

## 📋 Table of Contents

1. [What You'll Need](#what-youll-need)
2. [Your Project Files](#your-project-files)
3. [Step 1 — Install Git](#step-1--install-git)
4. [Step 2 — Initialize Git Locally](#step-2--initialize-git-locally)
5. [Step 3 — Create GitHub Repository](#step-3--create-github-repository)
6. [Step 4 — Push to GitHub](#step-4--push-to-github)
7. [Step 5 — Deploy on Vercel](#step-5--deploy-on-vercel)
8. [Step 6 — Your Live URL](#step-6--your-live-url)
9. [Updating Your Portfolio](#updating-your-portfolio)
10. [Connect a Custom Domain](#connect-a-custom-domain)
11. [Set Up Contact Form (Formspree)](#set-up-contact-form-formspree)
12. [Production Optimization Tips](#production-optimization-tips)
13. [Troubleshooting](#troubleshooting)

---

## What You'll Need

| Tool | Purpose | Free? |
|---|---|---|
| [Git](https://git-scm.com/downloads) | Version control | ✅ Free |
| [GitHub account](https://github.com/signup) | Host your code | ✅ Free |
| [Vercel account](https://vercel.com/signup) | Host your website | ✅ Free |
| A terminal / command prompt | Run commands | Built-in |

> **What is Git?** Git is a tool that tracks changes to your files — like a save history for your code.
>
> **What is GitHub?** A website where you store your code online so Vercel (and others) can access it.
>
> **What is Vercel?** A free hosting platform that takes your GitHub code and puts it live on the internet.

---

## Your Project Files

Your project folder should look like this:

```
khalil-portfolio/        ← Your project folder
├── index.html           ← Your complete portfolio
├── vercel.json          ← Tells Vercel how to deploy
├── .gitignore           ← Tells Git what NOT to upload
└── README.md            ← Project description
```

> **Important:** The main file MUST be named `index.html` (not `khalil-portfolio.html`).
> Rename it if needed before starting.

---

## Step 1 — Install Git

### Windows:
1. Go to https://git-scm.com/download/win
2. Download and run the installer
3. Keep all default options and click Next → Finish
4. Open **Git Bash** (search for it in Start menu)

### Mac:
```bash
# Open Terminal and run:
xcode-select --install
# A popup will appear — click Install
```

### Linux (Ubuntu/Debian):
```bash
sudo apt update
sudo apt install git -y
```

### Verify Git is installed:
```bash
git --version
# Should output something like: git version 2.43.0
```

### Set your identity (one-time setup):
```bash
# Replace with YOUR name and email (use the same email as your GitHub account)
git config --global user.name "Khalil Abdullahi Muhammad"
git config --global user.email "your-email@example.com"
```

---

## Step 2 — Initialize Git Locally

Open your terminal and navigate to your project folder.

```bash
# 1. Navigate to your project folder
#    Replace the path with wherever you saved your portfolio files
cd /path/to/khalil-portfolio

# On Windows it might look like:
cd C:\Users\Khalil\Documents\khalil-portfolio

# On Mac/Linux:
cd ~/Documents/khalil-portfolio
```

```bash
# 2. Initialize Git in this folder
#    This creates a hidden .git folder that tracks your files
git init

# Expected output:
# Initialized empty Git repository in /path/to/khalil-portfolio/.git/
```

```bash
# 3. Check which files Git can see
git status

# You'll see all your files listed in red (untracked = not saved yet)
```

```bash
# 4. Stage ALL files (tell Git "I want to save these")
git add .
# The dot (.) means "add everything in this folder"
```

```bash
# 5. Commit — save a snapshot of your files with a message
git commit -m "Initial commit: Khalil portfolio"

# Expected output:
# [main (root-commit) abc1234] Initial commit: Khalil portfolio
# 4 files changed, 850 insertions(+)
```

> ✅ **What just happened?** You've saved a snapshot of your project locally.
> Think of it like pressing Ctrl+S, but smarter — it remembers the full history.

---

## Step 3 — Create GitHub Repository

1. **Go to GitHub:** https://github.com
2. **Sign in** (or sign up if you don't have an account)
3. Click the **green "New"** button (top left, next to the Repositories heading)
   — OR go to https://github.com/new

4. Fill in the form:
   - **Repository name:** `khalil-portfolio`
   - **Description:** `My personal developer portfolio — Full-Stack Developer based in Abuja, Nigeria`
   - **Visibility:** Public ✅ (Vercel free tier requires public repos — or connect a paid plan for private)
   - **DO NOT** check "Add a README file" (you already have one)
   - **DO NOT** add .gitignore (you already have one)

5. Click **"Create repository"** (green button at the bottom)

6. GitHub will show you a page with setup commands. **Copy your repository URL** — it looks like:
   ```
   https://github.com/YOUR-USERNAME/khalil-portfolio.git
   ```

---

## Step 4 — Push to GitHub

Back in your terminal:

```bash
# 1. Tell Git where your GitHub repository is
#    Replace YOUR-USERNAME with your actual GitHub username
git remote add origin https://github.com/YOUR-USERNAME/khalil-portfolio.git

# Example:
# git remote add origin https://github.com/khalil-dev/khalil-portfolio.git
```

```bash
# 2. Rename your branch to "main" (modern GitHub standard)
git branch -M main
```

```bash
# 3. Push (upload) your code to GitHub
git push -u origin main

# You'll be asked for your GitHub username and password.
# NOTE: GitHub no longer accepts your regular password here.
# You need a Personal Access Token instead. See below ↓
```

### 🔑 GitHub Authentication (Personal Access Token)

GitHub removed password login for Git in 2021. You need a token:

1. On GitHub, click your **profile picture** (top right) → **Settings**
2. Scroll down the left sidebar → **Developer settings** (very bottom)
3. Click **Personal access tokens** → **Tokens (classic)**
4. Click **"Generate new token (classic)"**
5. Give it a name: `portfolio-deploy`
6. Set **Expiration:** 90 days (or No expiration)
7. Check the **`repo`** scope checkbox (first big checkbox)
8. Scroll down → Click **"Generate token"**
9. **COPY THE TOKEN NOW** — you won't see it again!

When Git asks for your password, **paste the token** instead.

```bash
# After pushing, verify it worked:
git push -u origin main

# Expected output:
# Enumerating objects: 6, done.
# Counting objects: 100% (6/6), done.
# Writing objects: 100% (6/6), 245 KiB | 1.2 MiB/s, done.
# Branch 'main' set up to track remote branch 'main' from 'origin'.
```

> ✅ **Check:** Go to `https://github.com/YOUR-USERNAME/khalil-portfolio`
> You should see your files there!

---

## Step 5 — Deploy on Vercel

### Method A — Vercel Dashboard (Recommended for Beginners)

1. Go to https://vercel.com and click **"Sign Up"**
2. Choose **"Continue with GitHub"** — this links your accounts automatically
3. Authorize Vercel to access your GitHub
4. You'll land on the Vercel dashboard
5. Click **"Add New..."** → **"Project"**
6. You'll see your GitHub repositories listed
7. Find **`khalil-portfolio`** and click **"Import"**
8. Vercel auto-detects it's a static site — no configuration needed
9. Leave all settings as default
10. Click the big **"Deploy"** button

Watch the deployment log — it takes about 30–60 seconds.

**You'll see a success screen with confetti 🎉**

---

### Method B — Vercel CLI (Advanced / Faster for updates)

```bash
# 1. Install Vercel CLI globally
npm install -g vercel

# 2. Login to Vercel
vercel login
# Opens your browser — click "Continue with GitHub"

# 3. Deploy from your project folder
cd /path/to/khalil-portfolio
vercel

# It will ask you some questions:
# ? Set up and deploy ~/khalil-portfolio? → Y
# ? Which scope? → Your username
# ? Link to existing project? → N
# ? What's your project's name? → khalil-portfolio
# ? In which directory is your code located? → ./
# Vercel will detect the framework automatically

# 4. For production deployment:
vercel --prod
```

---

## Step 6 — Your Live URL

After deployment, Vercel gives you:

- **Project URL:** `https://khalil-portfolio.vercel.app`
- **Unique deployment URL:** `https://khalil-portfolio-abc123.vercel.app`

> Every time you push to GitHub, Vercel **automatically redeploys** your site. No manual steps needed!

Add your live URL to:
- ✅ Your `README.md`
- ✅ Your GitHub profile
- ✅ Your LinkedIn profile
- ✅ Your CV/resume

---

## Updating Your Portfolio

This is the workflow every time you want to change something:

```bash
# 1. Make your changes in index.html (update projects, skills, contact info, etc.)

# 2. Navigate to your project folder
cd /path/to/khalil-portfolio

# 3. Check what you changed
git status
# Shows modified files in red

git diff index.html
# Shows exactly what lines changed (green = added, red = removed)

# 4. Stage your changes
git add .
# Or stage a specific file: git add index.html

# 5. Commit with a descriptive message
git commit -m "Update: added new project XYZ"
# Other example messages:
# "Fix: update contact email"
# "Feature: add new skills section"
# "Update: refresh project descriptions"

# 6. Push to GitHub
git push

# That's it! Vercel detects the push and automatically redeploys.
# Your live site updates in ~30 seconds ✅
```

### Check deployment status:
- Go to https://vercel.com/dashboard
- Click your project → **Deployments** tab
- See live logs for every deployment

---

## Connect a Custom Domain

### Option A — Buy from Namecheap / GoDaddy / Cloudflare

1. Buy your domain: e.g., `khalilmuhammad.dev` or `khalildev.com`
   - Recommended registrar: [Namecheap](https://namecheap.com) (~$10–12/year)
   - Or [Cloudflare Registrar](https://cloudflare.com/products/registrar/) (at-cost pricing)

2. In Vercel dashboard:
   - Go to your project → **Settings** → **Domains**
   - Click **"Add Domain"**
   - Type your domain: `khalilmuhammad.dev`
   - Click **Add**

3. Vercel shows you DNS records to add. Two options:

   **If using Namecheap/GoDaddy:**
   - Log into your domain registrar
   - Find **DNS Settings** or **Advanced DNS**
   - Add these records Vercel gives you:
     ```
     Type: A
     Host: @
     Value: 76.76.21.21    (Vercel's IP)
     
     Type: CNAME
     Host: www
     Value: cname.vercel-dns.com
     ```

   **If using Cloudflare (recommended):**
   - Add your domain to Cloudflare
   - Add the A and CNAME records above
   - Set SSL/TLS to "Full"

4. Wait 5–30 minutes for DNS to propagate
5. Vercel automatically provisions an **SSL certificate** (HTTPS) for free — using Let's Encrypt

> ✅ Your portfolio will be live at `https://khalilmuhammad.dev` with a green padlock!

---

## Set Up Contact Form (Formspree)

Your contact form UI is built — now make it actually send emails:

### Using Formspree (Free — 50 submissions/month)

1. Go to https://formspree.io and sign up (free)
2. Click **"New Form"** → name it "Portfolio Contact"
3. Copy your **Form ID** (looks like `xpwzabcd`)

4. In `index.html`, find the `handleSubmit` function:
   ```javascript
   const handleSubmit = (e) => {
     e.preventDefault();
     setSending(true);
     setTimeout(() => { setSent(true); setSending(false); }, 1500);
   };
   ```

5. Replace it with:
   ```javascript
   const handleSubmit = async (e) => {
     e.preventDefault();
     setSending(true);
     try {
       const response = await fetch('https://formspree.io/f/YOUR-FORM-ID', {
         method: 'POST',
         headers: { 'Content-Type': 'application/json' },
         body: JSON.stringify({
           name: form.name,
           email: form.email,
           subject: form.subject,
           message: form.message,
         }),
       });
       if (response.ok) {
         setSent(true);
       } else {
         alert('Something went wrong. Please try emailing me directly.');
       }
     } catch (err) {
       alert('Network error. Please email me directly.');
     }
     setSending(false);
   };
   ```

6. Replace `YOUR-FORM-ID` with your actual Formspree form ID
7. Save, commit, and push — the form will now send real emails to your inbox!

---

## Production Optimization Tips

### 1. Performance

Your portfolio loads React via CDN. To maximize speed:

```html
<!-- Already in your HTML — these load fast from unpkg CDN -->
<!-- For even faster loading, consider switching to:
     https://cdn.jsdelivr.net/npm/react@18/umd/react.production.min.js
     (production build is ~3x smaller)                              -->
```

Replace in `index.html`:
```html
<!-- BEFORE (development build — larger) -->
<script src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>

<!-- AFTER (production build — smaller, faster) -->
<script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
```

### 2. Add a Favicon

Create a small icon for your browser tab:

```html
<!-- Add inside <head> in index.html -->
<link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>👨‍💻</text></svg>" />
```

### 3. Open Graph Image (LinkedIn/Twitter previews)

Add a preview image so your portfolio looks great when shared on social media:

```html
<!-- Add inside <head> -->
<meta property="og:image" content="https://your-domain.com/og-image.png" />
<meta property="og:url" content="https://khalilmuhammad.dev" />
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:image" content="https://your-domain.com/og-image.png" />
```

Create a 1200×630px screenshot of your portfolio and upload it to your repo as `og-image.png`.

### 4. Analytics (Optional — Free)

Track who visits your portfolio:

```html
<!-- Add before </head> — replace UA-XXXXXXX with your Vercel Analytics token -->
<!-- Vercel Analytics (easiest — built into Vercel dashboard) -->
<script>
  window.va = window.va || function () { (window.vaq = window.vaq || []).push(arguments); };
</script>
<script defer src="/_vercel/insights/script.js"></script>
```

Enable in Vercel: Project Settings → Analytics → Enable

---

## Troubleshooting

### ❌ "git: command not found"
Git isn't installed. Go back to [Step 1](#step-1--install-git).

### ❌ "Permission denied (publickey)"
Use HTTPS URLs instead of SSH:
```bash
git remote set-url origin https://github.com/YOUR-USERNAME/khalil-portfolio.git
```

### ❌ "Authentication failed" when pushing
You need a Personal Access Token — see the [authentication section](#-github-authentication-personal-access-token) above.

### ❌ Vercel shows "404 Not Found"
Make sure your file is named **`index.html`** (not `portfolio.html` or anything else). Vercel looks for `index.html` by default.

### ❌ Fonts not loading on live site
Your HTML already uses Google Fonts via CDN — they should load fine. If blocked, the system font (`sans-serif`) will be used as fallback.

### ❌ Changes not showing after push
1. Wait 1–2 minutes for Vercel to redeploy
2. Hard-refresh your browser: `Ctrl + Shift + R` (Windows) or `Cmd + Shift + R` (Mac)
3. Check Vercel dashboard → Deployments to see if the new deployment succeeded

### ❌ "fatal: not a git repository"
You're not in the right folder. Use `cd` to navigate into your `khalil-portfolio` folder first.

---

## Quick Reference Card

```bash
# ── First-time setup ─────────────────────────
git init                          # Initialize git
git add .                         # Stage all files
git commit -m "Initial commit"    # Save snapshot
git remote add origin <URL>       # Link to GitHub
git branch -M main                # Rename branch
git push -u origin main           # Upload to GitHub

# ── Every future update ──────────────────────
git add .                         # Stage changes
git commit -m "Your message"      # Save snapshot
git push                          # Upload → Vercel auto-deploys

# ── Useful git commands ──────────────────────
git status                        # See what changed
git log --oneline                 # See commit history
git diff                          # See exact changes
git pull                          # Download latest from GitHub
```

---

**Questions?** Open an issue on your GitHub repository or reach out via the contact form on the live portfolio.

*Happy deploying! 🚀*
