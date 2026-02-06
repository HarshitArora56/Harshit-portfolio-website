# 🚀 Deployment Checklist for Your Portfolio

**Your GitHub Pages URL:** https://harshitarora56.github.io/Harshit-portfolio-website/

---

## ⚠️ IMPORTANT: Path Configuration

Since your site is at `/Harshit-portfolio-website/` (not the root), you need to update asset paths!

### **Option 1: Add Base Tag (Easiest)**

Add this line in `index.html` inside the `<head>` section, right after `<meta>` tags:

```html
<base href="/Harshit-portfolio-website/">
```

This tells the browser where to find all your files.

### **Option 2: Update All Asset Paths Manually**

If Option 1 doesn't work, update all paths in `index.html`:

**Find and Replace:**
```html
<!-- OLD -->
href="styles.css"
src="script.js"
src="assets/profile.jpg"

<!-- NEW -->
href="/Harshit-portfolio-website/styles.css"
src="/Harshit-portfolio-website/script.js"
src="/Harshit-portfolio-website/assets/profile.jpg"
```

---

## ✅ Pre-Deployment Checklist

### **1. Images (REQUIRED)**

Add these files to `assets/` folder:
- [ ] `profile.jpg` (400x400px)
- [ ] `maritime-port.jpg` (1200x600px)
- [ ] `netflix-analytics.jpg` (1200x600px)
- [ ] `churn-prediction.jpg` (1200x600px)
- [ ] `Harshit_Arora_Resume.pdf`

**Temporary placeholder if you don't have images:**
```html
<img src="https://via.placeholder.com/400x400/667eea/ffffff?text=Harshit+Arora" alt="Profile">
<img src="https://via.placeholder.com/1200x600/667eea/ffffff?text=Project+Screenshot" alt="Project">
```

### **2. Google Analytics**

- [ ] Created Google Analytics account
- [ ] Copied Measurement ID (G-XXXXXXXXXX)
- [ ] Updated `index.html` with your ID (replace both `G-XXXXXXXXXX`)
- [ ] Used correct URL: `https://harshitarora56.github.io/Harshit-portfolio-website/`

### **3. Personal Links**

Verify all these are YOUR links in `index.html`:
- [ ] GitHub: `https://github.com/HarshitArora56`
- [ ] LinkedIn: `https://www.linkedin.com/in/harshitarora56/`
- [ ] Tableau: `https://public.tableau.com/app/profile/harshitarora/vizzes`
- [ ] Email: `589harshitarora.2020@gmail.com`
- [ ] Phone: `+91 9215847003`

### **4. Resume Download**

Update resume path if using base tag:
```html
<!-- If using base tag -->
<a href="assets/Harshit_Arora_Resume.pdf" download>

<!-- If NOT using base tag -->
<a href="/Harshit-portfolio-website/assets/Harshit_Arora_Resume.pdf" download>
```

---

## 📁 Repository Structure

Your GitHub repository should look like:

```
Harshit-portfolio-website/
├── index.html
├── styles.css
├── script.js
├── README.md
├── DEPLOYMENT.md
├── CUSTOMIZATION.md
├── GOOGLE_ANALYTICS_GUIDE.md
├── CHANGES.md
├── QUICK_START.md
├── .gitignore
└── assets/
    ├── profile.jpg
    ├── maritime-port.jpg
    ├── netflix-analytics.jpg
    ├── churn-prediction.jpg
    └── Harshit_Arora_Resume.pdf
```

---

## 🚀 Deployment Commands

### **Initial Setup (First Time)**

```bash
# Navigate to your project folder
cd path/to/Harshit-portfolio-website

# Initialize git (if not already done)
git init

# Add all files
git add .

# Commit
git commit -m "Initial portfolio setup"

# Connect to GitHub
git remote add origin https://github.com/HarshitArora56/Harshit-portfolio-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### **Enable GitHub Pages**

1. Go to: https://github.com/HarshitArora56/Harshit-portfolio-website
2. Click **Settings** tab
3. Left sidebar → **Pages**
4. Source: **Deploy from a branch**
5. Branch: **main** | Folder: **/ (root)**
6. Click **Save**
7. Wait 2-3 minutes
8. Visit: https://harshitarora56.github.io/Harshit-portfolio-website/

### **Update After Changes**

```bash
# Save your changes
git add .

# Commit with a message
git commit -m "Updated [what you changed]"

# Push to GitHub
git push

# Changes will be live in 1-2 minutes!
```

---

## 🧪 Testing Checklist

### **Before Deploying:**

- [ ] Test locally (open `index.html` in browser)
- [ ] Dark mode loads by default
- [ ] Theme toggle works
- [ ] All navigation links work
- [ ] Projects display side-by-side on desktop
- [ ] Projects stack on mobile (resize browser)
- [ ] Contact form looks good
- [ ] No console errors (press F12)

### **After Deploying:**

- [ ] Visit: https://harshitarora56.github.io/Harshit-portfolio-website/
- [ ] All images load correctly
- [ ] CSS styling applied
- [ ] JavaScript working (dark mode toggle, smooth scroll)
- [ ] Resume downloads when clicked
- [ ] All external links open (GitHub, LinkedIn, Tableau)
- [ ] Mobile responsive (test on phone or DevTools)
- [ ] Google Analytics shows you in real-time

---

## 🐛 Common Issues & Fixes

### **Issue: Images Not Loading**

**Problem:** You see broken image icons

**Fix 1 - Add base tag:**
```html
<head>
    <base href="/Harshit-portfolio-website/">
    <!-- rest of head -->
</head>
```

**Fix 2 - Update image paths:**
```html
<!-- Change from: -->
<img src="assets/profile.jpg">

<!-- To: -->
<img src="/Harshit-portfolio-website/assets/profile.jpg">
```

### **Issue: CSS Not Loading**

**Problem:** Site has no styling, looks plain

**Fix - Update CSS path:**
```html
<!-- In index.html head section -->
<link rel="stylesheet" href="/Harshit-portfolio-website/styles.css">
```

Or use base tag (see above).

### **Issue: JavaScript Not Working**

**Problem:** Dark mode toggle doesn't work, no animations

**Fix - Update JS path:**
```html
<!-- Before closing </body> tag -->
<script src="/Harshit-portfolio-website/script.js"></script>
```

### **Issue: 404 Page Not Found**

**Possible causes:**
1. GitHub Pages not enabled → Check Settings → Pages
2. Wrong branch selected → Should be `main`
3. Waited less than 3 minutes → Wait a bit longer
4. Repository is private → Must be public

**Fix:**
- Make repository public
- Enable GitHub Pages in Settings
- Wait 3-5 minutes after enabling

### **Issue: Old Version Showing**

**Fix:**
```bash
# Clear GitHub cache
git commit --allow-empty -m "Trigger rebuild"
git push

# Clear browser cache
# Chrome: Ctrl + Shift + Delete
# Then hard refresh: Ctrl + Shift + R
```

---

## 📊 Google Analytics Setup

**After deploying:**

1. **Visit Google Analytics:** https://analytics.google.com
2. **Create property with this URL:**
   ```
   https://harshitarora56.github.io/Harshit-portfolio-website/
   ```
3. **Copy Measurement ID** (G-XXXXXXXXXX)
4. **Update in `index.html`** (replace both occurrences)
5. **Push changes:**
   ```bash
   git add index.html
   git commit -m "Added Google Analytics"
   git push
   ```
6. **Verify:** Visit site → Check Analytics real-time report

---

## 🎯 Post-Deployment Actions

### **Immediate (Today)**

- [ ] Share on LinkedIn
- [ ] Add to resume
- [ ] Add to GitHub profile README
- [ ] Add to email signature
- [ ] Test on mobile device

### **This Week**

- [ ] Submit to Google Search Console
- [ ] Check analytics daily
- [ ] Get feedback from friends/colleagues
- [ ] Make any needed adjustments

### **Ongoing**

- [ ] Update projects as you build them
- [ ] Add new skills as you learn
- [ ] Keep certifications current
- [ ] Check analytics weekly
- [ ] Refresh content quarterly

---

## 📱 Share Your Portfolio

**Great places to share:**

✅ **LinkedIn Profile:**
- Edit profile → Contact Info → Website
- URL: https://harshitarora56.github.io/Harshit-portfolio-website/
- Label: "Portfolio"

✅ **LinkedIn Post:**
```
🚀 Excited to share my new portfolio showcasing my journey in Data Science!

Featuring:
• ML projects with 80%+ accuracy
• Big Data pipelines on AWS
• Interactive Tableau dashboards
• RAG & LLM applications

Check it out: https://harshitarora56.github.io/Harshit-portfolio-website/

Would love your feedback! 💬

#DataScience #MachineLearning #Portfolio
```

✅ **GitHub Profile README:**
```markdown
🌐 **Portfolio:** https://harshitarora56.github.io/Harshit-portfolio-website/
```

✅ **Resume:**
Add under contact information

✅ **Email Signature:**
```
Harshit Arora
Data Science Professional
📧 589harshitarora.2020@gmail.com
🌐 harshitarora56.github.io/Harshit-portfolio-website
```

---

## 🔗 Important Links

**Your Portfolio:** https://harshitarora56.github.io/Harshit-portfolio-website/  
**GitHub Repo:** https://github.com/HarshitArora56/Harshit-portfolio-website  
**Google Analytics:** https://analytics.google.com

---

## ✅ Final Checklist

**Pre-Launch:**
- [ ] All images added
- [ ] Google Analytics configured
- [ ] Base tag added OR paths updated
- [ ] Tested locally
- [ ] Committed and pushed to GitHub
- [ ] GitHub Pages enabled

**Post-Launch:**
- [ ] Site loads correctly
- [ ] Analytics tracking works
- [ ] Shared on LinkedIn
- [ ] Added to resume
- [ ] Tested on mobile

---

**Your portfolio is ready to impress! 🌟**

Need help? Check the documentation files or open an issue on GitHub!
