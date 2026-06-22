# Awesome Markdown Skill

<p align="center">
  <img alt="GitHub Markdown" src="https://img.shields.io/badge/GitHub-Markdown-181717?logo=github">
  <img alt="Mermaid" src="https://img.shields.io/badge/Mermaid-diagrams-ff3670">
  <img alt="Codex Skill" src="https://img.shields.io/badge/Codex-Skill-0969da">
  <img alt="Renderer Safe" src="https://img.shields.io/badge/renderer-safe-2da44e">
</p>

<p align="center">
  <img src="awesome-markdown/assets/markdown-showcase.svg" alt="Awesome Markdown Skill preview" width="760">
</p>

`awesome-markdown` is a Codex skill for creating GitHub README files that are visually rich, renderer-safe, and easy to scan. This README is also a live showcase of the Markdown patterns the skill teaches.

> [!NOTE]
> The skill itself stays compact. Detailed patterns are loaded only when needed from `awesome-markdown/references/`.

> [!TIP]
> Use this repository as a starter when you want a README that demonstrates GitHub Markdown features directly on the repo front page.

> [!WARNING]
> GitHub README files do not run custom JavaScript, iframes, or external CSS. Use GitHub Pages or a docs framework for real interactivity.

## Skill Layout

| Path | Purpose |
|---|---|
| `awesome-markdown/SKILL.md` | Core trigger metadata and workflow |
| `awesome-markdown/references/github-readme-patterns.md` | On-demand snippets for rich GitHub Markdown |
| `awesome-markdown/references/review-checklist.md` | Final audit checklist |
| `awesome-markdown/assets/` | Small local media assets used by examples |

## Mermaid Flowchart

```mermaid
flowchart TD
    raw_data["S3 or local raw price data"] --> preprocess_step["Trading-hour filter and log-ratio preprocessing"];
    pg_postcleaning["Postgres postcleaning tables"] --> processed_series["Reference-compatible processed series"];
    preprocess_step --> audit_report["Preprocessing audit and build report"];
    causal_graph_node["Causal graph with tau lags"] --> parent_select["Direct parent selection"];
    parent_select --> pair_shards["Fixed-width causal NTP pairs"];
    audit_report --> processed_series;
    processed_series --> pair_shards;
    pair_shards --> token_stream["Patch-by-channel tokens"];
    token_stream --> metadata_embed["Role, channel, tau, and edge-weight embeddings"];
    metadata_embed --> decoder_stack["Causal decoder-only Transformer"];
    decoder_stack --> moe_block["Token-level sparse MoE"];
    moe_block --> forecast_heads["Mean, scale, quantile, and Student-t heads"];
    forecast_heads --> forecast_output["Point forecast, interval, samples, calibrated interval"];
```

## Collapsible Details

<details>
<summary>Show example README configuration</summary>

```yaml
renderer: github
sections:
  - badges
  - alerts
  - mermaid
  - tables
  - details
  - media
  - math
  - task_lists
compatibility:
  allow_html: limited
  allow_javascript: false
```

</details>

## Code Blocks

```bash
python train.py --config configs/forecast.yaml
```

```python
from pathlib import Path

readme = Path("README.md").read_text()
assert "`" * 3 + "mermaid" in readme
```

```sql
select symbol, avg(return_1m) as mean_return
from price_features
group by symbol;
```

## Math

Inline math works for compact notation such as $r_t$. Display math is useful for core formulas:

$$
r_t = \log(P_t) - \log(P_{t-1})
$$

$$
\hat{y}_{t+h} = \mu_\theta(x_{\le t}, h)
$$

## Media

SVG is useful for crisp architecture previews:

<p align="center">
  <img src="awesome-markdown/assets/markdown-showcase.svg" alt="Local SVG preview" width="620">
</p>

GIF is useful for short visual demos:

<p align="center">
  <img src="awesome-markdown/assets/demo.gif" alt="Animated README feature demo" width="420">
</p>

## Task List

- [x] Create the skill folder with `SKILL.md`
- [x] Move detailed examples into `references/`
- [x] Add local media assets
- [x] Demonstrate rich Markdown in the root README
- [ ] Push to `https://github.com/Minions-Land/Awesome-Markdown-Skill`

## GeoJSON Map

```geojson
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "name": "Shanghai"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [121.4737, 31.2304]
      }
    }
  ]
}
```

## TopoJSON Map

```topojson
{
  "type": "Topology",
  "objects": {
    "example": {
      "type": "GeometryCollection",
      "geometries": [
        {
          "type": "Point",
          "properties": {
            "name": "Shanghai"
          },
          "coordinates": [121.4737, 31.2304]
        }
      ]
    }
  },
  "arcs": []
}
```

## STL Preview

```stl
solid triangle
  facet normal 0 0 1
    outer loop
      vertex 0 0 0
      vertex 1 0 0
      vertex 0 1 0
    endloop
  endfacet
endsolid triangle
```

## Lightweight HTML

Use small HTML helpers when standard Markdown is not enough:

Press <kbd>Ctrl</kbd> + <kbd>C</kbd> to stop a local server.

<p align="center">
  <strong>Centered text and sized images work in GitHub README files.</strong>
</p>

## When README Is Not Enough

| Need | Better Tool |
|---|---|
| Full documentation site | MkDocs, Docusaurus, or VitePress |
| Interactive demos | GitHub Pages or Storybook |
| Notebook-style narrative | Jupyter Book |
| API reference publishing | Docs framework plus generated API docs |

## Install Locally

Copy or symlink `awesome-markdown/` into your Codex skills directory:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
ln -s "$(pwd)/awesome-markdown" "${CODEX_HOME:-$HOME/.codex}/skills/awesome-markdown"
```

Then invoke it with:

```text
Use $awesome-markdown to create a rich GitHub README for this repository.
```
