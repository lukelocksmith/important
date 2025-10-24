# Coding Standards - important.is

Standardy kodowania dla spójności, jakości i maintainability.

---

## 🎯 General Principles

1. **Readable > Clever** - kod czytamy 10x częściej niż piszemy
2. **Consistent** - follow conventions, nie wymyślaj
3. **DRY** - Don't Repeat Yourself
4. **KISS** - Keep It Simple, Stupid
5. **YAGNI** - You Aren't Gonna Need It (don't over-engineer)
6. **Comment Why, Not What** - kod pokazuje "what", komentarze "why"

---

## 📋 PHP Standards (WordPress)

### Follow WordPress Coding Standards
- https://developer.wordpress.org/coding-standards/wordpress-coding-standards/php/

### Key Points

**Naming:**
```php
// Functions: lowercase, underscores
function important_get_post_data() {}

// Classes: PascalCase
class Important_Custom_Widget {}

// Constants: UPPERCASE
define( 'IMPORTANT_VERSION', '1.0.0' );

// Variables: lowercase, underscores
$user_data = array();
```

**Indentation:**
- Tabs, not spaces
- Opening brace on same line

**Example:**
```php
<?php
function important_custom_function( $arg1, $arg2 = 'default' ) {
    if ( $arg1 === 'something' ) {
        // Do something
        return true;
    }

    return false;
}
```

**Arrays:**
```php
// Short array syntax
$array = [
    'key1' => 'value1',
    'key2' => 'value2',
];

// Trailing comma OK
```

**Sanitization & Escaping:**
```php
// Always sanitize input
$name = sanitize_text_field( $_POST['name'] );

// Always escape output
echo esc_html( $name );
echo esc_url( $url );
echo esc_attr( $attribute );
```

**Security:**
```php
// Use nonces
wp_nonce_field( 'action_name', 'nonce_field' );

// Check nonce
if ( ! wp_verify_nonce( $_POST['nonce_field'], 'action_name' ) ) {
    die( 'Security check failed' );
}

// Check capabilities
if ( ! current_user_can( 'edit_posts' ) ) {
    return;
}
```

---

## 🎨 CSS Standards

### Methodology: BEM-inspired

**Block Element Modifier:**
```css
/* Block */
.card {}

/* Element */
.card__title {}
.card__image {}
.card__description {}

/* Modifier */
.card--featured {}
.card__title--large {}
```

**Naming:**
- Lowercase, hyphens
- Descriptive names
- Avoid abbreviations unless very clear

**Organization:**
```css
/* 1. Positioning */
.element {
    position: absolute;
    top: 0;
    left: 0;
    z-index: 10;
}

/* 2. Box Model */
.element {
    display: flex;
    width: 100%;
    padding: 1rem;
    margin: 0 auto;
}

/* 3. Typography */
.element {
    font-size: 1rem;
    line-height: 1.5;
    color: #333;
}

/* 4. Visual */
.element {
    background-color: #fff;
    border: 1px solid #ddd;
}

/* 5. Misc */
.element {
    cursor: pointer;
    transition: all 0.3s;
}
```

**CSS Variables:**
```css
:root {
    --color-primary: #FF6B6B;
    --spacing-md: 2rem;
    --font-heading: 'Inter', sans-serif;
}

.element {
    color: var(--color-primary);
    padding: var(--spacing-md);
    font-family: var(--font-heading);
}
```

**Responsive:**
```css
/* Mobile first */
.element {
    font-size: 1rem;
}

/* Tablet and up */
@media (min-width: 768px) {
    .element {
        font-size: 1.25rem;
    }
}

/* Desktop */
@media (min-width: 1200px) {
    .element {
        font-size: 1.5rem;
    }
}
```

---

## ⚡ JavaScript Standards

### Modern ES6+
```javascript
// Use const/let, not var
const API_URL = 'https://api.example.com';
let counter = 0;

// Arrow functions
const double = (num) => num * 2;

// Template literals
const greeting = `Hello, ${name}!`;

// Destructuring
const { title, content } = post;

// Spread operator
const newArray = [...oldArray, newItem];
```

**Naming:**
```javascript
// Variables/functions: camelCase
const userData = {};
function getUserData() {}

// Classes: PascalCase
class UserManager {}

// Constants: UPPER_SNAKE_CASE
const API_KEY = 'xxx';
```

**Functions:**
```javascript
// Clear, single responsibility
function calculateTotal(items) {
    return items.reduce((sum, item) => sum + item.price, 0);
}

// Avoid side effects when possible
// Return new values, don't mutate
```

**Async:**
```javascript
// Async/await over promises when readable
async function fetchData() {
    try {
        const response = await fetch(API_URL);
        const data = await response.json();
        return data;
    } catch (error) {
        console.error('Error fetching data:', error);
    }
}
```

**Comments:**
```javascript
/**
 * Fetches user data from API
 * @param {number} userId - The user ID
 * @returns {Promise<Object>} User data object
 */
async function fetchUser(userId) {
    // Implementation
}
```

---

## 📝 HTML Standards

### Semantic HTML
```html
<!-- Good -->
<header>
    <nav>
        <ul>
            <li><a href="#">Link</a></li>
        </ul>
    </nav>
</header>

<main>
    <article>
        <h1>Title</h1>
        <p>Content</p>
    </article>
</main>

<footer>
    <p>&copy; 2025 Company</p>
</footer>

<!-- Avoid divitis -->
<!-- Bad: <div><div><div>...</div></div></div> -->
```

**Accessibility:**
```html
<!-- Alt text on images -->
<img src="photo.jpg" alt="Description of photo">

<!-- Labels on inputs -->
<label for="name">Name:</label>
<input type="text" id="name" name="name">

<!-- ARIA when needed -->
<button aria-label="Close dialog">×</button>

<!-- Semantic headings (h1->h2->h3, no skipping) -->
<h1>Main Title</h1>
<h2>Section</h2>
<h3>Subsection</h3>
```

---

## 🔧 Bricks Builder Standards

### Structure
```
.section (Section/Container)
  .section__container (Container, max-width)
    .section__content (Inner wrapper)
      .section__title (Heading)
      .section__description (Text)
      .section__cta (Button)
```

### Classes
- Use global classes for reusability
- Prefix custom classes: `important-*`
- Follow BEM for custom components

### Performance
- Minimize custom CSS (use Bricks' controls when possible)
- Lazy load images
- Defer non-critical scripts
- Minimize DOM depth

---

## 📚 Documentation Standards

### Code Comments

**PHP:**
```php
/**
 * Get formatted post data
 *
 * Retrieves post data and formats it for display,
 * including custom fields and taxonomies.
 *
 * @param int $post_id Post ID
 * @return array Formatted post data
 */
function important_get_formatted_post( $post_id ) {
    // Implementation
}
```

**JavaScript:**
```javascript
/**
 * Initialize slider
 *
 * Sets up Swiper slider with custom options
 * @param {string} selector - CSS selector for slider
 * @param {Object} options - Slider options
 */
function initSlider(selector, options = {}) {
    // Implementation
}
```

**Inline Comments:**
```php
// Good: Explain WHY
// Using transient to cache API response for 1 hour
set_transient( 'api_data', $data, HOUR_IN_SECONDS );

// Bad: Explain WHAT (code already shows this)
// Set transient
set_transient( 'api_data', $data, HOUR_IN_SECONDS );
```

### README Files
Every custom plugin/theme should have README:
```markdown
# Plugin Name

## Description
Brief description of what it does

## Installation
How to install

## Usage
How to use

## Configuration
Any configuration needed

## Dependencies
Required plugins/libraries

## Changelog
Version history
```

---

## ✅ Code Review Checklist

### Before Committing
- [ ] Code follows standards
- [ ] No console.logs or var_dumps
- [ ] No commented-out code (remove it)
- [ ] Functions are well-named and single-purpose
- [ ] No magic numbers (use constants)
- [ ] Input sanitized, output escaped
- [ ] Error handling implemented
- [ ] Tested locally
- [ ] No breaking changes to existing functionality

### Reviewing Others' Code
- [ ] Readable and understandable
- [ ] Follows standards
- [ ] Secure (no vulnerabilities)
- [ ] Performant (no obvious issues)
- [ ] Tested
- [ ] Documented if complex

---

## 🎯 Quality Metrics

### Aim For:
- Functions < 50 lines (generally)
- Max nesting depth: 4 levels
- Cyclomatic complexity < 10
- DRY: no copy-paste code
- Test coverage: as high as practical
- Page load time: < 3s
- Lighthouse score: 90+

---

## 🔧 Tools for Enforcement

### Linters
- **PHP_CodeSniffer** - PHP linting (WordPress standards)
- **ESLint** - JavaScript linting
- **Stylelint** - CSS linting
- **Prettier** - Code formatting

### VS Code Extensions
- PHP Intelephense
- ESLint
- Prettier
- Better Comments

### Git Hooks
- Pre-commit: run linters
- Pre-push: run tests (when we have them)

---

## 📖 Learning Resources

**PHP/WordPress:**
- WordPress Coding Standards: https://developer.wordpress.org/coding-standards/
- PHP The Right Way: https://phptherightway.com/

**JavaScript:**
- Airbnb JavaScript Style Guide: https://github.com/airbnb/javascript
- Clean Code JavaScript: https://github.com/ryanmcdermott/clean-code-javascript

**CSS:**
- BEM Methodology: http://getbem.com/
- CSS Guidelines: https://cssguidelin.es/

---

*Last updated: 2025-10-24*
