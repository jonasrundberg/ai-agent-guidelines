# Web Development Standards

## Overview
Web development guidelines for AI agents building modern web applications. These standards cover HTML, CSS, JavaScript/TypeScript, and responsive design principles.

---

## HTML Best Practices

### Semantic HTML
- **Use semantic elements** for better accessibility and SEO
- **Proper heading hierarchy** (h1 → h2 → h3, don't skip levels)
- **Meaningful attributes** (alt text, aria labels, roles)

### HTML Structure
```html
<!-- Good: Semantic HTML -->
<header>
  <nav aria-label="Main navigation">
    <ul>
      <li><a href="/">Home</a></li>
      <li><a href="/about">About</a></li>
    </ul>
  </nav>
</header>

<main>
  <article>
    <h1>Article Title</h1>
    <p>Article content...</p>
  </article>
  
  <aside>
    <h2>Related Content</h2>
    <p>Sidebar content...</p>
  </aside>
</main>

<footer>
  <p>&copy; 2025 Company Name</p>
</footer>

<!-- Bad: Non-semantic -->
<div class="header">
  <div class="nav">
    <div class="link"><a href="/">Home</a></div>
  </div>
</div>
```

### Accessibility
```html
<!-- Images with alt text -->
<img src="logo.png" alt="Company Logo">

<!-- Buttons vs Links -->
<button type="button" onclick="doAction()">Perform Action</button>
<a href="/page">Navigate to Page</a>

<!-- Form labels -->
<label for="email">Email Address</label>
<input type="email" id="email" name="email" required>

<!-- ARIA labels for icon buttons -->
<button aria-label="Close dialog">
  <span aria-hidden="true">×</span>
</button>
```

### Do's
- Use semantic HTML5 elements (`<header>`, `<nav>`, `<main>`, `<article>`, `<aside>`, `<footer>`)
- Include `alt` attributes for all images
- Use `<button>` for actions, `<a>` for navigation
- Maintain proper heading hierarchy
- Add ARIA labels where needed

### Don'ts
- Don't use `<div>` for everything - use semantic elements
- Don't skip heading levels (h1 → h3)
- Don't use generic text like "click here" for links
- Don't forget form labels

---

## CSS Best Practices

### Modern CSS Organization
- **Use CSS custom properties** (variables) for theming
- **Mobile-first approach** with min-width media queries
- **BEM or utility-first** naming conventions
- **Flexbox and Grid** for layouts

### CSS Examples
```css
/* CSS Custom Properties for theming */
:root {
  --color-primary: #4A9EFF;
  --color-background: #0A0E1A;
  --color-text: #E8EDF2;
  --spacing-sm: 0.5rem;
  --spacing-md: 1rem;
  --spacing-lg: 2rem;
  --border-radius: 8px;
}

/* Modern layout with Flexbox */
.container {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-md);
  padding: var(--spacing-lg);
}

/* Mobile-first responsive design */
.grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--spacing-md);
}

@media (min-width: 768px) {
  .grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

/* BEM naming convention */
.card {
  background: var(--color-background);
  border-radius: var(--border-radius);
  padding: var(--spacing-md);
}

.card__title {
  color: var(--color-text);
  font-size: 1.5rem;
  margin-bottom: var(--spacing-sm);
}

.card__content {
  color: var(--color-text);
  opacity: 0.8;
}

.card--highlighted {
  border: 2px solid var(--color-primary);
}

/* Modern button styles */
.button {
  padding: var(--spacing-sm) var(--spacing-md);
  border: none;
  border-radius: var(--border-radius);
  background: var(--color-primary);
  color: white;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.2s ease;
}

.button:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(74, 158, 255, 0.3);
}

.button:active {
  transform: translateY(0);
}
```

### Do's
- Use CSS custom properties for colors, spacing, and reusable values
- Prefer Flexbox and Grid over floats
- Use relative units (rem, em, %) over fixed pixels
- Write mobile-first media queries
- Use meaningful class names (BEM or descriptive)
- Group related properties together

### Don'ts
- Don't use `!important` unless absolutely necessary
- Don't use inline styles - keep CSS in stylesheets
- Don't use overly specific selectors (e.g., `div.container > ul > li > a`)
- Don't forget `:hover`, `:focus`, and `:active` states for interactive elements

---

## JavaScript/TypeScript Preferences

### Language Choice
- **Prefer TypeScript** for all new projects
- **Use ES6+ features** (arrow functions, destructuring, modules)
- **Async/await** over promises when possible

### JavaScript/TypeScript Examples
```typescript
// TypeScript interfaces for type safety
interface User {
  id: string;
  name: string;
  email: string;
  createdAt: Date;
}

interface ApiResponse<T> {
  data: T;
  status: number;
  message: string;
}

// Modern async function with error handling
async function fetchUser(userId: string): Promise<User> {
  try {
    const response = await fetch(`/api/users/${userId}`);
    
    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }
    
    const data: ApiResponse<User> = await response.json();
    return data.data;
    
  } catch (error) {
    console.error('Failed to fetch user:', error);
    throw error;
  }
}

// Destructuring and default parameters
function createCard({ 
  title, 
  content, 
  highlighted = false 
}: { 
  title: string; 
  content: string; 
  highlighted?: boolean;
}): HTMLElement {
  const card = document.createElement('div');
  card.className = `card ${highlighted ? 'card--highlighted' : ''}`;
  
  card.innerHTML = `
    <h2 class="card__title">${title}</h2>
    <p class="card__content">${content}</p>
  `;
  
  return card;
}

// Array methods over loops
const users: User[] = await fetchUsers();

// Filter and map
const activeUserNames = users
  .filter(user => user.isActive)
  .map(user => user.name);

// Reduce
const totalAge = users.reduce((sum, user) => sum + user.age, 0);

// Modern event handling
const button = document.querySelector('.button');

button?.addEventListener('click', async (event) => {
  event.preventDefault();
  
  try {
    const result = await performAction();
    showSuccessMessage(result);
  } catch (error) {
    showErrorMessage(error.message);
  }
});

// Optional chaining and nullish coalescing
const userName = user?.profile?.name ?? 'Anonymous';
const pageSize = config?.pagination?.size ?? 20;
```

### Module Organization
```typescript
// user.service.ts
export class UserService {
  private apiUrl = '/api/users';
  
  async getUser(id: string): Promise<User> {
    // Implementation
  }
  
  async updateUser(id: string, data: Partial<User>): Promise<User> {
    // Implementation
  }
}

// user.types.ts
export interface User {
  id: string;
  name: string;
  email: string;
}

export type UserRole = 'admin' | 'user' | 'guest';

// index.ts
export { UserService } from './user.service';
export type { User, UserRole } from './user.types';
```

### Do's
- Use TypeScript with strict mode enabled
- Use `const` and `let`, never `var`
- Prefer arrow functions for callbacks
- Use async/await for asynchronous code
- Use optional chaining (`?.`) and nullish coalescing (`??`)
- Destructure objects and arrays
- Use template literals for string concatenation
- Export types and interfaces separately

### Don'ts
- Don't use `var` - use `const` or `let`
- Don't use `any` type - be specific or use `unknown`
- Don't ignore TypeScript errors with `@ts-ignore`
- Don't mutate objects - prefer immutable patterns
- Don't use callbacks when async/await is clearer

---

## Responsive Design Approach

### Mobile-First Strategy
- **Design for mobile screens first**, then scale up
- **Use relative units** (rem, em, %, vh/vw)
- **Touch-friendly targets** (minimum 44×44px tap targets)
- **Breakpoints** based on content, not devices

### Responsive Patterns
```css
/* Mobile-first base styles */
.container {
  width: 100%;
  padding: 1rem;
}

.navigation {
  display: flex;
  flex-direction: column;
}

/* Tablet and up */
@media (min-width: 768px) {
  .container {
    max-width: 768px;
    margin: 0 auto;
    padding: 2rem;
  }
  
  .navigation {
    flex-direction: row;
    justify-content: space-between;
  }
}

/* Desktop and up */
@media (min-width: 1024px) {
  .container {
    max-width: 1200px;
  }
}

/* Responsive typography */
.title {
  font-size: clamp(1.5rem, 5vw, 3rem);
  line-height: 1.2;
}

/* Responsive images */
img {
  max-width: 100%;
  height: auto;
}

/* Responsive grid */
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
}
```

### Common Breakpoints
```css
/* Recommended breakpoints */
/* Small devices (phones) */
@media (min-width: 640px) { }

/* Medium devices (tablets) */
@media (min-width: 768px) { }

/* Large devices (desktops) */
@media (min-width: 1024px) { }

/* Extra large devices (large desktops) */
@media (min-width: 1280px) { }
```

### Do's
- Design mobile-first, enhance for larger screens
- Use `min-width` media queries (not `max-width`)
- Make touch targets at least 44×44px
- Test on actual devices, not just browser resizing
- Use viewport meta tag: `<meta name="viewport" content="width=device-width, initial-scale=1">`
- Use `clamp()` for responsive typography
- Use CSS Grid's `auto-fit` and `minmax()` for responsive layouts

### Don'ts
- Don't design desktop-first and try to scale down
- Don't rely on device-specific breakpoints
- Don't use fixed pixel widths for container elements
- Don't forget to test touch interactions on mobile

---

## Quick Reference

| Category | Standard |
|----------|----------|
| **HTML** | Semantic elements, accessibility, proper hierarchy |
| **CSS** | CSS variables, Flexbox/Grid, mobile-first |
| **JavaScript** | TypeScript, ES6+, async/await |
| **Naming** | BEM for CSS, camelCase for JS/TS |
| **Responsive** | Mobile-first, relative units, min-width queries |
| **Accessibility** | Alt text, ARIA labels, keyboard navigation |

---

## Framework-Specific Notes

### React/Next.js
```typescript
// Functional components with TypeScript
interface ButtonProps {
  label: string;
  onClick: () => void;
  variant?: 'primary' | 'secondary';
}

export function Button({ 
  label, 
  onClick, 
  variant = 'primary' 
}: ButtonProps) {
  return (
    <button 
      className={`button button--${variant}`}
      onClick={onClick}
    >
      {label}
    </button>
  );
}

// Use React hooks
import { useState, useEffect } from 'react';

function UserProfile({ userId }: { userId: string }) {
  const [user, setUser] = useState<User | null>(null);
  const [loading, setLoading] = useState(true);
  
  useEffect(() => {
    async function loadUser() {
      const data = await fetchUser(userId);
      setUser(data);
      setLoading(false);
    }
    
    loadUser();
  }, [userId]);
  
  if (loading) return <div>Loading...</div>;
  if (!user) return <div>User not found</div>;
  
  return <div>{user.name}</div>;
}
```

### Vue.js
```typescript
// Composition API with TypeScript
<script setup lang="ts">
import { ref, onMounted } from 'vue';

interface User {
  id: string;
  name: string;
}

const user = ref<User | null>(null);
const loading = ref(true);

onMounted(async () => {
  user.value = await fetchUser('123');
  loading.value = false;
});
</script>

<template>
  <div v-if="loading">Loading...</div>
  <div v-else-if="user">{{ user.name }}</div>
  <div v-else>User not found</div>
</template>
```
