# Design System - important.is

Framework dla spójnego designu we wszystkich projektach.

---

## 🎯 Design Philosophy

**Principles:**
- **Clarity** - clear hierarchy and purpose
- **Consistency** - patterns users recognize
- **Efficiency** - components that scale
- **Accessibility** - inclusive for all users
- **Beauty** - aesthetics that delight

---

## 🎨 Visual Foundation

### Typography

**Font Scales:**
```css
:root {
    /* Headings */
    --font-size-h1: 3rem;      /* 48px */
    --font-size-h2: 2.25rem;   /* 36px */
    --font-size-h3: 1.875rem;  /* 30px */
    --font-size-h4: 1.5rem;    /* 24px */
    --font-size-h5: 1.25rem;   /* 20px */
    --font-size-h6: 1rem;      /* 16px */

    /* Body */
    --font-size-base: 1rem;    /* 16px */
    --font-size-sm: 0.875rem;  /* 14px */
    --font-size-xs: 0.75rem;   /* 12px */
    --font-size-lg: 1.125rem;  /* 18px */
    --font-size-xl: 1.25rem;   /* 20px */

    /* Line Heights */
    --line-height-tight: 1.2;
    --line-height-normal: 1.5;
    --line-height-relaxed: 1.75;

    /* Font Weights */
    --font-weight-normal: 400;
    --font-weight-medium: 500;
    --font-weight-semibold: 600;
    --font-weight-bold: 700;
}
```

**Font Pairings (Recommended):**
- Inter (sans-serif) - modern, versatile
- Plus Jakarta Sans - friendly, rounded
- IBM Plex Sans - corporate, reliable
- Pair with serif for contrast when needed

---

### Color System

**Structure:**
```css
:root {
    /* Primary (Brand) */
    --color-primary-50: #...;
    --color-primary-100: #...;
    /* ... */
    --color-primary-500: #...;  /* Main */
    --color-primary-600: #...;
    /* ... */
    --color-primary-900: #...;

    /* Neutrals */
    --color-gray-50: #F9FAFB;
    --color-gray-100: #F3F4F6;
    --color-gray-200: #E5E7EB;
    /* ... */
    --color-gray-900: #111827;

    /* Semantic */
    --color-success: #10B981;
    --color-warning: #F59E0B;
    --color-error: #EF4444;
    --color-info: #3B82F6;

    /* Text */
    --color-text-primary: var(--color-gray-900);
    --color-text-secondary: var(--color-gray-600);
    --color-text-muted: var(--color-gray-500);

    /* Backgrounds */
    --color-bg-primary: #FFFFFF;
    --color-bg-secondary: var(--color-gray-50);
    --color-bg-tertiary: var(--color-gray-100);
}
```

**Usage Guidelines:**
- Primary: CTAs, links, key actions
- Neutrals: Text, backgrounds, borders
- Semantic: Success/error states
- Maintain WCAG AA contrast ratios (4.5:1 for text)

---

### Spacing Scale

**8px base grid:**
```css
:root {
    --spacing-0: 0;
    --spacing-1: 0.25rem;  /* 4px */
    --spacing-2: 0.5rem;   /* 8px */
    --spacing-3: 0.75rem;  /* 12px */
    --spacing-4: 1rem;     /* 16px */
    --spacing-5: 1.5rem;   /* 24px */
    --spacing-6: 2rem;     /* 32px */
    --spacing-8: 3rem;     /* 48px */
    --spacing-10: 4rem;    /* 64px */
    --spacing-12: 6rem;    /* 96px */
    --spacing-16: 8rem;    /* 128px */
}
```

---

### Shadows

```css
:root {
    --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
    --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
    --shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
}
```

---

### Border Radius

```css
:root {
    --radius-none: 0;
    --radius-sm: 0.25rem;    /* 4px */
    --radius-md: 0.5rem;     /* 8px */
    --radius-lg: 1rem;       /* 16px */
    --radius-full: 9999px;   /* Pill shape */
}
```

---

## 🧩 Components

### Buttons

**Variants:**
```html
<!-- Primary -->
<button class="btn btn--primary">Primary Action</button>

<!-- Secondary -->
<button class="btn btn--secondary">Secondary Action</button>

<!-- Outline -->
<button class="btn btn--outline">Outline</button>

<!-- Ghost -->
<button class="btn btn--ghost">Ghost</button>
```

**Sizes:**
```html
<button class="btn btn--sm">Small</button>
<button class="btn btn--md">Medium</button>
<button class="btn btn--lg">Large</button>
```

**CSS:**
```css
.btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: var(--spacing-3) var(--spacing-6);
    font-weight: var(--font-weight-semibold);
    border-radius: var(--radius-md);
    transition: all 0.2s;
    cursor: pointer;
}

.btn--primary {
    background-color: var(--color-primary-500);
    color: white;
}

.btn--primary:hover {
    background-color: var(--color-primary-600);
}
```

---

### Cards

```html
<div class="card">
    <div class="card__image">
        <img src="..." alt="...">
    </div>
    <div class="card__content">
        <h3 class="card__title">Title</h3>
        <p class="card__description">Description text</p>
        <a href="#" class="card__link">Read more</a>
    </div>
</div>
```

---

### Forms

**Input Fields:**
```html
<div class="form-group">
    <label for="name" class="form-label">Name</label>
    <input
        type="text"
        id="name"
        class="form-input"
        placeholder="Enter your name"
    >
    <span class="form-help">Help text here</span>
</div>
```

**States:**
- Default
- Focus
- Error
- Disabled

---

## 📐 Layout Patterns

### Container

```css
.container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 var(--spacing-4);
}

@media (min-width: 768px) {
    .container {
        padding: 0 var(--spacing-6);
    }
}
```

### Grid

```css
.grid {
    display: grid;
    gap: var(--spacing-6);
}

.grid--2-cols {
    grid-template-columns: repeat(2, 1fr);
}

.grid--3-cols {
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 768px) {
    .grid--2-cols,
    .grid--3-cols {
        grid-template-columns: 1fr;
    }
}
```

### Flex Utilities

```css
.flex { display: flex; }
.flex-col { flex-direction: column; }
.items-center { align-items: center; }
.justify-between { justify-content: space-between; }
.gap-4 { gap: var(--spacing-4); }
```

---

## 📱 Responsive Design

### Breakpoints

```css
/* Mobile first approach */

/* Small devices (landscape phones, 576px and up) */
@media (min-width: 576px) { }

/* Medium devices (tablets, 768px and up) */
@media (min-width: 768px) { }

/* Large devices (desktops, 992px and up) */
@media (min-width: 992px) { }

/* Extra large devices (large desktops, 1200px and up) */
@media (min-width: 1200px) { }
```

---

## ♿ Accessibility

### Minimum Requirements

**Color Contrast:**
- WCAG AA: 4.5:1 for normal text
- WCAG AA: 3:1 for large text (18px+)
- Tool: https://webaim.org/resources/contrastchecker/

**Focus States:**
```css
/* Always visible focus */
a:focus,
button:focus,
input:focus {
    outline: 2px solid var(--color-primary-500);
    outline-offset: 2px;
}
```

**Touch Targets:**
- Minimum 44x44px for interactive elements
- Adequate spacing between targets

**Semantic HTML:**
- Use proper heading hierarchy (h1 → h2 → h3)
- Use semantic elements (<nav>, <main>, <article>)
- ARIA labels where needed

---

## 🎬 Animations & Transitions

### Principles
- Subtle, purposeful
- Fast (< 300ms for micro-interactions)
- Respect `prefers-reduced-motion`

### Standard Transitions

```css
:root {
    --transition-fast: 150ms ease-in-out;
    --transition-base: 250ms ease-in-out;
    --transition-slow: 350ms ease-in-out;

    --easing-in: cubic-bezier(0.4, 0, 1, 1);
    --easing-out: cubic-bezier(0, 0, 0.2, 1);
    --easing-in-out: cubic-bezier(0.4, 0, 0.2, 1);
}

.btn {
    transition: all var(--transition-base);
}
```

### Respect User Preferences

```css
@media (prefers-reduced-motion: reduce) {
    *,
    *::before,
    *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
    }
}
```

---

## 📋 Design Checklist

### Before Development
- [ ] Design follows spacing scale
- [ ] Colors from palette
- [ ] Typography scale used
- [ ] Accessibility considered (contrast, sizes)
- [ ] Responsive design included
- [ ] Interactive states designed (hover, focus, active)

### During Development
- [ ] Using CSS variables
- [ ] Following BEM naming
- [ ] Components reusable
- [ ] Responsive tested
- [ ] Accessibility tested
- [ ] Performance optimized

---

## 🔧 Implementation in Bricks

### Setup

**1. Create Global Classes:**
- Typography classes
- Spacing utilities
- Color utilities
- Layout utilities

**2. Set Theme Styles:**
- CSS variables in Theme CSS
- Global element styles

**3. Build Components:**
- Create reusable blocks
- Save as templates
- Document usage

---

## 📚 Resources

**Tools:**
- Figma - Design files
- Coolors - Color palette generator
- Type Scale - Typography scale generator
- Contrast Checker - WCAG compliance

**Inspiration:**
- Refactoring UI - Design principles
- Tailwind CSS - Utility-first approach
- Material Design - Google's design system
- Apple Human Interface Guidelines

---

*Last updated: 2025-10-24*
