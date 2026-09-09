# Bead: sase-yw.3.1 — Harden shared shortcut value validation

[Bead Pages](../README.md) / [sase-yw.3](sase-yw.3.md) / sase-yw.3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yw.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yw.land.md) · **Assignee:** `sase-yw.3.1` · **Size:** medium
**Created:** 2026-09-09 13:04:42 EDT · **Closed:** 2026-09-09 13:27:35 EDT
**Plan:** [202609/finish\_double\_star\_model\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_double_star_model_completion.md)

## Description

core_safety: reject catalog values that cannot safely become one inline model directive, add focused Rust/PyO3/LSP regressions, and land a verified sase-core revision for downstream integration.

## Notes

[2026-09-09T17:27:05Z · sase-yw.3.1] PROPOSED FOLLOW-UP: make sase-core check.sh export the selected uv Python libdir on LD_LIBRARY_PATH - default just check selected python3.14, but PyO3 tests could not load libpython3.14.so.1.0 until that libdir was added.

[2026-09-09T17:27:35Z · sase-yw.3.1] Verified cargo fmt; cargo test -p sase_core model_alias_shortcut; cargo test -p sase_core_py model_shortcut; cargo test -p sase_core_py model_alias_shortcut; cargo test -p sase_xprompt_lsp model_shortcut; cargo test -p sase_xprompt_lsp model_alias_shortcut; reran just check with uv python3.14 LIBDIR on LD_LIBRARY_PATH after default loader failure; final epic-symbols check reported no entries.

## Dependencies

- **Blocks:** [sase-yw.3.2](sase-yw.3.2.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yw.3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-yw.3.1/README.md) | [sase-yw.3.1](sase-yw.3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6b84036`](https://github.com/sase-org/sase-core/commit/6b84036d96ff5d5495ebaf9836440c64ee65b37d) | fix(editor): reject unsafe model shortcut values | [sase-yw.3.1](sase-yw.3.1.md) | 2026-09-09 13:30:44 EDT |
