# 📐 Technical Specifications

## Project Overview
**D.quant Societe — Premium Single-Page Application**

**Type**: Static SPA (Single-Page Application)  
**Architecture**: Client-side rendered, no backend dependencies  
**Deployment**: CDN-ready, instant deployment

---

## 📦 File Structure

```
dquant-societe/
├── index.html           # Complete standalone SPA (46KB)
├── README.md            # Comprehensive documentation
├── DEPLOYMENT.md        # Deployment guide
└── TECHNICAL.md         # This file
```

**Total Package Size**: ~62KB (uncompressed)

---

## 🛠️ Technology Stack

### Core Technologies
| Technology | Version | Purpose | Load Source |
|------------|---------|---------|-------------|
| HTML5 | - | Semantic markup | Native |
| CSS3 | - | Styling foundation | Native |
| JavaScript (ES6+) | - | Interactivity | Native |
| Tailwind CSS | 3.4+ | Utility-first framework | CDN |
| GSAP | 3.12.5 | Animation library | CDN |
| ScrollTrigger | 3.12.5 | Scroll animations | CDN |
| Font Awesome | 6.5.1 | Icons | CDN |
| Google Fonts | - | Typography | CDN |

### External Dependencies (CDN)
```html
<!-- Fonts -->
https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700;800&family=Inter:wght@300;400;500;600;700

<!-- Tailwind CSS -->
https://cdn.tailwindcss.com

<!-- GSAP Core -->
https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js

<!-- GSAP ScrollTrigger -->
https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js

<!-- Font Awesome -->
https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css

<!-- Images (Unsplash placeholders) -->
https://images.unsplash.com/[photo-id]?w=[width]&q=80
```

---

## 🎨 Design System

### Color Palette
```css
/* Primary Colors */
--institutional-blue: #002045    /* Authority, trust */
--institutional-slate: #4A5568   /* Professional grey */
--institutional-gold: #C5A572    /* Premium accent */
--institutional-light: #E2E8F0   /* Subtle backgrounds */

/* Supporting Colors */
--white: #FFFFFF
--black: #000000
--gray-50: #F9FAFB
--gray-100: #F3F4F6
--gray-800: #1F2937
```

### Typography Scale
```css
/* Headings (Playfair Display - Serif) */
h1: 3.5rem - 4.5rem (56px - 72px)
h2: 2.5rem - 3rem (40px - 48px)
h3: 1.5rem - 2rem (24px - 32px)
h4: 1.25rem - 1.5rem (20px - 24px)

/* Body Text (Inter - Sans-serif) */
Large: 1.125rem (18px)
Base: 1rem (16px)
Small: 0.875rem (14px)
Tiny: 0.75rem (12px)

/* Font Weights */
Light: 300
Regular: 400
Medium: 500
Semibold: 600
Bold: 700
Extrabold: 800
```

### Spacing Scale (Tailwind)
```
0.25rem (4px)   → space-1
0.5rem (8px)    → space-2
0.75rem (12px)  → space-3
1rem (16px)     → space-4
1.5rem (24px)   → space-6
2rem (32px)     → space-8
3rem (48px)     → space-12
4rem (64px)     → space-16
6rem (96px)     → space-24
```

---

## 📱 Responsive Breakpoints

```css
/* Mobile First Approach */
Base (Mobile):     0px - 767px    (default styles)
Tablet (md):       768px - 1023px (md: prefix)
Desktop (lg):      1024px - 1279px (lg: prefix)
Large Desktop:     1280px+        (xl: prefix)

/* Key Breakpoint Values */
sm: 640px
md: 768px
lg: 1024px
xl: 1280px
2xl: 1536px
```

### Layout Adjustments
| Element | Mobile | Tablet | Desktop |
|---------|--------|--------|---------|
| Navigation | Hamburger | Full nav | Full nav |
| Hero Height | 70vh | 85vh | 100vh |
| Grid Columns | 1 | 2 | 3-4 |
| Font Scale | 90% | 95% | 100% |
| Padding | 4-6 | 6-8 | 8-12 |

---

## 🎬 Animation Specifications

### Slide Transitions
```javascript
// Hero Slider
Duration: 1200ms
Easing: ease-in-out
Interval: 5000ms (auto-advance)
Effect: Opacity fade (0 → 1)
```

### Scroll Reveal
```javascript
// Intersection Observer
Threshold: 0.1
Root Margin: 0px 0px -100px 0px
Transition: 800ms cubic-bezier(0.16, 1, 0.3, 1)
Transform: translateY(50px) → translateY(0)
Opacity: 0 → 1
```

### Counter Animation
```javascript
Duration: 2000ms
Update Rate: 16ms (60fps)
Easing: Linear with requestAnimationFrame
Trigger: IntersectionObserver at 50% threshold
```

### GSAP Effects
```javascript
// Parallax (Hero)
scrollTrigger: { scrub: true }
opacity: 1 → 0.7
scale: 1 → 1.1

// Stagger (Cards)
stagger: 0.2s
duration: 0.8s
ease: 'power3.out'

// SVG Animation
AI Core: scale(0) → scale(1), 1s, back.out(1.7)
HI Nodes: scale(0) → scale(1), 0.8s, stagger: 0.15s
Lines: strokeDashoffset: 100 → 0, 1s, delay: 1s
```

---

## 🔧 JavaScript Features

### Core Functions
```javascript
1. Navigation
   - Sticky header on scroll (threshold: 100px)
   - Smooth scroll to sections
   - Active link highlighting

2. Hero Slider
   - Auto-advance (5s interval)
   - Manual navigation (dots)
   - Smooth fade transitions
   - Active dot tracking

3. Reveal Animations
   - IntersectionObserver API
   - Element visibility tracking
   - Class-based animation triggers

4. Counter Animation
   - Triggered on scroll into view
   - Smooth number increment
   - Configurable target values

5. Language Switcher
   - Active state management
   - UI updates (prepared for i18n)

6. Form Handling
   - Basic validation
   - Submission prevention (demo)
   - Alert feedback
```

### Performance Optimizations
- **Debounced scroll listeners**: Reduce CPU load
- **RequestAnimationFrame**: Smooth 60fps animations
- **Passive event listeners**: Improved scroll performance
- **Lazy intersection observers**: Only observe visible elements
- **CSS transforms**: GPU-accelerated animations

---

## 🎯 Component Inventory

### UI Components
1. **Navigation Bar** (Sticky)
   - Logo + Brand
   - 5 Navigation Links
   - Language Switcher (EN/KR)
   - Mobile Menu Toggle

2. **Hero Slider** (3 slides)
   - Full viewport height
   - Background images
   - Dark overlay gradients
   - Call-to-action buttons
   - Navigation dots

3. **Section Headers** (Reusable)
   - Label (uppercase, gold)
   - Title (large serif)
   - Description (grey text)

4. **Feature Cards** (Various types)
   - Icon + Title + Text
   - Hover effects (elevation, shadow)
   - Responsive grid layouts

5. **Leadership Cards**
   - Avatar circle (icon/image)
   - Name + Title + English name
   - Role description

6. **Committee Cards**
   - Icon badge
   - Title + Description
   - Bullet point list
   - Border accent (left edge)

7. **Statistics Counters**
   - Large number display
   - Label text
   - Animated count-up

8. **SVG Infographic**
   - Central AI core
   - 4 HI nodes
   - Connecting lines
   - Text labels
   - Animated drawing

9. **Contact Form**
   - Name, Email, Organization
   - Message textarea
   - Submit button
   - Validation feedback

10. **Footer**
    - 4-column grid
    - Quick links
    - Social media icons
    - Copyright notice

---

## 🌐 Browser API Usage

### Modern Web APIs
```javascript
1. IntersectionObserver
   - Scroll-triggered animations
   - Lazy loading preparation
   - Counter triggers

2. requestAnimationFrame
   - Smooth counter animations
   - Performance optimization

3. classList API
   - Dynamic class management
   - Animation state control

4. querySelector/querySelectorAll
   - DOM element selection
   - Event listener attachment

5. addEventListener
   - User interactions
   - Scroll events
   - Form submissions

6. setTimeout/setInterval
   - Slider auto-advance
   - Timed transitions

7. scrollTo (smooth)
   - Navigation scrolling
   - Section jumping
```

---

## 🔍 SEO Optimization

### Meta Tags (Recommended additions)
```html
<!-- Primary Meta Tags -->
<title>D.quant Societe — Investment Excellence & Social Impact</title>
<meta name="title" content="D.quant Societe — Investment Excellence & Social Impact">
<meta name="description" content="A professional investment association dedicated to investor protection, AI-driven strategies, and social empowerment through digital literacy programs.">
<meta name="keywords" content="investment, digital assets, AI trading, financial literacy, social impact">

<!-- Open Graph / Facebook -->
<meta property="og:type" content="website">
<meta property="og:url" content="https://www.dquantsociete.com/">
<meta property="og:title" content="D.quant Societe — Investment Excellence">
<meta property="og:description" content="Professional investment association for digital asset investors">
<meta property="og:image" content="https://www.dquantsociete.com/og-image.jpg">

<!-- Twitter -->
<meta property="twitter:card" content="summary_large_image">
<meta property="twitter:url" content="https://www.dquantsociete.com/">
<meta property="twitter:title" content="D.quant Societe — Investment Excellence">
<meta property="twitter:description" content="Professional investment association">
<meta property="twitter:image" content="https://www.dquantsociete.com/twitter-image.jpg">

<!-- Canonical -->
<link rel="canonical" href="https://www.dquantsociete.com/">

<!-- Robots -->
<meta name="robots" content="index, follow">
```

### Semantic HTML
✅ Proper heading hierarchy (h1 → h2 → h3)  
✅ Landmark elements (`<nav>`, `<main>`, `<section>`, `<footer>`)  
✅ Descriptive alt text (prepare for production images)  
✅ ARIA labels for interactive elements

---

## ⚡ Performance Metrics

### Target Performance
```
First Contentful Paint (FCP): < 1.5s
Largest Contentful Paint (LCP): < 2.5s
Time to Interactive (TTI): < 3.5s
Cumulative Layout Shift (CLS): < 0.1
First Input Delay (FID): < 100ms
```

### Actual Performance (Expected)
```
Page Weight: ~500KB (with images)
HTML Size: 46KB
JS Size: ~150KB (CDN libraries)
CSS Size: ~50KB (Tailwind)
Images: ~250KB (3 hero images, compressed)

Load Time: 1-2 seconds (fast connection)
Render Time: < 1 second
```

### Optimization Checklist
- [x] Minimize HTTP requests (single HTML file)
- [x] Use CDN for libraries (global caching)
- [x] Compress images (WebP, 80% quality)
- [x] Lazy load images (native loading="lazy")
- [x] Defer non-critical JavaScript
- [x] Use CSS transforms for animations (GPU)
- [ ] Enable gzip/brotli compression (server)
- [ ] Implement service worker (PWA)
- [ ] Add resource hints (preconnect, prefetch)

---

## 🔐 Security Headers (Server Configuration)

```nginx
# Nginx example
add_header X-Frame-Options "DENY" always;
add_header X-Content-Type-Options "nosniff" always;
add_header X-XSS-Protection "1; mode=block" always;
add_header Referrer-Policy "no-referrer-when-downgrade" always;
add_header Content-Security-Policy "default-src 'self'; script-src 'self' 'unsafe-inline' https://cdn.tailwindcss.com https://cdnjs.cloudflare.com; style-src 'self' 'unsafe-inline' https://fonts.googleapis.com https://cdnjs.cloudflare.com; font-src 'self' https://fonts.gstatic.com; img-src 'self' https://images.unsplash.com data:; connect-src 'self';" always;

# Enable HTTPS redirect
if ($scheme != "https") {
    return 301 https://$host$request_uri;
}
```

---

## 🧪 Testing Checklist

### Functional Testing
- [ ] All navigation links work
- [ ] Slider auto-advances every 5 seconds
- [ ] Slider dots manually navigate
- [ ] Smooth scroll to sections
- [ ] Language switcher changes active state
- [ ] Counters animate on scroll into view
- [ ] Form submission shows alert
- [ ] All hover effects work
- [ ] SVG infographic animates on scroll
- [ ] Mobile menu toggle works

### Cross-Browser Testing
- [ ] Chrome (latest)
- [ ] Firefox (latest)
- [ ] Safari (latest)
- [ ] Edge (latest)
- [ ] Mobile Safari (iOS 14+)
- [ ] Chrome Mobile (Android 10+)

### Responsive Testing
- [ ] iPhone SE (375px)
- [ ] iPhone 12 Pro (390px)
- [ ] iPad (768px)
- [ ] iPad Pro (1024px)
- [ ] Desktop 1080p (1920px)
- [ ] Desktop 4K (3840px)

### Accessibility Testing
- [ ] Keyboard navigation (Tab, Enter, Arrow keys)
- [ ] Screen reader compatibility (NVDA, JAWS)
- [ ] Color contrast ratios (WCAG AA)
- [ ] Focus indicators visible
- [ ] ARIA labels present
- [ ] Alt text for images

### Performance Testing
- [ ] Google PageSpeed Insights (90+ score)
- [ ] GTmetrix (Grade A)
- [ ] WebPageTest (< 3s load time)
- [ ] Lighthouse audit (all categories 90+)

---

## 📊 Analytics Setup (Recommended)

### Google Analytics 4
```html
<!-- Add before </head> -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Events to Track
- Page views
- Navigation clicks
- Slider interactions
- CTA button clicks
- Form submissions
- Scroll depth
- Time on page
- Exit rate

---

## 🔄 Version Control

**Current Version**: 1.0.0  
**Release Date**: 2024-03-15  
**Status**: Production Ready

### Version History
```
1.0.0 - 2024-03-15
- Initial production release
- Full SPA implementation
- Hero slider with 3 slides
- All sections complete
- GSAP animations
- Responsive design
- Documentation complete
```

### Future Versions (Planned)
```
1.1.0 - Q2 2024
- Multi-language support (full i18n)
- Blog/News section
- Member testimonials

1.2.0 - Q3 2024
- Video integration
- Live chat widget
- Newsletter signup

2.0.0 - Q4 2024
- Member portal
- Dashboard integration
- Backend API connection
```

---

## 📞 Technical Support

**Developer Contact**: development@dquantsociete.com  
**Documentation**: See README.md  
**Deployment**: See DEPLOYMENT.md  
**Technical Specs**: This file

---

**Last Updated**: 2024-03-15  
**Maintained By**: D.quant Societe Development Team  
**License**: Proprietary — All Rights Reserved
