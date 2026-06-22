---
name: awesome-markdown
description: Create, improve, or audit GitHub-compatible Markdown and README files with rich presentation patterns. Use when Codex needs to build README.md files, Markdown documentation, or repo landing pages that use badges, Mermaid diagrams, alerts, tables, collapsible details, media, syntax-highlighted code, math, task lists, GeoJSON/TopoJSON/STL blocks, or lightweight HTML while preserving GitHub renderer compatibility and progressive disclosure.
---

# Awesome Markdown

## Core Workflow

1. Confirm the renderer. Default to GitHub README compatibility unless the user names another renderer such as GitLab, MkDocs, Docusaurus, VitePress, or a private docs system.
2. Put the most useful content first: project name, one-sentence purpose, badges, quick-start commands, and the primary visual.
3. Choose display patterns for the content, not for decoration. Use diagrams for flows, tables for comparison, collapsible sections for long details, alerts for important caveats, and media for real visual evidence.
4. Avoid README features that GitHub strips or blocks, including custom JavaScript, iframes, external CSS, and arbitrary interactive widgets.
5. Verify relative links, asset paths, code fences, and heading order before finishing.

## Progressive Resources

- Read `references/github-readme-patterns.md` when creating or enriching a README with concrete GitHub Markdown examples.
- Read `references/review-checklist.md` when auditing an existing README or doing a final quality pass.
- Reuse `assets/markdown-showcase.svg` or `assets/demo.gif` only when a repository needs small local sample media.

## Pattern Selection

- Architecture, process, data flow: prefer Mermaid. Use a rendered PNG/SVG when the diagram is too dense for Mermaid.
- Status, versions, license, coverage: use badges near the title.
- Warnings, prerequisites, compatibility notes: use GitHub alert blocks.
- Commands, config, APIs: use fenced code blocks with language tags.
- Long optional details: use `<details>` and `<summary>`.
- Results, UI, screenshots, demos: use local images, SVG, or GIF with concise alt text.
- Metrics, feature matrices, data schemas: use tables.
- Equations: use GitHub math blocks.
- Roadmaps and release readiness: use task lists.
- Locations or geometry: use `geojson`, `topojson`, or `stl` code blocks when GitHub rendering is useful.
- Small layout refinements: use limited HTML such as centered images, width attributes, and `<kbd>` tags.

## Output Rules

- Keep README examples copy-pasteable and renderer-safe.
- Prefer local assets over fragile hotlinks, except for common badge services.
- Include fallback text around diagrams and media so the README remains understandable if a renderer does not support a feature.
- Do not bury installation or first-run instructions inside collapsed sections.
- Keep the skill itself lean; put detailed Markdown snippets in references instead of expanding this file.
