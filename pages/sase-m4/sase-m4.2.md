# Bead: sase-m4.2 — Repair strict PDF documentation export

[Bead Pages](../README.md) / [sase-m4](README.md) / sase-m4.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01o.md) · **Assignee:** `sase-m4.2` · **Size:** medium
**Created:** 2026-08-14 14:20:04 EDT · **Closed:** 2026-08-14 15:08:58 EDT
**Plan:** [202608/stabilize\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202608/stabilize_github_actions.md)

## Description

docs-pdf: identify the browser 404 requests and correct their documentation source without weakening strict export.

## Notes

[2026-08-14T19:07:31Z · sase-m4.2] PROPOSED FOLLOW-UP: just check Rich substring tests fail under FORCE_COLOR — agent/CI FORCE_COLOR makes CLI/TUI tests assert plain strings that Rich emits with ANSI (e.g. test_cli_work_from_plan_preview, plugins pane); they pass with NO_COLOR=1 and are unrelated to docs-pdf.

[2026-08-14T19:08:58Z · sase-m4.2] Verified exact browser 404 URLs and fixed them at origin without disabling strict export. Last green docs-pdf was 2aff0a03; first fail 465d81ec changed only markdown prose (no local assets). Exporter 6.2.0 logs Chrome console text without the URL; a file:// Playwright probe matching the printer captured: https://fonts.googleapis.com/css?family=Roboto:300,300i,400,400i,700,700i%7CRoboto+Mono:400,400i,700,700i&display=fallback plus fonts.gstatic.com Roboto/Roboto Mono woff2 files (Material remote fonts). CI phrases those as "Failed to load resource: the server responded with a status of 404 ()" on many pages. Set theme.font: false in mkdocs-pdf.yml only (site still uses Google Fonts). After that, just docs-pdf-check cleared browser errors but the handbook was 22.6 MiB over the 22 MiB guard; postprocess now re-encodes shared RGB PNGs once (quality 95) and compresses streams. Re-ran just docs-check (strict site build) and just docs-pdf-check: no browser errors, 44 chapter outlines, 8 optimized images, 690 pages, 15.3 MiB. Added tests/test_docs_pdf_tools.py for font:false, --strict recipe, and image-optimization. just check lint gates passed; scoped tests escalated (Justfile/pyproject/uv.lock) and 118 CLI/TUI substring failures reproduced only under FORCE_COLOR (pass with NO_COLOR=1) — recorded as PROPOSED FOLLOW-UP, not caused by this phase.

[2026-08-14T19:10:32Z · sase-m4.2] Verified exact browser 404 URLs (fonts.googleapis.com Roboto CSS and fonts.gstatic.com woff2 files) and fixed them at origin without disabling --strict export: theme.font: false in mkdocs-pdf.yml only. After 404s cleared, just docs-pdf-check hit the 22 MiB guard at 22.6 MiB; postprocess now re-encodes shared RGB PNGs once (quality 95) and compresses streams. Re-ran just docs-check and just docs-pdf-check: no browser errors, 44 chapter outlines, 8 optimized images, 690 pages, 15.3 MiB. Added tests/test_docs_pdf_tools.py. Lint gates passed; FORCE_COLOR CLI/TUI substring failures recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-m4.6](sase-m4.6.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m4.2/README.md) | [sase-m4.2](sase-m4.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e4baf07`](https://github.com/sase-org/sase/commit/e4baf07717f5a9cb836316b8db5416d1af3f8096) | fix(docs): stop strict PDF export from fetching remote Google Fonts | [sase-m4.2](sase-m4.2.md) | 2026-08-14 15:11:11 EDT |
