---
name: awesome-readme
description: Create, improve, or audit beautiful GitHub README component libraries and README snippets. Use when Codex needs renderer-safe GitHub README components such as badges, hero images, link bars, alerts, Mermaid diagrams, tables, collapsible details, media, code blocks, math, task lists, sponsor/logo grids, keyboard tags, anchors, GitHub metadata cards, GeoJSON/TopoJSON/STL previews, and limited HTML. Focus on components that render inside GitHub README.md, not full documentation-site layout systems.
---

# Awesome README

## Scope

Provide reusable GitHub README components. Do not design a whole documentation flow unless the user asks for it.

Prioritize components that render directly in GitHub README files:

- Badges and status chips
- Hero banners, local SVG/PNG/GIF media, screenshots, and logo strips
- GitHub alert blocks
- Mermaid diagrams
- Markdown tables and HTML table grids
- Collapsible `<details>` sections
- Syntax-highlighted code blocks, diff blocks, and terminal blocks
- Math blocks
- Task lists
- Keyboard tags and anchor links
- GeoJSON, TopoJSON, and ASCII STL code blocks
- Limited sanitized HTML for alignment, sizing, and compact grids

## Workflow

1. Confirm the target renderer. Default to GitHub README compatibility.
2. Select components from `references/component-library.md` rather than inventing unsupported widgets.
3. Use simulated placeholder examples unless the user provides real product, brand, or metric data.
4. Keep examples component-level. Avoid turning the answer into a full site, a landing page, or a docs framework.
5. Run the checks in `references/review-checklist.md` before finishing when editing a repository.

## Progressive Resources

- Read `references/component-library.md` when building or expanding README components.
- Read `references/review-checklist.md` before finalizing a README or reviewing one.
- Reuse `assets/readme-components.svg` or `assets/demo.gif` only when a repo needs local sample media.

## Compatibility Rules

- Do not rely on JavaScript, iframes, external CSS, or runtime widgets in README.md.
- Prefer local assets for screenshots, hero art, diagrams, and GIFs.
- Use external URLs mainly for stable badge services or GitHub-native links.
- Include clear alt text for images.
- Keep long optional examples in collapsible sections, but keep key install or usage snippets visible.
