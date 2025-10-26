# Default Color Palette 

## Overview
This adaptive color palette is designed for professional tech applications with support for both light and dark themes.
The palette uses a sophisticated blue-gray aesthetic with carefully balanced contrast and muted accent colors.
Both themes share consistent accent and status colors for unified branding across modes.

---

## Light Theme Colors

### Background & Surfaces (Light Mode)
- **`#EEF2F6`** - Main background (light)
  - Use for: Page backgrounds, main canvas areas
  - Slightly darker off-white with subtle blue-gray tint for better contrast
  - Tailwind equivalent: `bg-gray-100` or custom

- **`#FFFFFF`** - Secondary surface (light)
  - Use for: Cards, panels, modals, header/footer
  - Pure white for elevated components
  - Tailwind equivalent: `bg-white`

- **`#EEF2F6`** - Content background gradient start (light)
  - Use for: Shaded content sections with subtle gradient
  - Creates visual hierarchy in light mode
  - Gradient: `linear-gradient(135deg, #EEF2F6 0%, #FFFFFF 100%)`

### Borders & Text (Light Mode)
- **`#E5E7EB`** - Borders & dividers (light)
  - Use for: Borders, dividers, subtle separators
  - Soft gray for definition without harshness
  - Tailwind equivalent: `border-gray-200`

- **`#1A1F2E`** - Primary text (light mode)
  - Use for: Headings, body text, primary content
  - Dark blue-gray for strong readability on light backgrounds

- **`#6B7A8F`** - Secondary text (light mode)
  - Use for: Subtitles, descriptions, labels
  - Medium gray for supporting text

- **`#9BA8B8`** - Tertiary text (light mode)
  - Use for: Metadata, timestamps, placeholder text
  - Light gray for low-emphasis information

---

## Dark Theme Colors

### Background & Surfaces (Dark Mode)
- **`#0A0E1A`** - Main background (dark)
  - Use for: Page backgrounds, main canvas areas
  - Deep dark blue-black, modern tech aesthetic
  - Tailwind equivalent: `bg-gray-900` or custom

- **`#1A1F2E`** - Secondary surface (dark)
  - Use for: Cards, panels, modals, header/footer
  - Slightly lighter dark surface for layered components
  - Tailwind equivalent: `bg-gray-800`

- **`#1C2832`** - Content background gradient start (dark)
  - Use for: Shaded content sections with subtle gradient
  - Blue-gray tint for visual hierarchy
  - Gradient: `linear-gradient(135deg, #1C2832 0%, #1A1F2E 100%)`

### Borders & Text (Dark Mode)
- **`#2A3142`** - Borders & dividers (dark)
  - Use for: Borders, dividers, subtle separators
  - Neutral dark gray for definition without harshness
  - Tailwind equivalent: `border-gray-700`

- **`#E8EDF2`** - Primary text (dark mode)
  - Use for: Headings, body text, primary content
  - Light gray for strong readability on dark backgrounds
  - Tailwind equivalent: `text-gray-100`

- **`#9BA8B8`** - Secondary text (dark mode)
  - Use for: Subtitles, descriptions, labels
  - Medium gray for supporting text
  - Tailwind equivalent: `text-gray-400`

- **`#6B7A8F`** - Tertiary text (dark mode)
  - Use for: Metadata, timestamps, placeholder text
  - Darker gray for low-emphasis information
  - Tailwind equivalent: `text-gray-500`

### Sidebar (Dark Mode)
- **Sidebar gradient (dark)**: `linear-gradient(135deg, #1A1F2E 0%, #2A3142 50%, #3A4556 100%)`
  - Use for: Side navigation panels in dark mode
  - Darker variant of the main theme colors

---

## Shared Colors (Both Themes)

### Interactive Elements
- **`#5A7A99`** - Primary accent (highlight)
  - Use for: Primary buttons, important interactive elements
  - Muted blue-gray for professional calls-to-action
  - Works in both light and dark modes

- **`#4D6A85`** - Darker accent (active state)
  - Use for: Hover states, active interactions
  - Deeper blue variant for interactive feedback
  - Works in both light and dark modes

- **`#6B8CAE`** - Light accent (links)
  - Use for: Links, secondary interactive elements
  - Lighter blue for text links and less prominent actions
  - Works in both light and dark modes

### Sidebar (Light Mode)
- **Sidebar gradient (light)**: `linear-gradient(135deg, #4D6A85 0%, #5A7A99 50%, #7A9FBD 100%)`
  - Use for: Side navigation panels in light mode
  - Blue-gray gradient complementing the light theme

---

## Status & Feedback Colors

### System Feedback
- **`#5C8D6F`** - Success/positive
  - Use for: Success messages, positive confirmations, completed states
  - Muted sage green, professional and calming

- **`#C75B5B`** - Error/negative
  - Use for: Error messages, destructive actions, failed states
  - Muted red-coral, clear but not alarming

- **`#D4945C`** - Warning
  - Use for: Warning messages, caution states, pending actions
  - Muted amber-orange for attention without aggression

- **`#6B8CAE`** - Info
  - Use for: Informational messages, tips, neutral notifications
  - Muted blue, calm and informative

---

## Special Elements

### Badges & Pills
- **Success badge (light mode)**: `bg: #E8F5E9` / `text: #2D5940`
  - Use for: Status badges in light theme
  - Light green background with dark green text
  - Tailwind: `bg-green-100` / `text-green-700`

- **Success badge (dark mode)**: `bg: #2D5940` / `text: #6FB88A`
  - Use for: Status badges in dark theme
  - Dark green background with light green text
  - Tailwind: `bg-green-900` / `text-green-300`

---

### Usage Guidelines

### Do's
- **Light mode**: Use `#EEF2F6` or custom bg as the base for all pages
- **Dark mode**: Use `#0A0E1A` or `bg-gray-900` as the base for all pages
- Layer white/`#1A1F2E` for cards and elevated components (depending on theme)
- Use gradients for content sections to create subtle depth in both themes
- Use accent colors (`#5A7A99`) sparingly for important actions
- Maintain text hierarchy with the three text shades in each theme
- Use distinct status colors only for their intended purposes
- Keep overall aesthetic professional and polished in both modes
- Use Tailwind's dark mode classes: `class="bg-white dark:bg-gray-800"`

### Don'ts
- Don't use bright, saturated colors outside the accent/status palette
- Don't mix status colors for non-status purposes
- Don't forget to add dark mode variants for all color-dependent elements
- Don't create harsh borders - use `#E5E7EB` (light) or `#2A3142` (dark)
- Don't overuse the primary accent - maintain professional restraint
- Don't use hard-coded colors without dark mode alternatives

### Accessibility
- **Light mode**: Primary text (`#1A1F2E`) on main background (`#EEF2F6`) meets WCAG AA standards
- **Dark mode**: Primary text (`#E8EDF2`) on main background (`#0A0E1A`) meets WCAG AA standards
- All status colors are distinguishable for colorblind users in both themes
- Accent colors provide sufficient contrast for interactive elements
- Text hierarchy ensures clear visual distinction in both modes

### Example Component Styling

**Using Tailwind CSS (Recommended)**:
```html
<!-- Page background -->
<body class="bg-[#EEF2F6] dark:bg-gray-900">

<!-- Header/Footer -->
<header class="bg-white dark:bg-gray-800 border-b border-gray-200 dark:border-gray-700">

<!-- Card with gradient content -->
<div class="bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-xl shadow-lg">
  <div class="gradient-content-bg p-6">
    <!-- Content -->
  </div>
</div>

<!-- Button primary -->
<button class="bg-blue-highlight hover:bg-blue-active text-white px-5 py-1.5 rounded-lg">
  Primary Action
</button>

<!-- Button secondary -->
<button class="bg-white dark:bg-gray-700 hover:bg-gray-100 dark:hover:bg-gray-600 
               text-gray-900 dark:text-gray-100 border border-gray-300 dark:border-gray-600 
               px-5 py-1.5 rounded-lg">
  Secondary Action
</button>

<!-- Link -->
<a class="text-blue-link hover:text-blue-highlight">Learn More</a>

<!-- Success badge -->
<span class="bg-green-100 dark:bg-green-900 text-green-700 dark:text-green-300 
             text-xs font-medium px-3 py-1 rounded-full uppercase">
  Active
</span>
```

**CSS Gradients**:
```css
/* Light mode content gradient */
.gradient-content-bg {
  background: linear-gradient(135deg, #EEF2F6 0%, #FFFFFF 100%);
}

/* Dark mode content gradient */
.dark .gradient-content-bg {
  background: linear-gradient(135deg, #1C2832 0%, #1A1F2E 100%);
}

/* Light mode sidebar gradient */
.gradient-sidebar {
  background: linear-gradient(135deg, #4D6A85 0%, #5A7A99 50%, #7A9FBD 100%);
}

/* Dark mode sidebar gradient */
.dark .gradient-sidebar {
  background: linear-gradient(135deg, #1A1F2E 0%, #2A3142 50%, #3A4556 100%);
}
```

**Tailwind Config**:
```javascript
tailwind.config = {
  darkMode: 'class',
  theme: {
    extend: {
      colors: {
        'blue-highlight': '#5A7A99',
        'blue-active': '#4D6A85',
        'blue-link': '#6B8CAE',
        'status-success': '#5C8D6F',
        'status-error': '#C75B5B',
        'status-warning': '#D4945C',
        'status-info': '#6B8CAE',
      }
    }
  }
}
```

---

## Quick Reference

### Light Theme
| Purpose | Color | Hex | Tailwind |
|---------|-------|-----|----------|
| Main background | Slightly darker off-white | `#EEF2F6` | `bg-[#EEF2F6]` |
| Secondary surface | White | `#FFFFFF` | `bg-white` |
| Border | Light gray | `#E5E7EB` | `border-gray-200` |
| Primary text | Dark blue-gray | `#1A1F2E` | `text-gray-900` |
| Secondary text | Medium gray | `#6B7A8F` | `text-gray-600` |
| Tertiary text | Light gray | `#9BA8B8` | `text-gray-500` |

### Dark Theme
| Purpose | Color | Hex | Tailwind |
|---------|-------|-----|----------|
| Main background | Dark blue-black | `#0A0E1A` | `bg-gray-900` |
| Secondary surface | Dark surface | `#1A1F2E` | `bg-gray-800` |
| Content background | Blue-gray tint | `#1C2832` | Custom |
| Border | Dark gray | `#2A3142` | `border-gray-700` |
| Primary text | Light gray | `#E8EDF2` | `text-gray-100` |
| Secondary text | Medium gray | `#9BA8B8` | `text-gray-400` |
| Tertiary text | Dark gray | `#6B7A8F` | `text-gray-500` |

### Shared Colors (Both Themes)
| Purpose | Color | Hex | Usage |
|---------|-------|-----|-------|
| Primary accent | Muted blue-gray | `#5A7A99` | Buttons, highlights |
| Accent active | Deep blue-gray | `#4D6A85` | Hover states |
| Links | Light blue-gray | `#6B8CAE` | Text links |
| Success | Sage green | `#5C8D6F` | Success messages |
| Error | Muted coral | `#C75B5B` | Error messages |
| Warning | Muted amber | `#D4945C` | Warnings |
| Info | Muted blue | `#6B8CAE` | Info messages |