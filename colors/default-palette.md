# Default Color Palette 

## Overview
This color palette is designed for any user interfaces.
The theme uses soft, clean colors with a light aesthetic.

---

## Primary Colors

### Background & Surfaces
- **`#F5F7FA`** - Main background
  - Use for: Page backgrounds, main canvas areas
  - Soft off-white with subtle blue-gray tint

- **`#1A1F2E`** - Secondary surface
  - Use for: Cards, panels, modals, elevated components
  - Dark surface for elevated components and contrast

- **`#2A3142`** - Borders & dividers
  - Use for: Borders, dividers, subtle separators
  - Creates definition without harsh contrast

---

## Accent Colors

### Interactive Elements
- **`#4A9EFF`** - Primary accent (blue)
  - Use for: Hover states, highlights, selected items
  - Main interactive color for user feedback

- **`#3B7DD6`** - Darker blue (active state)
  - Use for: Active/pressed states, selected navigation items
  - Darker variant for active interactions

- **`#5DADE2`** - Light blue (links)
  - Use for: Hyperlinks, clickable text elements
  - Lighter, more approachable blue for text-based interactions

---

## Text Colors

### Typography Hierarchy
- **`#1A1F2E`** - Primary text (on light backgrounds)
  - Use for: Headings, body text, primary content on light backgrounds
  - High contrast dark text

- **`#E8EDF2`** - Primary text (on dark backgrounds)
  - Use for: Headings, body text on dark surfaces
  - High contrast light text

- **`#6B7A8F`** - Secondary text
  - Use for: Subtitles, descriptions, labels
  - Works on both light and dark backgrounds

- **`#9BA8B8`** - Tertiary text
  - Use for: Metadata, timestamps, placeholder text
  - Lowest emphasis for auxiliary information

---

## Status & Feedback Colors

### System Feedback
- **`#4CAF50`** - Success/positive
  - Use for: Success messages, positive confirmations, completed states
  - Standard green for positive feedback

- **`#FF6B6B`** - Error/negative
  - Use for: Error messages, destructive actions, failed states
  - Coral red for negative feedback (softer than pure red)

- **`#FFA726`** - Warning
  - Use for: Warning messages, caution states, pending actions
  - Orange for attention-requiring states

- **`#64B5F6`** - Info
  - Use for: Informational messages, tips, neutral notifications
  - Light blue for informational feedback

---

## Usage Guidelines

### Do's
- Use `#F5F7FA` as the base for all pages
- Layer `#1A1F2E` on top for cards and dark components
- Use `#4A9EFF` sparingly for important interactive elements
- Maintain text hierarchy with appropriate colors based on background
- Use `#1A1F2E` for text on light backgrounds, `#E8EDF2` for text on dark backgrounds
- Use status colors only for their intended purposes

### Don'ts
- Don't use bright, saturated colors outside the status palette
- Don't mix status colors for non-status purposes
- Don't use pure black (`#000000`) or pure white (`#FFFFFF`) - use designated palette colors
- Don't create harsh borders - use `#2A3142` for subtle definition
- Don't place `#1A1F2E` text on `#1A1F2E` backgrounds

### Accessibility
- Primary text (`#1A1F2E`) on main background (`#F5F7FA`) meets WCAG AAA standards
- Light text (`#E8EDF2`) on dark surfaces (`#1A1F2E`) meets WCAG AA standards
- Accent colors (`#4A9EFF`, `#5DADE2`) provide sufficient contrast for interactive elements
- Status colors are distinguishable for colorblind users

### Example Component Styling
```css
/* Button primary */
background: #4A9EFF;
color: #E8EDF2;

/* Button primary hover */
background: #3B7DD6;

/* Card on light background */
background: #FFFFFF;
border: 1px solid #2A3142;
color: #1A1F2E;

/* Card on dark background */
background: #1A1F2E;
border: 1px solid #2A3142;
color: #E8EDF2;

/* Input field on light background */
background: #FFFFFF;
border: 1px solid #2A3142;
color: #1A1F2E;

/* Input field focus */
border-color: #4A9EFF;

/* Link on light background */
color: #5DADE2;

/* Link on dark background */
color: #5DADE2;
```

---

## Quick Reference

| Purpose | Color | Hex |
|---------|-------|-----|
| Main background | Soft off-white | `#F5F7FA` |
| Card/panel (dark) | Dark surface | `#1A1F2E` |
| Border | Subtle gray-blue | `#2A3142` |
| Hover/highlight | Blue | `#4A9EFF` |
| Active state | Dark blue | `#3B7DD6` |
| Link | Light blue | `#5DADE2` |
| Primary text (light bg) | Dark blue-gray | `#1A1F2E` |
| Primary text (dark bg) | Off-white | `#E8EDF2` |
| Secondary text | Medium gray | `#6B7A8F` |
| Tertiary text | Light gray | `#9BA8B8` |
| Success | Green | `#4CAF50` |
| Error | Coral red | `#FF6B6B` |
| Warning | Orange | `#FFA726` |
| Info | Light blue | `#64B5F6` |