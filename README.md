# Aswar AlAsimah Website - أسوار العاصمة

## Deployment on Hostinger

### Step 1: Prepare Files
All files in this folder are ready to deploy:
```
aswar-website/
├── index.html          (Main page)
├── css/style.css       (Styles)
├── js/main.js          (Scripts)
├── .htaccess           (Server config)
└── README.md           (This file)
```

### Step 2: Upload to Hostinger
1. Log in to your Hostinger hPanel
2. Go to **Files → File Manager**
3. Navigate to `public_html/` folder
4. **Delete** any existing files in `public_html/`
5. Upload ALL files from this folder:
   - `index.html` → directly into `public_html/`
   - `css/` folder → into `public_html/css/`
   - `js/` folder → into `public_html/js/`
   - `.htaccess` → into `public_html/`

### Step 3: Connect Domain
1. In hPanel, go to **Domains**
2. Point `aswaraleasima.com` to your Hostinger hosting
3. Enable **SSL Certificate** (free with Hostinger)

### Step 4: Contact Form Setup
The contact form currently shows a demo animation. To make it work:

**Option A: Use Formspree (easiest)**
1. Sign up at https://formspree.io
2. Create a form and get your endpoint URL
3. In `index.html`, change the form tag to:
   ```html
   <form class="contact-form" id="contactForm" action="https://formspree.io/f/YOUR_ID" method="POST">
   ```

**Option B: Use EmailJS**
1. Sign up at https://www.emailjs.com
2. Follow their setup guide

### Step 5: Add Product Images
Replace the placeholder icons with real product photos:
1. Add your images to a new `images/` folder
2. Replace `<div class="product-placeholder">` blocks with `<img>` tags

### Notes
- The site is fully responsive (mobile, tablet, desktop)
- All external resources (fonts, icons) load from CDN
- HTTPS is enforced via .htaccess
- WhatsApp button links to +964 771 277 8800
