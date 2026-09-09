# Bead: sase-ys.2 — Pin the core and prove ACE/LSP parity

[Bead Pages](../README.md) / [sase-ys](README.md) / sase-ys.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yf.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yf.land.w3.md) · **Assignee:** `sase-ys.2` · **Size:** medium
**Created:** 2026-09-09 06:57:15 EDT · **Closed:** 2026-09-09 08:25:30 EDT
**Plan:** [202609/lsp\_star\_model\_alias\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/lsp_star_model_alias_completion.md)

## Description

sase_star_alias_parity: ratchet to the landed core, make ACE consume the shared alias-only filter, add installed-binary parity tests, update editor documentation, and run repository verification.

## Notes

[2026-09-09T12:25:30Z · sase-ys.2] Pinned sase-core-revision.txt to cb669ec96526 (phase-1 star-alias contract). ACE now consumes filter_model_alias_shortcut_entries through the model-completion wire adapter; acceptance still revalidates via plan_model_alias_shortcut_edit. Did not bump pyproject sase-core-rs floor: PyPI latest is 0.32.53 and the new binding has no containing release tag yet (core-floor-probe blocked_unpublished). Verified: 119 focused tests (ACE widget/edit-plan, alias-only filter, catalog/payload identity, installed-binary ACE/LSP parity including trigger *, isIncomplete, preselect, filterText, UTF-16 edits, whitespace/Unicode/CRLF, no-match ownership, protected stars, missing/malformed catalogs, and unchanged %model: rows) plus just check (lint + scoped suite escalated for core-identity-changed). sase bead epic-symbols sase-ys.2 reported no entries. Docs updated in editor.md, xprompt.md, and ace.md; auto_directive_menu remains ACE-only.

## Dependencies

- **Depends on:** [sase-ys.1](sase-ys.1.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ys.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ys.2/README.md) | [sase-ys.2](sase-ys.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1852f09`](https://github.com/sase-org/sase/commit/1852f091ac3a4ebe8ac0cc25c6298d87d7edd3ee) | feat(xprompt): pin core and share ACE/LSP star-alias completion | [sase-ys.2](sase-ys.2.md) | 2026-09-09 08:26:55 EDT |
