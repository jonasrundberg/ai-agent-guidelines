# AI Agent Guidelines

Personal library of guidelines, standards, and references for AI agents when building applications.

## Purpose

This repository contains markdown files that AI coding agents (VS Code, Cline, Windsurf, Cursor, etc.) can reference when building apps. The guidelines ensure consistency across projects and help agents understand preferred styles, patterns, and standards.

## Structure

```
├── colors/          # Color palettes and design systems
├── apis/            # API integration guidelines
├── python/          # Python coding standards
├── web/             # Web development guidelines
└── databases/       # Database schemas and standards
```

## Usage

### For AI Agents
Reference files directly from this repo when building apps:

```
"Use the color palette from my guidelines repo at colors/goals-palette.md"
"Follow the Python standards in python/style-guide.md"
```

### For Humans
Clone and reference locally, or link directly to files on GitHub.

## Access

This is a private repository. AI agents access it via the GitHub API using a personal access token stored as `GITHUB_AGENT_GUIDELINES_TOKEN`.

## Guidelines

### Adding New Guidelines
- Use clear, descriptive markdown
- Include examples where applicable
- Keep files focused on a single topic
- Use tables for quick reference

### File Naming
- Use kebab-case: `default-palette.md`
- Be descriptive: `postgres-schema-patterns.md`
- Avoid abbreviations unless universally understood

## Current Guidelines

### Colors
- [Default Color Palette](colors/default-palette.md) - UI color system

### Python
- [Python Standards](python/standards.md) - Python coding standards and best practices

### Web Development
- [Web Standards](web/standards.md) - HTML, CSS, JavaScript/TypeScript guidelines

## Contributing

This is a personal repo, but guidelines can be updated by AI agents when instructed:

```
"Update the error color in my guidelines to #FF5252"
"Add a new section to the Python guidelines about error handling"
```

## License

MIT License.