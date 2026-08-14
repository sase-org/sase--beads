# Bead: sase-m4.4 — Reconcile ACE visual behavior and snapshots

[Bead Pages](../README.md) / [sase-m4](README.md) / sase-m4.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01o.md) · **Assignee:** `sase-m4.4` · **Size:** medium
**Created:** 2026-08-14 14:20:22 EDT · **Closed:** 2026-08-14 15:05:19 EDT
**Plan:** [202608/stabilize\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202608/stabilize_github_actions.md)

## Description

visual-baselines: classify visual diffs, fix nondeterministic state, and accept only intentional golden changes.

## Notes

[2026-08-14T19:05:19Z · sase-m4.4] Classified CI PNG failures: 325/387 were the default ⚑1 ✉18 badge with ✉ as .notdef because some resvg-py wheels ignore font_dirs; remaining outliers were the same Noto/DejaVu fallback (⚠, ✏️, ⚡). render_svg_to_png now passes font_files so bundled faces load on every wheel. Visual fixtures pin shipped notification_tabs and wait for the exact ⚑1 ✉18 badge. Regenerated 415 goldens to that hermetic rendering. just test-visual passed twice (676 passed, 1 skipped). just check passed.

[2026-08-14T19:08:13Z · sase-m4.4] Classified CI PNG failures: 325/387 were the default ⚑1 ✉18 badge with ✉ as .notdef because some resvg-py wheels ignore font_dirs; remaining outliers were the same Noto/DejaVu fallback (⚠, ✏️, ⚡). render_svg_to_png now passes font_files so bundled faces load on every wheel. Visual fixtures pin shipped notification_tabs and wait for the exact ⚑1 ✉18 badge. Regenerated 415 goldens to that hermetic rendering. just test-visual passed twice (676 passed, 1 skipped). just check passed.

## Dependencies

- **Blocks:** [sase-m4.6](sase-m4.6.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m4.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m4.4/README.md) | [sase-m4.4](sase-m4.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bc040fe`](https://github.com/sase-org/sase/commit/bc040fee5d4a7cb2ad98c104587fa42499d9e089) | test: load bundled ACE visual fonts via font\_files | [sase-m4.4](sase-m4.4.md) | 2026-08-14 15:08:50 EDT |
