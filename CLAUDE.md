# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

Static GitHub Pages website hosted at **azrousof.fr** (see `CNAME`). No build system, no framework, no package manager — pure HTML/CSS. Deployment is automatic on push to `main`.

To preview locally, open any HTML file directly in a browser, or use a simple server:
```bash
python3 -m http.server 8080
```

## Architecture

```
index.html                        # Homepage — app catalog for Azrousof
ft/
  footbalance.html                # FootBalance app landing page
  footbalance-tutorial-{lang}.html  # Tutorial pages (ar, de, en, es, fr, it, pt)
CNAME                             # azrousof.fr
```

### Design system

All pages share a consistent dark theme defined via CSS custom properties:

| Variable | Value | Role |
|---|---|---|
| `--navy` | `#0D1B2E` | Page background |
| `--navy-card` | `#1C2D42` | Card/section background |
| `--gold` / `--gold-light` | `#C9952A` / `#E8B84B` | Primary accent |
| `--blue-accent` | `#3B82F6` | Secondary accent |
| `--crimson` | `#C0243A` | Danger/highlight |
| `--text` | `#E8EDF4` | Body text |
| `--text-muted` | `#7A90A8` | Secondary text |

Fonts loaded from Google Fonts: **Bebas Neue** (display/titles) + **DM Sans** (body).

### Tutorial pages

The 7 `footbalance-tutorial-{lang}.html` files are large (~987 KB each) and fully self-contained (inline SVG data URIs, no external assets beyond Google Fonts). When editing one, the same change usually needs to be applied to all language variants.
