# AI Agent Instructions for Guidelines Repository

## Repository Purpose

This is a **meta-repository** containing markdown guidelines that AI coding agents reference when building applications.

## Architecture

```
colors/                        # Color palettes
  default-palette.md           # Light/dark adaptive color system
python/                        # Python coding standards
  standards.md                 # Python style guide with type hints
web/                           # Web development standards and templates
  standards.md                 # Web development guidelines
  default-template.html        # Standard template with light/dark mode toggle
  light-template.html          # Light theme only template
  sidepanel-template.html      # Template with sidebar navigation
  examples/                    # Example implementations
apis/                          # API integration guidelines (future)
databases/                     # Database schemas and patterns (future)
```

---

## Instructions for AI Agents in IDEs

Copy and paste these instructions to agents when building applications.

### 🎨 Web Development

**For building web applications with proper styling:**

```
Read https://github.com/jonasrundberg/ai-agent-guidelines/blob/main/web/standards.md for coding standards and best practices.
Read https://github.com/jonasrundberg/ai-agent-guidelines/blob/main/colors/default-palette.md to understand the adaptive light/dark color system.
Use https://github.com/jonasrundberg/ai-agent-guidelines/blob/main/web/default-template.html or https://github.com/jonasrundberg/ai-agent-guidelines/blob/main/web/sidepanel-template.html as your base template.
Follow the exact CSS classes, HTML structure, Tailwind & Heroicons configuration, and component patterns from these templates.
All pages must support both light and dark modes with automatic OS theme detection.
Use Tailwind CSS with the custom color extensions defined in the templates.
Use Heroicons for icons.
```

**Key Features to Include:**
- Light/dark mode toggle with sun/moon icons
- OS theme preference detection (`prefers-color-scheme`)
- Theme persistence via `localStorage`
- Tailwind CSS with `darkMode: 'class'` configuration
- Responsive design (desktop-first, mobile-compatible)
- Consistent color palette across both themes

**Template Selection:**
- Use `default-template.html` (https://github.com/jonasrundberg/ai-agent-guidelines/blob/main/web/default-template.html) for standard full-width layouts
- Use `sidepanel-template.html` (https://github.com/jonasrundberg/ai-agent-guidelines/blob/main/web/sidepanel-template.html) for apps with persistent navigation sidebar


### 🐍 Python Development

**For building Python applications:**

```
Read https://github.com/jonasrundberg/ai-agent-guidelines/blob/main/python/standards.md for coding standards and best practices.
Follow PEP 8 with 88-character line length (Black standard).
Use mandatory type hints for all function signatures.
Write Google-style docstrings with Args/Returns/Raises sections.
Create custom exception classes for domain-specific errors.
```

--- 