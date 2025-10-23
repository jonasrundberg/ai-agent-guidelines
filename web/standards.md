# Web Development Standards

## Overview
Web development guidelines for AI agents building modern web applications using Tailwind CSS and vanilla JavaScript/HTML.

---

## HTML Structure

### Semantic Elements
- Use `<header>`, `<nav>`, `<main>`, `<article>`, `<aside>`, `<footer>`
- Maintain proper heading hierarchy (h1 → h2 → h3)
- Use `<button>` for actions, `<a>` for navigation

### Accessibility Essentials
```html
<!-- Images need alt text -->
<img src="logo.png" alt="Company Logo">

<!-- Form labels required -->
<label for="email">Email</label>
<input type="email" id="email" name="email" required>

<!-- ARIA labels for icon-only buttons -->
<button aria-label="Close">×</button>
```

---

## Tailwind CSS

### Setup (CDN)
Use the CDN with inline config for custom colors:

```html
<script src="https://cdn.tailwindcss.com"></script>
<script>
    tailwind.config = {
        theme: {
            extend: {
                colors: {
                    'primary': '#4A9EFF',
                    'primary-dark': '#3B7DD6',
                }
            }
        }
    }
</script>
```

### Common Patterns
```html
<!-- Button -->
<button class="bg-primary hover:bg-primary-dark text-white px-4 py-2 rounded">
    Click Me
</button>

<!-- Card -->
<div class="bg-white border border-gray-300 rounded-lg p-4">
    <h2 class="text-xl font-bold mb-2">Title</h2>
    <p class="text-gray-600">Content</p>
</div>

<!-- Responsive Grid -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
    <!-- items -->
</div>

<!-- Flexbox Layout -->
<div class="flex flex-col md:flex-row gap-4">
    <!-- items -->
</div>
```

### Do's
- Use Tailwind utility classes directly in HTML
- Define custom colors in config for brand colors
- Use responsive prefixes (`sm:`, `md:`, `lg:`, `xl:`)
- Use state variants (`hover:`, `focus:`, `active:`)

### Don'ts
- Don't write custom CSS unless absolutely necessary
- Don't use arbitrary values excessively (use config instead)
- Don't forget responsive design with breakpoint prefixes

---

## Responsive Design

### Desktop-First Approach
- **Design for full-size monitors first**, then adapt for mobile
- Apps must work on both desktop and mobile devices
- Prioritize desktop experience unless specifically instructed otherwise
- Use responsive breakpoints to adjust layouts for smaller screens

### Tailwind Breakpoints
```html
<!-- Desktop-first: Base styles for desktop, adapt for mobile -->
<div class="grid grid-cols-3 md:grid-cols-2 sm:grid-cols-1 gap-4">
    <!-- 3 columns on desktop, 2 on tablet, 1 on mobile -->
</div>

<!-- Show/hide based on screen size -->
<div class="block lg:hidden">Mobile menu</div>
<div class="hidden lg:block">Desktop navigation</div>
```

---

## JavaScript Patterns

### Modern JavaScript (ES6+)
```javascript
// Async/await for API calls
async function fetchUser(userId) {
    try {
        const response = await fetch(`/api/users/${userId}`);
        if (!response.ok) throw new Error('Failed to fetch');
        return await response.json();
    } catch (error) {
        console.error('Error:', error);
    }
}

// DOM manipulation
const button = document.querySelector('#myButton');
button?.addEventListener('click', async () => {
    const data = await fetchUser(123);
    updateUI(data);
});

// Array methods
const activeUsers = users
    .filter(user => user.active)
    .map(user => user.name);
```

### Do's
- Use `const` and `let`, never `var`
- Use async/await for asynchronous operations
- Use optional chaining (`?.`) and nullish coalescing (`??`)
- Use template literals for strings
- Use arrow functions

### Don'ts
- Don't use `var`
- Don't ignore errors in try/catch blocks
- Don't mutate objects directly

---

## Quick Reference

| Category | Standard |
|----------|----------|
| **HTML** | Semantic elements, accessibility |
| **CSS** | Tailwind CSS utility classes |
| **JavaScript** | Modern ES6+, async/await |
| **Responsive** | Desktop-first, works on both desktop and mobile |
| **Breakpoints** | `sm:` (640px), `md:` (768px), `lg:` (1024px), `xl:` (1280px) |
