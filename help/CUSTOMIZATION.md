# 🎨 Customization Guide

Complete guide to customize your portfolio to match your personal brand and style.

## 🌈 Changing Colors

### Method 1: Using CSS Variables (Easiest)

Open `styles.css` and find the `:root` section at the top:

```css
:root {
    /* Change these values */
    --primary-color: #0066ff;      /* Main brand color */
    --secondary-color: #00c9ff;    /* Accent color */
    --accent-color: #ff6b6b;       /* Highlight color */
}
```

**Popular Color Schemes:**

**Tech Blue (Current):**
```css
--primary-color: #0066ff;
--secondary-color: #00c9ff;
```

**Professional Purple:**
```css
--primary-color: #667eea;
--secondary-color: #764ba2;
```

**Modern Green:**
```css
--primary-color: #11998e;
--secondary-color: #38ef7d;
```

**Vibrant Orange:**
```css
--primary-color: #f57c00;
--secondary-color: #ff6f00;
```

**Elegant Dark:**
```css
--primary-color: #2d3436;
--secondary-color: #636e72;
```

### Method 2: Gradients

Change gradient styles:

```css
:root {
    --gradient-primary: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}
```

**Gradient Generator Tools:**
- [cssgradient.io](https://cssgradient.io/)
- [uigradients.com](https://uigradients.com/)

## 📝 Content Updates

### Hero Section

**Update your tagline:**

Find in `index.html`:
```html
<p class="hero-description">
    Building intelligent solutions with 
    <span class="highlight">Machine Learning</span>, 
    <span class="highlight">Python</span>, and 
    <span class="highlight">Big Data Analytics</span>
</p>
```

Change to:
```html
<p class="hero-description">
    Creating data-driven solutions with 
    <span class="highlight">AI</span>, 
    <span class="highlight">Deep Learning</span>, and 
    <span class="highlight">Cloud Technologies</span>
</p>
```

### About Section

**Update your bio:**

```html
<p class="about-intro">
    Your new professional summary here...
</p>
```

### Adding New Skills

Find the skills section and copy this template:

```html
<div class="skill-card" data-category="CATEGORY">
    <div class="skill-icon">
        <i class="fab fa-ICON"></i>
    </div>
    <h3>Skill Name</h3>
    <p>Short description</p>
    <div class="skill-level">
        <div class="skill-bar" style="width: 85%"></div>
    </div>
</div>
```

**Categories:**
- `programming`
- `ml`
- `data`
- `cloud`

**Find icons at:** [fontawesome.com/icons](https://fontawesome.com/icons)

### Adding New Projects

Copy this template:

```html
<div class="project-card">
    <div class="project-image">
        <img src="assets/your-project.jpg" alt="Project Name">
        <div class="project-overlay">
            <div class="project-links">
                <a href="GITHUB_URL" target="_blank" class="project-link">
                    <i class="fab fa-github"></i>
                </a>
                <a href="LIVE_URL" target="_blank" class="project-link">
                    <i class="fas fa-external-link-alt"></i>
                </a>
            </div>
        </div>
    </div>
    <div class="project-content">
        <h3>Project Name</h3>
        <p>Project description goes here...</p>
        
        <div class="project-tech">
            <span>Python</span>
            <span>TensorFlow</span>
            <span>Docker</span>
        </div>
        
        <div class="project-stats">
            <div class="stat">
                <i class="fas fa-star"></i>
                <span>Key Achievement</span>
            </div>
        </div>
        
        <div class="project-buttons">
            <a href="GITHUB_URL" target="_blank" class="btn btn-small btn-secondary">
                <i class="fab fa-github"></i> GitHub
            </a>
            <a href="LIVE_URL" target="_blank" class="btn btn-small">
                <i class="fas fa-rocket"></i> Live Demo
            </a>
        </div>
    </div>
</div>
```

### Updating Social Links

Find all occurrences and update:

```html
<!-- GitHub -->
<a href="https://github.com/YOUR_USERNAME" target="_blank">

<!-- LinkedIn -->
<a href="https://www.linkedin.com/in/YOUR_PROFILE" target="_blank">

<!-- Email -->
<a href="mailto:your.email@example.com">
```

## 🖼️ Layout Modifications

### Changing Section Order

Sections are in this order:
1. Hero
2. About
3. Skills
4. Projects
5. Education
6. Resume
7. Contact

To reorder, simply cut and paste entire `<section>` blocks.

### Removing a Section

Don't want the Education section? Simply delete:
```html
<section id="education" class="education">
    <!-- entire section content -->
</section>
```

And remove from navigation:
```html
<li><a href="#education" class="nav-link">Education</a></li>
```

### Adding a New Section

Template for new section:

```html
<section id="new-section" class="new-section">
    <div class="container">
        <div class="section-header">
            <h2 class="section-title">Section Title</h2>
            <p class="section-subtitle">Section subtitle</p>
        </div>
        
        <!-- Your content here -->
        
    </div>
</section>
```

Add to navigation:
```html
<li><a href="#new-section" class="nav-link">New Section</a></li>
```

Add CSS styling:
```css
.new-section {
    padding: var(--spacing-xl) 0;
    background: var(--bg-secondary);
}
```

## 🎭 Animation Customization

### Speed

Change animation speed in `styles.css`:

```css
:root {
    --transition-fast: 0.2s ease;   /* Faster animations */
    --transition-base: 0.3s ease;   /* Normal speed */
    --transition-slow: 0.5s ease;   /* Slower animations */
}
```

### Disable Animations

Add to CSS:
```css
* {
    animation: none !important;
    transition: none !important;
}
```

### Custom Animation

Create new animation:
```css
@keyframes slideInLeft {
    from {
        opacity: 0;
        transform: translateX(-50px);
    }
    to {
        opacity: 1;
        transform: translateX(0);
    }
}

.my-element {
    animation: slideInLeft 0.6s ease;
}
```

## 📱 Responsive Breakpoints

Modify breakpoints in `styles.css`:

```css
/* Tablet */
@media (max-width: 1024px) {
    /* Styles for tablets */
}

/* Mobile */
@media (max-width: 768px) {
    /* Styles for mobile */
}

/* Small mobile */
@media (max-width: 480px) {
    /* Styles for small screens */
}
```

## 🔤 Typography

### Changing Fonts

**Option 1: Google Fonts**

1. Go to [fonts.google.com](https://fonts.google.com)
2. Select a font (e.g., "Inter", "Roboto", "Montserrat")
3. Copy the embed code
4. Replace in `index.html` `<head>`:

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

5. Update in `styles.css`:
```css
body {
    font-family: 'Inter', sans-serif;
}
```

**Option 2: System Fonts (Faster)**

```css
body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
}
```

### Font Sizes

Modify in `:root`:
```css
:root {
    --font-xs: 0.75rem;
    --font-sm: 0.875rem;
    --font-base: 1rem;
    --font-lg: 1.125rem;
    --font-xl: 1.5rem;
    --font-2xl: 2rem;
    --font-3xl: 3rem;
    --font-4xl: 4rem;
}
```

## 🎯 Advanced Customizations

### Add Particles Background

Add to hero section:
```html
<!-- Add before closing </body> -->
<script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
<div id="particles-js"></div>
```

CSS:
```css
#particles-js {
    position: absolute;
    width: 100%;
    height: 100%;
    z-index: 0;
}
```

JavaScript:
```javascript
particlesJS('particles-js', {
    particles: {
        number: { value: 80 },
        color: { value: '#667eea' },
        opacity: { value: 0.5 }
    }
});
```

### Add Smooth Scroll Indicator

```html
<div class="scroll-progress"></div>
```

CSS:
```css
.scroll-progress {
    position: fixed;
    top: 0;
    left: 0;
    width: 0%;
    height: 4px;
    background: var(--gradient-primary);
    z-index: 9999;
    transition: width 0.3s;
}
```

JavaScript:
```javascript
window.addEventListener('scroll', () => {
    const scrollProgress = document.querySelector('.scroll-progress');
    const scrolled = (window.scrollY / (document.documentElement.scrollHeight - window.innerHeight)) * 100;
    scrollProgress.style.width = scrolled + '%';
});
```

### Add Typing Effect to Hero

Already included in `script.js`, just uncomment:
```javascript
window.addEventListener('load', function() {
    const heroTitle = document.querySelector('.hero-title');
    const titleText = heroTitle.textContent;
    typeWriter(heroTitle, titleText, 80);
});
```

### Add Reading Progress Bar

For blog posts or long content:
```html
<div class="reading-progress"></div>
```

```css
.reading-progress {
    position: fixed;
    top: 0;
    left: 0;
    height: 3px;
    background: var(--gradient-primary);
    z-index: 9999;
}
```

```javascript
window.addEventListener('scroll', () => {
    const article = document.querySelector('.article-content');
    const progress = (window.scrollY / article.offsetHeight) * 100;
    document.querySelector('.reading-progress').style.width = progress + '%';
});
```

## 🔧 JavaScript Customization

### Disable Features

In `script.js`, comment out sections you don't want:

```javascript
// Disable dark mode
// themeToggle.addEventListener('click', function() { ... });

// Disable smooth scroll
// navLinks.forEach(link => { ... });

// Disable animations
// window.addEventListener('scroll', reveal);
```

### Add Google Analytics

Add before `</head>`:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

### Add Chatbot

Example with Tidio:
```html
<script src="//code.tidio.co/YOUR_TIDIO_CODE.js" async></script>
```

## 🎨 Quick Style Changes

### Rounded vs Sharp Corners

```css
:root {
    /* Rounded (current) */
    --radius-sm: 8px;
    --radius-md: 12px;
    --radius-lg: 16px;
    
    /* Very rounded */
    --radius-sm: 16px;
    --radius-md: 24px;
    --radius-lg: 32px;
    
    /* Sharp corners */
    --radius-sm: 0px;
    --radius-md: 0px;
    --radius-lg: 0px;
}
```

### Shadow Intensity

```css
:root {
    /* Subtle (current) */
    --shadow-md: 0 4px 16px rgba(0, 0, 0, 0.08);
    
    /* Bold */
    --shadow-md: 0 8px 24px rgba(0, 0, 0, 0.15);
    
    /* Minimal */
    --shadow-md: 0 2px 8px rgba(0, 0, 0, 0.05);
}
```

### Button Styles

```css
/* Solid (current) */
.btn-primary {
    background: var(--gradient-primary);
}

/* Outline */
.btn-primary {
    background: transparent;
    border: 2px solid var(--primary-color);
    color: var(--primary-color);
}

/* Glass morphism */
.btn-primary {
    background: rgba(102, 126, 234, 0.1);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(102, 126, 234, 0.2);
}
```

## 📋 Testing Checklist

After customization:

- [ ] Test on Chrome
- [ ] Test on Firefox
- [ ] Test on Safari
- [ ] Test on mobile (DevTools)
- [ ] Check dark mode
- [ ] Check all links
- [ ] Verify animations
- [ ] Check console for errors (F12)
- [ ] Test contact form
- [ ] Validate HTML
- [ ] Check page speed
- [ ] Test accessibility

## 🆘 Common Issues

**Colors not changing:**
- Clear browser cache (Ctrl+Shift+Del)
- Hard refresh (Ctrl+Shift+R)
- Check CSS syntax

**Layout broken:**
- Validate HTML at validator.w3.org
- Check browser console for errors
- Ensure closing tags match

**Fonts not loading:**
- Check Google Fonts link in `<head>`
- Verify font name matches exactly
- Check network tab in DevTools

## 📚 Resources

**Design Inspiration:**
- [Dribbble](https://dribbble.com/tags/portfolio)
- [Behance](https://behance.net)
- [Awwwards](https://awwwards.com)

**Color Tools:**
- [Coolors](https://coolors.co) - Color palette generator
- [Adobe Color](https://color.adobe.com)
- [Paletton](https://paletton.com)

**Icons:**
- [Font Awesome](https://fontawesome.com/icons)
- [Heroicons](https://heroicons.com)
- [Feather Icons](https://feathericons.com)

**Fonts:**
- [Google Fonts](https://fonts.google.com)
- [Font Pair](https://fontpair.co)

**CSS Generators:**
- [CSS Gradient](https://cssgradient.io)
- [Get Waves](https://getwaves.io)
- [Fancy Border Radius](https://9elements.github.io/fancy-border-radius/)

---

**Happy Customizing! 🎨**

Need help? Open an issue on GitHub or contact me!
