# Bead: sase-az.2 — Representation targets and one copy-target registry

[Bead Pages](../README.md) / [sase-az](README.md) / sase-az.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-az.2` · **Size:** medium
**Created:** 2026-07-29 23:12:34 UTC · **Closed:** 2026-07-30 00:21:38 UTC
**Plan:** [202607/copy\_as\_palette.md](https://github.com/sase-org/sase--plans/blob/main/202607/copy_as_palette.md)

## Description

targets: collapse the duplicated copy-target label sets into one registry carrying footer labels, palette labels, categories, and plural forms; add uniform Markdown-link and metadata-JSON targets to the four Artifacts key groups (link also to changespecs); make marked-set output paste-ready per representation (newline-separated references, Markdown list, JSON array, skip-and-report partial failures); and size-cap the contents-shaped targets.

## Notes

[2026-07-30T00:21:38Z · sase-az.2] Implemented the shared copy-target registry, uniform Markdown-link and metadata-JSON targets, paste-ready marked-set forms with partial-failure counts, and bounded content-shaped copies; synchronized keymaps/default config/footer/help/docs/changelog. Verified 113 focused copy/help/delivery tests and full just test: 23,986 passed, 7 skipped. just check passes Python/Markdown formatting plus keep-sorted, ruff, mypy, pyscripts, changelog, Symvision, and toobig; its SASE validation is independently blocked by six existing missing prompt/reverse links for three shared 202607 plans (artifacts_files_subtab, at_reference_completion_menu, copy_as_palette).

[2026-07-30T00:22:28Z · sase-az.2] Verified focused copy-mode suite (113 passed), full suite (23,986 passed, 7 skipped), and repository-local formatting/lint gates; just check's remaining shared SDD prompt-link validation errors pre-existed these changes.

## Dependencies

- **Depends on:** [sase-az.1](sase-az.1.md) ✓
- **Blocks:** [sase-az.3](sase-az.3.md) ✓
