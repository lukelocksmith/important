# WordPress & Bricks Builder - important.is

Nasza specjalizacja i standardy pracy z WordPress i Bricks Builder.

---

## 🎯 Why WordPress + Bricks?

### WordPress
- ✅ Most popular CMS (40%+ web)
- ✅ Klienci znają i trust
- ✅ Łatwy w zarządzaniu
- ✅ Ogromny ekosystem
- ✅ SEO-friendly
- ✅ Scalable
- ✅ Open source

### Bricks Builder
- ✅ Clean code (no bloat)
- ✅ Performance-first
- ✅ Designer-friendly
- ✅ Developer-friendly (custom elements, filters)
- ✅ No jQuery dependency
- ✅ Full control
- ✅ One-time purchase
- ✅ Growing ecosystem

### Together
- 🚀 Speed of development
- 💎 Quality of output
- 🎯 Client can manage content
- 🔧 Developers can extend
- 💰 Cost-effective for clients

---

## 🏗️ Standard Stack

### Core
- **WordPress** (latest version, always updated)
- **Bricks Builder** (current version)
- **PHP** 8.0+
- **MySQL** 5.7+ or 8.0+

### Essential Plugins
- **Bricks Builder** (page builder)
- **Advanced Custom Fields (ACF) PRO** (custom fields)
- **WP Rocket** or similar (caching & performance)
- **Wordfence** or **Sucuri** (security)
- **UpdraftPlus** (backups)
- **Yoast SEO** or **Rank Math** (SEO)
- **WP Mail SMTP** (email delivery)

### Optional (Based on Need)
- **WooCommerce** (e-commerce)
- **Gravity Forms** or **WPForms** (advanced forms)
- **WPML** or **Polylang** (multilingual)
- **Custom plugins** (project-specific)

---

## 📋 WordPress Best Practices

### Setup & Configuration

**Core Settings:**
- Latest WordPress version
- HTTPS enforced (SSL)
- Correct permalink structure (/blog/%postname%/)
- Timezone set correctly
- Discourage search engines (staging only!)
- Automatic updates for minor versions

**Performance:**
- Object caching (Redis/Memcached)
- Opcode caching (OPcache)
- GZIP compression
- Image optimization (WebP)
- Lazy loading
- CDN (Cloudflare)

**Security:**
- Strong passwords everywhere
- 2FA for admins
- Limit login attempts
- Regular backups
- Security headers
- File permissions correct
- Hide wp-admin from bots
- Regular updates (core, plugins, themes)

---

### Plugin Philosophy

**Rules:**
- ✅ Use as few plugins as possible
- ✅ Only trusted, maintained plugins
- ✅ Check reviews & last update
- ✅ Prefer lightweight solutions
- ✅ Custom code > plugin when makes sense
- ❌ Never use nulled/pirated plugins
- ❌ Avoid bloated "all-in-one" plugins

**Before Installing:**
- Do we really need it?
- Is there lighter alternative?
- Can we code it ourselves?
- Is plugin actively maintained?
- What's performance impact?

---

### Theme Approach

**Our Standard:**
- Blank/minimal theme (e.g., GeneratePress, Kadence, or custom minimal)
- Bricks Builder handles all design
- Theme provides only basic structure

**Child Theme:**
- Always use child theme for customizations
- Parent theme stays updatable
- Custom functions in child theme

---

## 🧱 Bricks Builder Best Practices

### Structure & Organization

**Global Elements:**
- Header (reusable)
- Footer (reusable)
- Repeating sections (reusable)

**Classes & Naming:**
```
.section
.section__container
.section__heading
.section__content

.card
.card__image
.card__title
.card__description
.card__button

.btn
.btn--primary
.btn--secondary
.btn--large
```

**Use BEM methodology where applicable:**
- Block__Element--Modifier
- Consistent naming convention
- Easy to understand structure

---

### Performance

**Do:**
- ✅ Minimize CSS/JS
- ✅ Defer non-critical JS
- ✅ Use lazy loading
- ✅ Optimize images before upload
- ✅ Use system fonts or limited web fonts
- ✅ Clean up unused CSS classes
- ✅ Limit use of heavy elements (sliders, animations)

**Don't:**
- ❌ Excessive animations
- ❌ Too many custom fonts
- ❌ Huge unoptimized images
- ❌ Render-blocking scripts
- ❌ Excessive nesting (CSS specificity issues)

---

### Responsive Design

**Breakpoints:**
- Desktop: 1200px+
- Laptop: 992px - 1199px
- Tablet: 768px - 991px
- Mobile: < 768px

**Mobile-First Approach:**
- Design mobile first
- Enhance for larger screens
- Test on real devices

**Responsive Checklist:**
- [ ] All text readable
- [ ] Images scale properly
- [ ] Navigation works (mobile menu)
- [ ] Forms usable
- [ ] Buttons tappable (min 44x44px)
- [ ] Spacing appropriate
- [ ] No horizontal scroll

---

### Custom Elements

**When to Create:**
- Repeating complex components
- Need specific functionality
- Better DX for clients
- Performance optimization

**Structure:**
```php
<?php
namespace Bricks;

class Important_Custom_Element extends Element {
  public $category = 'important';
  public $name = 'important-custom-element';
  public $icon = 'fas fa-star';

  public function get_label() {
    return esc_html__( 'Custom Element', 'bricks' );
  }

  public function set_controls() {
    // Control definitions
  }

  public function render() {
    // Render logic
  }
}
```

**Best Practices:**
- Clean, documented code
- Proper escaping & sanitization
- Efficient queries
- Accessibility considered
- Responsive by default

---

## 🎨 Design to Bricks Workflow

### Process

**1. Design (Figma)**
- Complete design system
- All breakpoints designed
- Interaction states
- Style guide

**2. Setup Bricks**
- Import fonts
- Setup color variables
- Define reusable classes
- Create global elements

**3. Build Pages**
- Build mobile first
- Match design exactly
- Use classes consistently
- Test responsive

**4. Refinement**
- Cross-browser testing
- Performance optimization
- Accessibility check
- Client review

---

### Design System in Bricks

**Theme Styles:**
- Colors (CSS variables)
- Typography scales
- Spacing system
- Button styles
- Form styles

**Example CSS Variables:**
```css
:root {
  /* Colors */
  --color-primary: #FF6B6B;
  --color-secondary: #4ECDC4;
  --color-dark: #2C3E50;
  --color-light: #ECF0F1;

  /* Typography */
  --font-heading: 'Inter', sans-serif;
  --font-body: 'Inter', sans-serif;

  /* Spacing */
  --spacing-xs: 0.5rem;
  --spacing-sm: 1rem;
  --spacing-md: 2rem;
  --spacing-lg: 4rem;
  --spacing-xl: 6rem;
}
```

---

## 🔧 Development Workflow

### Local Development

**Tools:**
- Local (by Flywheel)
- MAMP/XAMPP
- Docker (Laravel Sail, etc.)
- Valet (Mac)

**Setup:**
1. Install WordPress
2. Install Bricks
3. Essential plugins
4. Import staging if available
5. Version control (Git)

---

### Version Control

**Git Strategy:**
- Keep WordPress core out of repo (use .gitignore)
- Include: theme, plugins, uploads
- Or: only custom theme/plugins

**.gitignore Example:**
```
# WordPress Core
/wp-admin/
/wp-includes/
/wp-content/index.php
/wp-content/plugins/index.php
/wp-content/themes/index.php

# Configuration
wp-config.php
.htaccess

# Uploads (or track, depending)
/wp-content/uploads/

# Caches and logs
*.log
/wp-content/cache/

# OS Files
.DS_Store
Thumbs.db
```

---

### Deployment

**Staging → Production:**

**Process:**
1. Test thoroughly on staging
2. Backup production
3. Deploy files (FTP, Git, hosting panel)
4. Database sync (if needed - careful!)
5. Search/replace URLs if different
6. Test production
7. Clear all caches

**Tools:**
- WP Migrate DB Pro (database)
- Git-based deployment (SpinupWP, DeployHQ)
- Hosting providers' tools
- Manual (FTP) as last resort

---

## ⚡ Performance Optimization

### Targets
- **Page Speed Insights:** 90+ (both mobile & desktop)
- **Largest Contentful Paint (LCP):** < 2.5s
- **First Input Delay (FID):** < 100ms
- **Cumulative Layout Shift (CLS):** < 0.1
- **Time to First Byte (TTFB):** < 600ms

### Tactics

**Images:**
- WebP format
- Correct dimensions (no massive images scaled with CSS)
- Lazy loading
- CDN delivery

**CSS:**
- Minimize & combine
- Remove unused CSS
- Critical CSS inline
- Defer non-critical

**JavaScript:**
- Minimize & combine
- Defer or async loading
- Remove jQuery if possible (Bricks doesn't need it!)
- Limit third-party scripts

**Hosting:**
- Quality hosting (SSD, LiteSpeed/Nginx)
- PHP 8.0+
- Object caching
- Server-level caching

**Caching:**
- Page caching (WP Rocket, etc.)
- Browser caching
- Object caching (Redis)
- CDN (Cloudflare)

---

## 🔒 Security Best Practices

**Essentials:**
- [ ] Strong, unique passwords
- [ ] 2FA on admin accounts
- [ ] Limit login attempts
- [ ] Security plugin (Wordfence/Sucuri)
- [ ] Regular updates
- [ ] SSL certificate
- [ ] Security headers
- [ ] Database prefix not default (wp_)
- [ ] File permissions correct (755 dirs, 644 files)
- [ ] Disable file editing in wp-config
- [ ] Hide WordPress version
- [ ] XML-RPC disabled if not needed
- [ ] Regular backups

**wp-config.php Hardening:**
```php
// Disable file editing
define( 'DISALLOW_FILE_EDIT', true );

// Security keys (unique!)
define('AUTH_KEY', '[unique string]');
// ... etc

// Force SSL
define('FORCE_SSL_ADMIN', true);

// Limit revisions
define('WP_POST_REVISIONS', 5);
```

---

## 📱 Testing Checklist

### Functionality
- [ ] All pages load
- [ ] All links work
- [ ] Forms submit & deliver emails
- [ ] Search works
- [ ] Login/logout works
- [ ] All features functional

### Browsers
- [ ] Chrome (latest)
- [ ] Firefox (latest)
- [ ] Safari (latest)
- [ ] Edge (latest)
- [ ] Mobile browsers (iOS Safari, Chrome)

### Devices
- [ ] Desktop (1920px, 1366px)
- [ ] Laptop (1280px)
- [ ] Tablet (iPad, Android tablet)
- [ ] Mobile (iPhone, Android phones)
- [ ] Check landscape & portrait

### Performance
- [ ] PageSpeed Insights > 90
- [ ] GTmetrix Grade A
- [ ] Core Web Vitals pass
- [ ] Load time < 3s

### SEO
- [ ] Meta titles & descriptions
- [ ] Heading hierarchy (H1, H2, etc.)
- [ ] Alt text on images
- [ ] XML sitemap
- [ ] Robots.txt
- [ ] Schema markup (where applicable)
- [ ] Mobile-friendly test passes

### Accessibility
- [ ] Keyboard navigation works
- [ ] Screen reader friendly
- [ ] Color contrast sufficient (WCAG AA)
- [ ] Focus states visible
- [ ] Alt text on all images
- [ ] Forms have labels
- [ ] ARIA labels where needed

---

## 📚 Resources

**Official Docs:**
- WordPress Codex: https://codex.wordpress.org/
- Bricks Academy: https://academy.bricksbuilder.io/
- PHP Manual: https://www.php.net/manual/

**Learning:**
- WP Beginner: https://www.wpbeginner.com/
- Bricks Community: https://www.facebook.com/groups/bricksbuilder

**Tools:**
- WP-CLI: https://wp-cli.org/
- Query Monitor (debugging plugin)
- Debug Bar (debugging plugin)

---

*Last updated: 2025-10-24*
