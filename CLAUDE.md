# AI Agent Instructions for Guidelines Repository

## Repository Purpose

This is a **meta-repository** containing markdown guidelines that AI coding agents reference when building applications. You are working on the guidelines themselves, not consuming them.

## Architecture

```
colors/          # Color palettes (e.g., default-palette.md)
python/          # Python coding standards (e.g., standards.md)
web/             # Web development standards and templates
  standards.md   # Web development guidelines
  default-template.html      # Standard template with light/dark mode
  light-template.html        # Light theme only template
  sidepanel-template.html    # Template with sidebar navigation
  examples/      # Example implementations
apis/            # API integration guidelines (empty - future)
databases/       # Database schemas and patterns (empty - future)
README.md        # Main entry point with usage examples
```

Each guideline file follows a consistent structure:
- **Overview** section explaining purpose
- **Clear sections** with practical examples
- **Do's/Don'ts** lists for quick reference
- **Quick Reference** table at the end
- Code examples using proper markdown fenced blocks

## Key Patterns

### Guideline File Format (see `colors/default-palette.md`)
```markdown
# Title

## Overview
Brief description of what this guideline covers

---

## Major Section

### Subsection
- **Bold key points** with explanations
- Use for: Specific use cases

### Examples
\```language
// Code examples with clear comments
\```

### Do's
- Specific actionable items
- Reference actual values from the guideline

### Don'ts
- Concrete anti-patterns to avoid
- Explain why, not just what

---

## Quick Reference

| Purpose | Description | Value |
|---------|-------------|-------|
| Item    | What it is  | `#HEX` or concrete value |
```

### Color Palette Structure
The color palette supports **both light and dark themes** with adaptive colors:
- **Light theme**: Light backgrounds (`#F5F7FA`) with dark text (`#1A1F2E`)
- **Dark theme**: Dark backgrounds (`#0A0E1A`) with light text (`#E8EDF2`)
- **Shared colors**: Accent colors (`#5A7A99`, `#4D6A85`, `#6B8CAE`) work in both themes
- All colors include hex codes, Tailwind equivalents, usage descriptions, and component examples
- Templates include automatic OS theme detection with manual toggle override

### Python Standards
- PEP 8 with 88-character line length (Black standard)
- **Mandatory type hints** for all function signatures
- Google-style docstrings with Args/Returns/Raises sections
- Custom exception classes for domain errors

### Web Standards
- **Tailwind CSS** for all styling (CDN setup with inline config)
- **Light/Dark mode support** using Tailwind's `dark:` classes with `darkMode: 'class'`
- **OS theme detection** with `prefers-color-scheme` media query
- **Desktop-first** responsive design (prioritize full monitors over mobile)
- Apps must work on both desktop and mobile devices
- Vanilla JavaScript (ES6+) with async/await
- Semantic HTML5 elements mandatory
- Theme persistence via `localStorage`

## Common Workflows

### Adding New Guidelines
1. Create markdown file in appropriate folder: `<category>/<name>.md`
2. Follow the established format structure (see patterns above)
3. Include practical code examples (not pseudocode)
4. Add entry to README.md under "Current Guidelines" section
5. Commit with descriptive message: `"Add <category> guidelines for <topic>"`

### Updating Existing Guidelines
1. Read the full file to understand current structure
2. Maintain consistency with existing Do's/Don'ts format
3. Update Quick Reference table if values change
4. Update code examples to reflect changes
5. Commit message: `"Update <category> guidelines - <specific change>"`

### Example: Adding a New Color
```markdown
- **`#HEX`** - Descriptive name
  - Use for: Specific UI elements, states, contexts
  - Brief explanation of when/why to use this color
```

## Repository Conventions

### File Naming
- Use `kebab-case`: `default-palette.md`, not `DefaultPalette.md`
- Be descriptive: `postgres-schema-patterns.md`, not `db.md`
- Category name in folder, specific topic in filename

### Markdown Style
- Use `---` horizontal rules between major sections
- Use `**bold**` for key terms and values (hex codes, config names)
- Use fenced code blocks with language identifiers: ` ```python `, ` ```css `
- Use tables for quick reference (consistent columns across files)

### Git Workflow
- This is a **private repository** with **Claude GitHub App** installed
- Also accessible via `GITHUB_AGENT_GUIDELINES_TOKEN` for legacy integrations
- Commit directly to `main` branch (no PR process)
- Use descriptive commit messages explaining the "what" and "why"
- Push immediately after committing

## Critical Context

**This repository is FOR AI agents, not BY users**. When instructed to "add Python error handling guidelines," you are:
- ✅ Adding/updating markdown documentation in `python/standards.md`
- ❌ NOT writing actual Python code to handle errors

**Guidelines should be prescriptive**, not aspirational. Document:
- ✅ "Use Google-style docstrings" with concrete examples
- ❌ NOT "Consider documenting your code"

## Repository Access

AI agents can access this private repository through two methods:

1. **Claude GitHub App** - Primary integration for Claude-based agents with full repository access
2. **`GITHUB_AGENT_GUIDELINES_TOKEN`** - Environment variable for legacy integrations and read operations when building other projects

## Examples From This Codebase

**Good guideline** (from `python/standards.md`):
```markdown
### Do's
- Always type function parameters and return values
- Use `Optional[T]` for nullable values
- Use `List[T]`, `Dict[K, V]` instead of `list`, `dict`
```

**Good color specification** (from `colors/default-palette.md`):
```markdown
- **`#F5F7FA`** - Main background (light mode)
  - Use for: Page backgrounds, main canvas areas
  - Soft off-white with subtle blue-gray tint
  - Tailwind equivalent: `bg-gray-50`

- **`#5A7A99`** - Primary accent (both themes)
  - Use for: Primary buttons, important interactive elements
  - Muted blue-gray for professional calls-to-action
  - Works in both light and dark modes
```

**README references** show how external agents use these guidelines:
```markdown
"Use the color palette from my guidelines repo at colors/default-palette.md"
"Follow the Python standards in python/style-guide.md"
```
