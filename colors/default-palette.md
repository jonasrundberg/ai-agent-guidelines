# Default Color Palette 

## Overview
This color palette is designed for any user interfaces.
The theme uses muted but clear colors with a darker aesthetic.

---

## Primary Colors

### Background & Surfaces
- **`#0A0E1A`** - Main background color
  - Use for: Page backgrounds, main container backgrounds
  - Dark blue-black that provides the foundation for all interfaces

- **`#1A1F2E`** - Secondary surface
  - Use for: Cards, panels, modals, elevated components
  - Slightly lighter than main background for visual hierarchy

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
- **`#E8EDF2`** - Primary text
  - Use for: Headings, body text, primary content
  - High contrast white with slight blue tint

- **`#9BA8B8`** - Secondary text
  - Use for: Subtitles, descriptions, labels
  - Reduced emphasis for supporting information

- **`#6B7A8F`** - Tertiary text
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
- Use `#0A0E1A` as the base for all pages
- Layer `#1A1F2E` on top for cards and components
- Use `#4A9EFF` sparingly for important interactive elements
- Maintain text hierarchy with the three text colors
- Use status colors only for their intended purposes

### Don'ts
- Don't use bright, saturated colors outside the status palette
- Don't mix status colors for non-status purposes
- Don't use pure white (`#FFFFFF`) - always use `#E8EDF2` for text
- Don't create harsh borders - use `#2A3142` for subtle definition

### Accessibility
- Primary text (`#E8EDF2`) on main background (`#0A0E1A`) meets WCAG AA standards
- Accent colors (`#4A9EFF`, `#5DADE2`) provide sufficient contrast for interactive elements
- Status colors are distinguishable for colorblind users

### Example Component Styling
```css
/* Button primary */
background: #4A9EFF;
color: #E8EDF2;

/* Button primary hover */
background: #3B7DD6;

/* Card */
background: #1A1F2E;
border: 1px solid #2A3142;

/* Input field */
background: #1A1F2E;
border: 1px solid #2A3142;
color: #E8EDF2;

/* Input field focus */
border-color: #4A9EFF;

/* Link */
color: #5DADE2;
```

---

## Quick Reference

| Purpose | Color | Hex |
|---------|-------|-----|
| Main background | Dark blue-black | `#0A0E1A` |
| Card/panel | Secondary surface | `#1A1F2E` |
| Border | Subtle gray-blue | `#2A3142` |
| Hover/highlight | Blue | `#4A9EFF` |
| Active state | Dark blue | `#3B7DD6` |
| Link | Light blue | `#5DADE2` |
| Primary text | Off-white | `#E8EDF2` |
| Secondary text | Medium gray | `#9BA8B8` |
| Tertiary text | Dark gray | `#6B7A8F` |
| Success | Green | `#4CAF50` |
| Error | Coral red | `#FF6B6B` |
| Warning | Orange | `#FFA726` |
| Info | Light blue | `#64B5F6` |