# 🚀 Landing Pages Setup Guide (ScaleBrandsLab)

This document explains how your landing page system is structured, how to add new pages, and how to scale it in the future.

---

# 🧩 Current Architecture

* Hosting: Cloudflare Pages
* DNS: Route 53
* Structure: Folder-based static pages

Each landing page is served via:

```
pages.scalebrandslab.com/{slug}
```

Example:

```
pages.scalebrandslab.com/karen-rands
```

---

# 📁 Project Structure

```
landing-pages/
  karen-rands/
    index.html
    favicon.ico
  client-xyz/
    index.html
    favicon.ico
```

Each folder = one landing page

---

# ➕ How to Add a New Landing Page

### Step 1: Create folder

```
/new-client-name/
```

### Step 2: Add index.html

```
/new-client-name/index.html
```

### Step 3: (Optional) Add favicon

```
/new-client-name/favicon.ico
```

### Step 4: Push to GitHub

```
git add .
git commit -m "add new landing page"
git push
```

Cloudflare will auto-deploy 🚀

---

# 🎨 Favicon Setup

## Option 1 — Global favicon (same for all pages)

Place in root:

```
/favicon.ico
```

And add in every HTML file:

```html
<link rel="icon" href="/favicon.ico" />
```

---

## Option 2 — Per-page favicon (recommended)

Inside each folder:

```
/karen-rands/favicon.ico
```

Then in that page:

```html
<link rel="icon" href="./favicon.ico" />
```

This allows branding per client.

---

# 🌐 Domain Setup

Domain:

```
pages.scalebrandslab.com
```

Route 53 config:

* Type: CNAME
* Name: pages.scalebrandslab.com
* Value: landing-pages.pages.dev

---

# ⚡ Performance Best Practices

* Keep pages static (no heavy JS)
* Optimize images
* Avoid large libraries
* Inline critical CSS if possible

---

# 🔥 Future Upgrades

## 1. Template System

Create reusable HTML template:

```
/templates/base.html
```

Then generate pages using data.

---

## 2. Auto-generate pages from data

Use:

* Google Sheets
* CSV
* JSON

Write a script (Node/Python) to generate folders automatically.

---

## 3. Add Forms

Options:

* Formspree
* Custom backend
* Cloudflare Workers (advanced)

---

## 4. Analytics

Add:

* Google Analytics
* PostHog

---

## 5. Move to React (if needed)

Use Vite or Next.js (static export) for templating at scale.

---

# 🧠 Naming Guidelines

Use clean slugs:

```
karen-rands
fitness-coach-delhi
b2b-saas-founder
```

Avoid spaces and uppercase.

---

# 🛑 Common Mistakes

* Missing index.html inside folder
* Wrong favicon path
* Using absolute paths incorrectly
* Editing directly in production without Git

---

# ✅ Summary

* Each folder = one landing page
* Push to GitHub = auto deploy
* Use per-page favicon for flexibility
* Keep it simple and fast

---

If you scale this to 50–100+ pages, move to a template + generation system.