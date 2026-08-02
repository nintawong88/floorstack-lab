# CLAUDE.md

Guidance for Claude Code working in this repo.

## What this is

Static HTML mockups/portfolio for Chawin Intawong, pushed to
`github.com/nintawong88/floorstack-lab`. No build step — open files
directly in a browser or serve as static assets.

## Files

| File | Purpose |
|---|---|
| `index.html` | Homepage — Chawin Intawong personal/consulting site (supply chain & logistics executive bio). Also the ChawinConsulting identity; FloorStack was merged into it as one brand rather than kept separate. |
| `floorstack.html` | FloorStack build log — live status/journal for the FloorStack product suite. |
| `floorstack-wms.html` | FloorStack WMS — product demo. Before/after warehouse (floor-stack vs 5-level racking), count-method scenes, Switch Scan goods receive/putaway app mockup, plain-language ask/quick-command mockup. Links out to the count module. |
| `floorstack-count.html` | FloorStack WMS · Count module demo (zone-level count control center) — not a separate product, linked from `floorstack-wms.html`. |
| `floorstack-procure.html` | FloorStack Procure — product demo (floor-stack procurement UI, bilingual EN/TH). |
| `chawinconsulting-site/` | **Separate nested git repo** (own `.git`), untracked by this repo. Zero-dependency Node static server + Railway deploy config for a standalone version of the portfolio site. Not yet pushed to GitHub or linked to Railway — see its own `README.md`. |

## Conventions

- Each HTML file is self-contained: CSS and JS inlined, Google Fonts via
  `<link>`, no external JS framework.
- Shared design tokens (CSS custom properties) repeat per-file rather than
  being factored out — e.g. `--ink`, `--navy`, `--accent` in `index.html`
  vs `--paper`, `--card`, `--ink` in the `floorstack-*` demo files. Keep
  edits local to the file you're touching; don't introduce a shared
  stylesheet unless asked.
- No test suite, no package manager, no dependencies to install.

## `chawinconsulting-site/` subproject

Independent git repo living inside this one (not a submodule, just an
untracked directory — `git status` in the parent shows it as untracked,
not embedded). Deploy instructions are in
[chawinconsulting-site/README.md](chawinconsulting-site/README.md):
GitHub → Railway auto-deploy, or `railway up` from the CLI. Currently has
one local commit only; not pushed anywhere.
