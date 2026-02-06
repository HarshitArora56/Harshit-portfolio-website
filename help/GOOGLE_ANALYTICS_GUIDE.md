# 📊 Google Analytics Setup & Tracking Guide

Complete guide to add Google Analytics to your portfolio and track visitors.

## 🎯 What You'll Track

With Google Analytics, you can see:
- 📈 **Visitor count** - How many people visit your site
- 🌍 **Geographic location** - Where visitors are from
- 📱 **Device type** - Desktop, mobile, or tablet
- 🕐 **Visit duration** - How long people stay
- 🔗 **Traffic sources** - LinkedIn, GitHub, direct links, etc.
- 📄 **Page views** - Which sections people view most
- 👥 **Real-time visitors** - Who's on your site right now

---

## 📝 Step-by-Step Setup

### **Step 1: Create Google Analytics Account (5 minutes)**

1. **Visit Google Analytics:**
   ```
   https://analytics.google.com
   ```

2. **Sign in** with your Google account

3. **Click "Start measuring"** (if new account)

4. **Account Setup:**
   - Account name: `Portfolio Analytics`
   - ✅ Check all data sharing settings (recommended)
   - Click **"Next"**

5. **Property Setup:**
   - Property name: `Harshit Arora Portfolio`
   - Reporting time zone: **India Standard Time**
   - Currency: **Indian Rupee (₹)**
   - Click **"Next"**

6. **Business Information:**
   - Industry category: `Technology` or `Computers & Electronics`
   - Business size: `Small - 1 to 10 employees`
   - Click **"Next"**

7. **Business Objectives:**
   - Select: **"Examine user behavior"**
   - Click **"Create"**

8. **Terms of Service:**
   - Select: **India**
   - ✅ Accept both checkboxes
   - Click **"I Accept"**

---

### **Step 2: Set Up Data Stream**

1. **Platform Selection:**
   - Click: **"Web"**

2. **Stream Details:**
   - Website URL: 
     ```
     https://harshitarora56.github.io/Harshit-portfolio-website/
     ```
   
   - Stream name: `Portfolio Website`
   
   - ✅ Enable **"Enhanced measurement"** (recommended)
     - This tracks: scrolls, outbound clicks, site search, video engagement

3. **Click "Create stream"**

4. **Copy Your Measurement ID:**
   ```
   G-XXXXXXXXXX
   ```
   You'll see this at the top. **COPY THIS!**

---

### **Step 3: Add Code to Your Website**

#### **Option A: Use Updated index.html (Easiest)**

1. **Download the updated `index.html`** file (it already has the Analytics code)

2. **Replace `G-XXXXXXXXXX`** with your actual Measurement ID:
   - Open `index.html` in text editor
   - Find `G-XXXXXXXXXX` (appears twice)
   - Replace with your real ID like `G-ABC123DEF4`

3. **Save the file**

#### **Option B: Manual Addition**

Open `index.html` and add this code **right after** the `<title>` tag:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());
    gtag('config', 'G-XXXXXXXXXX');
</script>
<!-- End Google Analytics -->
```

**Replace `G-XXXXXXXXXX`** with your Measurement ID (appears **twice** in the code).

---

### **Step 4: Deploy Your Website**

Upload your updated website:

**If using GitHub Pages:**
```bash
git add index.html
git commit -m "Added Google Analytics tracking"
git push
```

**If using Netlify/Vercel:**
- Simply drag and drop your updated files
- Or push to GitHub (auto-deploys)

---

### **Step 5: Verify It's Working**

1. **Visit your live website:**
   ```
   https://harshitarora56.github.io/Harshit-portfolio-website/
   ```

2. **Open Google Analytics:**
   - Go to: [analytics.google.com](https://analytics.google.com)
   - Click on your property

3. **Check Real-time Report:**
   - Left sidebar → **Reports** → **Realtime**
   - You should see **1 active user** (that's you!)
   - Shows: Location, page, device

4. **Wait 24-48 hours** for full data to appear

---

## 📊 How to Use Google Analytics

### **Dashboard Overview**

After 24-48 hours, you'll see:

**Left Sidebar Menu:**
- 🏠 **Home** - Quick overview
- 📊 **Reports** - Detailed analytics
- 🔍 **Explore** - Custom analysis
- 📢 **Advertising** - Campaign tracking

---

### **Key Reports to Check**

#### **1. Real-time Report**
**Reports → Realtime**

See who's on your site RIGHT NOW:
- Active users
- Page they're viewing
- City/country
- Traffic source

**Use case:** Share your portfolio link on LinkedIn, then watch people visit in real-time!

---

#### **2. User Acquisition**
**Reports → Acquisition → User acquisition**

See where visitors come from:
- 🔗 Direct (typed URL)
- 🔍 Organic Search (Google)
- 🔗 Referral (LinkedIn, GitHub, etc.)
- 📧 Email (sent link via email)

**Use case:** Know if LinkedIn or GitHub profile drives more traffic.

---

#### **3. Traffic Overview**
**Reports → Life cycle → Acquisition → Traffic acquisition**

Detailed breakdown:
- Sessions (visits)
- Users (unique visitors)
- New vs. returning
- Average engagement time

---

#### **4. Pages and Screens**
**Reports → Engagement → Pages and screens**

See which sections are most popular:
- `/` (home page)
- `/#projects` (projects section)
- `/#contact` (contact section)

**Use case:** Know which projects people view most.

---

#### **5. Demographics**
**Reports → User → Demographics**

Learn about your audience:
- **Age groups**
- **Gender**
- **Interests**

**Use case:** Understand who's interested in your work.

---

#### **6. Technology**
**Reports → User → Tech → Tech details**

See what devices visitors use:
- 💻 Desktop: 65%
- 📱 Mobile: 30%
- 📱 Tablet: 5%

**Browsers:** Chrome, Safari, Firefox, etc.

**Use case:** Ensure your site works well on popular devices.

---

#### **7. Geography**
**Reports → User → Demographics details**

World map showing:
- Countries
- Cities
- Language

**Use case:** Know if you're getting international attention.

---

## 🎯 Tracking Custom Events (Advanced)

### **Track Resume Downloads**

Add this to your download button in `index.html`:

Find:
```html
<a href="assets/Harshit_Arora_Resume.pdf" download class="btn btn-primary btn-large">
```

Replace with:
```html
<a href="assets/Harshit_Arora_Resume.pdf" download class="btn btn-primary btn-large" 
   onclick="gtag('event', 'download', {'event_category': 'resume', 'event_label': 'Resume PDF'});">
```

Now you can see how many people download your resume!

---

### **Track Project Link Clicks**

Track GitHub links:

```html
<a href="https://github.com/..." 
   onclick="gtag('event', 'click', {'event_category': 'project', 'event_label': 'MaritimePort AI GitHub'});">
```

Track Live Demo links:

```html
<a href="https://your-demo.com" 
   onclick="gtag('event', 'click', {'event_category': 'demo', 'event_label': 'Churn Predictor Live'});">
```

---

### **Track Contact Form Submissions**

In `script.js`, find the contact form success section and add:

```javascript
// After successful form submission
gtag('event', 'submit', {
    'event_category': 'contact',
    'event_label': 'Contact Form'
});
```

---

## 📈 Analytics Best Practices

### **What to Monitor Weekly**

1. **Total visitors** - Growing trend?
2. **Traffic sources** - Which platforms work best?
3. **Popular pages** - Which projects get attention?
4. **Bounce rate** - Are people staying or leaving quickly?

### **Monthly Review**

- Compare month-over-month growth
- Check which countries show interest
- Identify peak traffic times
- Review most engaged content

### **When Sharing Portfolio**

**Before sharing on LinkedIn:**
1. Open Analytics Real-time view
2. Post your portfolio link
3. Watch visitors arrive in real-time!
4. Track conversion over next 24 hours

---

## 🔒 Privacy Considerations

### **GDPR Compliance (Optional)**

If you get European visitors, consider adding a cookie consent banner:

**Simple Notice:**
Add to your footer in `index.html`:

```html
<div class="analytics-notice" style="position: fixed; bottom: 0; width: 100%; background: #333; color: white; padding: 1rem; text-align: center; font-size: 0.9rem;">
    This site uses Google Analytics to improve user experience. 
    <a href="#" style="color: #00c9ff;">Learn more</a>
</div>
```

**Cookie Consent Plugin:**
- [Cookie Consent by Osano](https://www.osano.com/cookieconsent)
- [GDPR Cookie Consent](https://www.freeprivacypolicy.com/free-cookie-consent.php)

---

## 🎓 Learning Resources

### **Google Analytics Academy (Free)**
```
https://analytics.google.com/analytics/academy/
```
Courses:
- Google Analytics for Beginners
- Advanced Google Analytics
- Google Analytics 4

### **YouTube Tutorials**
- Search: "Google Analytics 4 for beginners"
- Focus on GA4 (not Universal Analytics)

### **Documentation**
```
https://support.google.com/analytics
```

---

## 🐛 Troubleshooting

### **Not Seeing Data?**

**Check 1: Measurement ID**
- Correct format: `G-XXXXXXXXXX`
- Same ID in both places in code
- No extra spaces or typos

**Check 2: Code Placement**
- Must be in `<head>` section
- Before closing `</head>` tag
- No syntax errors in HTML

**Check 3: Browser Extensions**
- Ad blockers may block Analytics
- Test in Incognito mode
- Try different browser

**Check 4: Deployment**
- Changes uploaded to server?
- Clear browser cache
- Hard refresh (Ctrl + Shift + R)

**Check 5: Wait Time**
- Real-time: Works immediately
- Full reports: 24-48 hours

---

### **Real-time Not Working?**

1. **Visit your live site** (not local file)
2. **Check browser console** (F12) for errors
3. **Verify Measurement ID** matches exactly
4. **Disable ad blockers** temporarily
5. **Use Incognito/Private mode**

---

### **Seeing Your Own Visits?**

**Exclude your IP address:**

1. Google Analytics → **Admin** (bottom left)
2. Under **Property** → **Data Streams**
3. Click your stream
4. Click **Configure tag settings**
5. **Define internal traffic** → **Create**
6. Add your IP address
7. **Data Filters** → Create filter to exclude internal traffic

**Find your IP:** Google "what is my ip"

---

## 📊 Sample Analytics Setup

Here's what you'll see after a week:

```
Total Users: 245
New Users: 203
Sessions: 312
Bounce Rate: 42%
Avg. Session Duration: 2m 35s

Top Traffic Sources:
1. LinkedIn: 45%
2. Direct: 30%
3. GitHub: 15%
4. Google Search: 10%

Top Pages:
1. Home: 312 views
2. Projects: 234 views
3. Contact: 156 views

Top Countries:
1. India: 65%
2. United States: 20%
3. United Kingdom: 8%
4. Others: 7%

Devices:
Desktop: 68%
Mobile: 28%
Tablet: 4%
```

---

## ✅ Quick Implementation Checklist

- [ ] Created Google Analytics account
- [ ] Set up property and data stream
- [ ] Copied Measurement ID (G-XXXXXXXXXX)
- [ ] Updated index.html with Analytics code
- [ ] Replaced placeholder ID with real ID
- [ ] Deployed updated website
- [ ] Verified in Real-time report
- [ ] Bookmarked Analytics dashboard
- [ ] Set up weekly review reminder

---

## 🎯 Next Steps After Setup

**Week 1:**
- Check daily to understand baseline traffic
- Test all features work correctly
- Share portfolio and watch real-time

**Week 2:**
- Identify top traffic sources
- See which projects get most views
- Check geographic distribution

**Month 1:**
- Review monthly trends
- Optimize based on user behavior
- Add custom event tracking

**Ongoing:**
- Weekly quick check
- Monthly detailed review
- Use insights for improvements

---

## 💡 Pro Tips

1. **Bookmark your Analytics dashboard** for quick access
2. **Check before important shares** (LinkedIn posts, job applications)
3. **Monitor during job search** to track interest
4. **Use insights to improve** popular sections
5. **Share stats on LinkedIn** (tastefully) - "Portfolio reached X professionals from Y countries"
6. **Set up weekly email reports** in Analytics settings

---

## 🆘 Need Help?

**Google Analytics Help Center:**
```
https://support.google.com/analytics
```

**Analytics Community:**
```
https://support.google.com/analytics/community
```

**YouTube Tutorials:**
- Search: "Google Analytics 4 setup tutorial"
- Focus on GA4 (the new version)

---

**Your Measurement ID:** `G-XXXXXXXXXX`  
*Remember to replace this with your actual ID!*

**Analytics Dashboard:** https://analytics.google.com  
**Your Site:** https://harshitarora56.github.io/Harshit-portfolio-website/

---

**Last Updated:** February 2026  
**Setup For:** Harshit Arora Portfolio
