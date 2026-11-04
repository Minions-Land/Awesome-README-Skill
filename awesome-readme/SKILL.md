---
name: awesome-readme
description: Create, improve, or audit beautiful GitHub README component libraries and README snippets. Use when Codex needs renderer-safe GitHub README components such as badges, hero images, link bars, alerts, Mermaid diagrams, tables, collapsible details, media, code blocks, MDX snippets as displayed examples, math, task lists, sponsor/logo grids, keyboard tags, anchors, GitHub metadata cards, GeoJSON/TopoJSON/STL previews, and limited HTML. Focus on components that render inside GitHub README.md, not full documentation-site layout systems. Also use it to write or restructure a whole evidence-backed README for a research codebase, ML model, benchmark or tool (results table with baselines, architecture diagram, runnable quick start, optional English + 简体中文 pair).
---

# Awesome README

## Scope

Provide reusable GitHub README components. Do not design a whole documentation flow unless the user asks for it; when they do, follow `references/research-readme-flow.md`.

Prioritize components that render directly in GitHub README files:

- Badges and status chips
- Hero banners, local SVG/PNG/GIF media, screenshots, and logo strips
- GitHub alert blocks
- Mermaid diagrams
- Markdown tables and HTML table grids
- Collapsible `<details>` sections
- Syntax-highlighted code blocks, diff blocks, terminal blocks, and displayed MDX snippets
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
- Read `references/research-readme-flow.md` when asked for a whole README (research code, models, tools): reading the repo for evidence, section order, writing rules, bilingual pairs, checklist.
- Start a whole README from `assets/research-readme-template.md`.
- Reuse `assets/readme-components.svg` or `assets/demo.gif` only when a repo needs local sample media.

## Compatibility Rules

- Do not rely on JavaScript, iframes, external CSS, or runtime widgets in README.md.
- Treat MDX as a displayed code example in README.md. Do not imply that JSX components execute inside GitHub README rendering.
- Prefer local assets for screenshots, hero art, diagrams, and GIFs.
- Use external URLs mainly for stable badge services or GitHub-native links.
- Include clear alt text for images.
- Keep long optional examples in collapsible sections, but keep key install or usage snippets visible.
