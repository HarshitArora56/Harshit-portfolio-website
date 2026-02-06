# 🚀 Deployment Guide - GitHub Pages

Complete step-by-step guide to deploy your portfolio on GitHub Pages (100% FREE)

## Prerequisites

✅ GitHub account (create at [github.com](https://github.com))  
✅ Git installed on your computer  
✅ All portfolio files ready

## 📋 Deployment Steps

### Step 1: Prepare Your Files

Ensure you have these files in one folder:
```
my-portfolio/
├── index.html
├── styles.css
├── script.js
├── assets/
│   ├── profile.jpg
│   ├── maritime-port.jpg
│   ├── netflix-analytics.jpg
│   ├── churn-prediction.jpg
│   └── Harshit_Arora_Resume.pdf
├── README.md
└── .gitignore
```

### Step 2: Install Git (If Not Installed)

**Windows:**
- Download from [git-scm.com](https://git-scm.com/download/win)
- Run installer with default settings
- Open "Git Bash" from Start Menu

**Mac:**
- Open Terminal
- Run: `git --version`
- If not installed, it will prompt installation

**Linux:**
```bash
sudo apt-get install git  # Ubuntu/Debian
sudo yum install git      # CentOS/Fedora
```

### Step 3: Initialize Git Repository

Open terminal/command prompt in your project folder:

```bash
# Navigate to your project folder
cd path/to/my-portfolio

# Initialize git
git init

# Add all files
git add .

# Make first commit
git commit -m "Initial commit - Portfolio website"
```

### Step 4: Create GitHub Repository

**Option A: Personal Website (Recommended)**

1. Go to [github.com](https://github.com)
2. Click **"+"** → **"New repository"**
3. Repository name: **`yourusername.github.io`** (replace with YOUR username)
   - Example: `HarshitArora56.github.io`
4. Keep it **Public**
5. **Don't** initialize with README (we already have files)
6. Click **"Create repository"**

**Option B: Project Repository**

1. Repository name: **`portfolio`** (or any name)
2. Your site will be at: `yourusername.github.io/portfolio`

### Step 5: Connect and Push to GitHub

Copy the commands from GitHub (shown after creating repo):

```bash
# Add remote repository
git remote add origin https://github.com/yourusername/yourusername.github.io.git

# Rename branch to main (if needed)
git branch -M main

# Push to GitHub
git push -u origin main
```

**First time pushing?** Git will ask for credentials:
- Username: your GitHub username
- Password: your GitHub password or Personal Access Token

**Personal Access Token (if password doesn't work):**
1. GitHub → Settings → Developer settings
2. Personal access tokens → Tokens (classic)
3. Generate new token
4. Select scopes: `repo` (all)
5. Copy token and use as password

### Step 6: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **"Settings"** tab
3. Scroll to **"Pages"** in left sidebar
4. Under **"Source"**:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **"Save"**

### Step 7: Wait for Deployment

- GitHub will show: "Your site is ready to be published at..."
- Wait 2-5 minutes for first deployment
- Check the Actions tab to see deployment progress

### Step 8: Access Your Live Website! 🎉

**Personal website:** `https://yourusername.github.io`  
**Project repository:** `https://yourusername.github.io/repository-name`

## 🔄 Updating Your Website

Made changes? Push updates:

```bash
# Save changes
git add .

# Commit with message
git commit -m "Updated projects section"

# Push to GitHub
git push
```

Changes will be live in 1-2 minutes!

## 🎨 Custom Domain (Optional)

Want `www.harshitarora.com` instead of `username.github.io`?

### Buy a Domain
- Namecheap: ~$10/year
- GoDaddy: ~$15/year
- Google Domains: ~$12/year

### Configure DNS

**In your domain provider:**
1. Add A records pointing to GitHub:
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```
2. Add CNAME record:
   - Host: `www`
   - Value: `yourusername.github.io`

**In GitHub Pages settings:**
1. Enter your custom domain
2. Check "Enforce HTTPS"
3. Wait 24 hours for DNS propagation

## 🐛 Troubleshooting

### Site Not Loading

**Check:**
- Repository is public (not private)
- GitHub Pages is enabled in settings
- `index.html` exists in root folder
- Wait 5 minutes after first deployment

**404 Error:**
- Ensure `index.html` filename is lowercase
- Check branch is set to `main` in Pages settings
- Clear browser cache (Ctrl+Shift+Delete)

### Images Not Showing

**Fix:**
```html
<!-- Use relative paths, not absolute -->
✅ <img src="assets/profile.jpg">
❌ <img src="/assets/profile.jpg">  <!-- Works locally, not on GH Pages -->
```

**If using project repo (not username.github.io):**
```html
<!-- Add repo name to paths -->
<img src="/portfolio/assets/profile.jpg">
```

Or update your base tag:
```html
<head>
  <base href="/portfolio/">
</head>
```

### CSS/JS Not Loading

**Check paths:**
```html
✅ <link rel="stylesheet" href="styles.css">
✅ <script src="script.js"></script>

❌ <link rel="stylesheet" href="/styles.css">
❌ <script src="/script.js">
```

### Mixed Content Errors (HTTPS)

If using external resources:
```html
❌ <script src="http://example.com/script.js">
✅ <script src="https://example.com/script.js">
```

### Push Rejected

```bash
# If remote has changes you don't have
git pull origin main --rebase
git push
```

## 📊 Analytics Setup (Optional)

### Google Analytics

1. Create account at [analytics.google.com](https://analytics.google.com)
2. Get tracking ID (G-XXXXXXXXXX)
3. Add to `<head>` in `index.html`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

## 🔍 SEO Optimization

### Submit to Google

1. Go to [Google Search Console](https://search.google.com/search-console)
2. Add your website
3. Verify ownership
4. Submit sitemap: `https://yourusername.github.io/sitemap.xml`

### Create `sitemap.xml`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://yourusername.github.io/</loc>
    <lastmod>2025-02-05</lastmod>
    <priority>1.0</priority>
  </url>
</urlset>
```

### Create `robots.txt`:

```txt
User-agent: *
Allow: /
Sitemap: https://yourusername.github.io/sitemap.xml
```

## 🎯 Best Practices

1. **Commit Often**
   - Commit after each significant change
   - Write clear commit messages
   - Use branches for major changes

2. **Backup**
   - GitHub is your backup!
   - Keep local copy on multiple devices
   - Download releases periodically

3. **Test Before Pushing**
   - Test locally first
   - Check all links work
   - Verify on multiple browsers

4. **Keep Updated**
   - Update projects regularly
   - Add new skills
   - Refresh content quarterly

## 🆘 Getting Help

**Resources:**
- [GitHub Pages Docs](https://docs.github.com/pages)
- [Git Tutorial](https://git-scm.com/doc)
- [GitHub Community](https://github.community)

**Common Issues:**
- [GitHub Pages Troubleshooting](https://docs.github.com/pages/getting-started-with-github-pages/troubleshooting-404-errors-for-github-pages-sites)

## 🎓 Git Cheat Sheet

```bash
# Check status
git status

# See changes
git diff

# See commit history
git log --oneline

# Undo last commit (keep changes)
git reset --soft HEAD~1

# Discard all local changes
git reset --hard

# Create new branch
git checkout -b feature-name

# Switch branches
git checkout main

# Merge branch
git merge feature-name

# Delete branch
git branch -d feature-name

# Pull latest changes
git pull origin main

# Clone repository
git clone https://github.com/username/repo.git
```

## ✅ Deployment Checklist

Before going live:

- [ ] All images optimized and added
- [ ] Resume PDF uploaded
- [ ] All links tested (GitHub, LinkedIn, etc.)
- [ ] Contact information correct
- [ ] Mobile responsive checked
- [ ] Dark mode working
- [ ] No console errors (F12)
- [ ] All sections completed
- [ ] README updated
- [ ] .gitignore configured
- [ ] Git initialized and committed
- [ ] Pushed to GitHub
- [ ] GitHub Pages enabled
- [ ] Site loads correctly
- [ ] Shared with network!

---

**Congratulations! Your portfolio is now live! 🎉**

Share it:
- LinkedIn profile
- Resume
- Email signature
- Twitter/X bio
- GitHub profile README
