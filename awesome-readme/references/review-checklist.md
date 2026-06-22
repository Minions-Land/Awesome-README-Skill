# README Component Review Checklist

Use this checklist before returning a GitHub README component library or component-heavy README.

## Component Fit

- Components are independent snippets, not a forced page layout.
- Every component can render inside GitHub README.md.
- Examples use simulated placeholder content unless real user data was provided.
- Unsupported widgets are identified as unsupported instead of presented as README components.

## GitHub Compatibility

- Code fences are balanced and labeled.
- Mermaid examples are original and not copied from user input.
- GeoJSON and TopoJSON snippets are valid JSON.
- Local image paths exist.
- HTML is limited to sanitized display helpers such as `<p>`, `<img>`, `<table>`, `<br>`, `<strong>`, `<a>`, and `<kbd>`.
- No JavaScript, iframes, external CSS, or hidden runtime dependency is required.

## Open Source Hygiene

- License badge matches the repository license.
- MIT license text is present when the repo claims MIT.
- Third-party examples are paraphrased or recreated, not copied verbatim.

## Readability

- Badge rows are not overloaded.
- Alerts are short and reserved for high-signal notes.
- Image and GIF alt text is meaningful.
- Collapsible sections hide optional detail only.
- Tables remain narrow enough to scan on GitHub.
