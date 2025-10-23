# Default Color Palette 

## Overview
This dark theme color palette is designed for professional tech applications.
The theme uses a sophisticated dark blue-gray aesthetic with carefully balanced contrast and muted accent colors.

---

## Primary Colors

### Background & Surfaces
- **`#0A0E1A`** - Main background
  - Use for: Page backgrounds, main canvas areas
  - Deep dark blue-black, modern tech aesthetic

- **`#1A1F2E`** - Secondary surface
  - Use for: Cards, panels, modals, header/footer
  - Slightly lighter dark surface for layered components

- **`#1C2832`** - Content background (gradient base)
  - Use for: Shaded content sections with subtle gradient
  - Blue-gray tint for visual hierarchy
  - Gradient: `linear-gradient(135deg, #1C2832 0%, #1A1F2E 100%)`

- **`#2A3142`** - Borders & dividers
  - Use for: Borders, dividers, subtle separators
  - Neutral dark gray for definition without harshness

---

## Accent Colors

### Interactive Elements
- **`#4A9EFF`** - Primary accent (highlight)
  - Use for: Primary buttons, important interactive elements
  - Bright blue for clear calls-to-action

- **`#3B7DD6`** - Darker accent (active state)
  - Use for: Hover states, active interactions
  - Deeper blue variant for interactive feedback

- **`#5DADE2`** - Light accent (links)
  - Use for: Links, secondary interactive elements
  - Lighter blue for text links and less prominent actions

---

## Text Colors

### Typography Hierarchy
- **`#E8EDF2`** - Primary text
  - Use for: Headings, body text, primary content
  - Light gray for strong readability on dark backgrounds

- **`#9BA8B8`** - Secondary text
  - Use for: Subtitles, descriptions, labels
  - Medium gray for supporting text

- **`#6B7A8F`** - Tertiary text
  - Use for: Metadata, timestamps, placeholder text
  - Darker gray for low-emphasis information

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
- **`#2D5940`** - Badge background (success variant)
  - Use for: Status badges, pills, tags with success/active state
  - Dark green background

- **`#6FB88A`** - Badge text (success variant)
  - Use for: Text on dark badge backgrounds
  - Light green for readability on dark badge backgrounds

---

## Usage Guidelines

### Do's
- Use `#0A0E1A` as the base for all pages (dark tech aesthetic)
- Layer `#1A1F2E` for cards and elevated components
- Use gradient `#1C2832` → `#1A1F2E` for content sections to create subtle depth
- Use bright accent colors (`#4A9EFF`) sparingly for important actions
- Maintain text hierarchy with the three text shades
- Use distinct status colors only for their intended purposes
- Keep overall aesthetic dark and professional

### Don'ts
- Don't use bright, saturated colors outside the accent/status palette
- Don't mix status colors for non-status purposes
- Don't use pure white (`#FFFFFF`) for backgrounds (use text colors instead)
- Don't create harsh borders - use `#2A3142` for subtle definition
- Don't overuse the primary accent - let the dark design breathe

### Accessibility
- Primary text (`#E8EDF2`) on main background (`#0A0E1A`) meets WCAG AA standards
- All status colors are distinguishable for colorblind users
- Accent colors provide sufficient contrast for interactive elements
- Text hierarchy ensures clear visual distinction

### Example Component Styling
```css
/* Page background */
background: #0A0E1A;

/* Header/Footer */
background: #1A1F2E;
border-bottom: 1px solid #2A3142;

/* Card with gradient content */
.card {
  background: #1A1F2E;
  border: 1px solid #2A3142;
  border-radius: 8px;
}

.card-content {
  background: linear-gradient(135deg, #1C2832 0%, #1A1F2E 100%);
  padding: 24px;
}

/* Button primary */
background: #4A9EFF;
color: #FFFFFF;

/* Button primary hover */
background: #3B7DD6;

/* Button secondary */
background: #1A1F2E;
border: 1px solid #2A3142;
color: #E8EDF2;

/* Button secondary hover */
background: #2A3142;

/* Link */
color: #5DADE2;

/* Link hover */
color: #4A9EFF;

/* Success button */
background: #5C8D6F;
color: #FFFFFF;

/* Badge/Pill */
background: #2D5940;
color: #6FB88A;
padding: 4px 12px;
border-radius: 9999px;
font-size: 12px;
text-transform: uppercase;
```

---

## Quick Reference

| Purpose | Color | Hex |
|---------|-------|-----|
| Main background | Dark blue-black | `#0A0E1A` |
| Secondary surface | Dark surface | `#1A1F2E` |
| Content background | Blue-gray tint | `#1C2832` |
| Border | Dark gray | `#2A3142` |
| Primary accent | Bright blue | `#4A9EFF` |
| Accent active | Deep blue | `#3B7DD6` |
| Links | Light blue | `#5DADE2` |
| Primary text | Light gray | `#E8EDF2` |
| Secondary text | Medium gray | `#9BA8B8` |
| Tertiary text | Dark gray | `#6B7A8F` |
| Success | Sage green | `#5C8D6F` |
| Error | Muted coral | `#C75B5B` |
| Warning | Muted amber | `#D4945C` |
| Info | Muted blue | `#6B8CAE` |
| Badge bg (success) | Dark green | `#2D5940` |
| Badge text (success) | Light green | `#6FB88A` |