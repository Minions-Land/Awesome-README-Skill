# Research README flow

Use this flow when the user wants a *whole* README (not single components), especially for a
research codebase, ML model, benchmark or tool. Build each block from the components in
`component-library.md`; this file decides what goes in, in which order, and what counts as evidence.


A README is the landing page of a project. In about thirty seconds a reader should know what the
project is, why it matters, whether it works (numbers), and how to run it. Beauty comes from
structure and restraint, not decoration. Every claim should be traceable to something in the repo.

## Workflow

1. **Read before writing.** Skim the code layout, configs, scripts, tests, result files and any
   existing README or docs. Collect real facts: parameter counts, dataset sizes, metric values,
   commands that actually exist, dependency versions. Note where each number came from.
2. **Pick the reader.** A research codebase serves collaborators and reviewers (results, method,
   reproduction). A tool serves users (install, usage, API). The answer decides section order.
3. **Draft the skeleton** from `assets/research-readme-template.md`. Keep the section order unless the reader
   needs something else first.
4. **Fill it with evidence.** Tables over prose for numbers; one diagram for the architecture or
   data flow; commands copied from scripts that exist; paths that exist.
5. **Verify.** Run through the checklist below. Re-check every number against its source file.
   Every link and path must resolve, and every command must match a real script or entry point.
6. **Bilingual pair (when asked or when the team reads Chinese).** Write `README.md` (English) and
   `README_zh-CN.md`, with a language switch line at the top of both. Translate meaning, not word
   order: plain, natural Chinese; keep technical terms (macro-F1, MoE, FlashAttention) as is.

## Section order (default for research code)

| Section | What it holds | Why here |
|---|---|---|
| Title + centered one-line tagline | What it is, in plain words | The 5-second answer |
| Nav links · language switch | Anchors to the sections below | Long READMEs need a map |
| Badges (4–6) | Language, framework, hardware, size, data scale, status | Facts at a glance — only true ones |
| Overview (1 paragraph + small table) | The idea; what goes in and comes out | Context before numbers |
| Results | One table: method rows × metric columns, best in bold, baselines included | The proof, before the reader leaves |
| Architecture | One mermaid diagram + a component table | How it works, scannable |
| Engineering / infrastructure (if notable) | Change → measured effect table | Shows rigour, credits the work |
| Data | Dataset table: name, size, what it is, how it was built | Reproducibility |
| Quick start | Environment line, then copy-paste commands with comments | Lets someone run it |
| Evaluation / usage | Commands for the main workflows | The second thing people try |
| Repository layout | A short annotated tree | Orientation for contributors |
| Acknowledgements | Libraries and ideas built on, with links; license | Honest credit |

For a tool or library, move Quick start and Usage above Results, and add an API section.

## Writing rules (and why)

- **Numbers carry the argument.** A results table with baselines persuades; adjectives
  ("state-of-the-art", "blazing fast") do not, and invite scepticism. State the setting
  (data split, steps, hardware) next to the numbers so they can be compared fairly.
- **Report the uncomfortable result too.** If one metric is worse than a baseline, show it and
  say what is being done about it. Readers trust a README that admits limits.
- **Badges are facts, not decoration.** Use shields.io static badges for values you verified
  (`https://img.shields.io/badge/<label>-<value>-<hex>`). Never add CI, coverage or download
  badges that do not exist. Four to six badges; more turns into noise.
- **One diagram, not five.** Mermaid renders on GitHub; keep node labels short, use `<br/>` for a
  second line, and show the data flow left to right. See `references/patterns.md`.
- **Tables for anything with columns.** Right-align numbers, bold the best per column, keep units
  in the header.
- **Commands must run.** Copy them from existing scripts or entry points; one command per line
  with a short trailing comment; say the environment (OS, Python, GPU, package manager) first.
- **Callouts sparingly.** GitHub alerts (`> [!NOTE]`, `> [!IMPORTANT]`, `> [!WARNING]`) for one or
  two facts the reader must not miss (e.g. internal paths, a data caveat).
- **No walls of text.** Paragraphs of 2–4 sentences; bullets for lists of 3+ items; headers as
  short noun phrases.
- **Paths as links.** Relative links to files and folders (`[data_build/](data_build/)`) let the
  reader click through on GitHub.
- **Secrets and private details stay out.** No tokens, passwords, internal IPs or personal data.
  Mention internal paths only to explain them, in a NOTE.

## Checklist before handing over

- [ ] Tagline says what it is without jargon
- [ ] Every number matches a file in the repo (or a cited paper), with its setting stated
- [ ] Results table includes baselines and is readable on a phone (≤ 6 numeric columns)
- [ ] Diagram renders (valid mermaid) and matches the code
- [ ] Every command and path exists; anchors in the nav resolve
- [ ] Badges are all true; none for things that do not exist
- [ ] Limits and open problems are stated
- [ ] Bilingual pair (if any) carries the same numbers and links
- [ ] No secrets, tokens or personal data

## Common mistakes

| Mistake | Fix |
|---|---|
| Marketing adjectives with no numbers | A results table with baselines and the setting |
| Badges for CI / coverage that do not exist | Only static badges for verified facts |
| Commands that were never run | Copy from scripts/entry points; test them |
| Five diagrams, none matching the code | One diagram that matches the code |
| Wall-of-text overview | One paragraph + one table |
| Numbers that differ between English and Chinese versions | Edit both in the same change |
| Hiding the weak metric | Show it and say what is next |
