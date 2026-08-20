# Bead: sase-rj.2 — Complete contextual directive support in the xprompt LSP

[Bead Pages](../README.md) / [sase-rj](README.md) / sase-rj.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08s](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08s.md) · **Assignee:** `sase-rj.2` · **Size:** medium
**Created:** 2026-08-20 13:44:20 EDT · **Closed:** 2026-08-20 15:15:33 EDT
**Plan:** [202608/xprompt\_directive\_completion\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_directive_completion_parity.md)

## Description

external-editor-lsp: drive LSP names, snippets, keyword names, and contextual values from the shared contract, extending the existing cached editor catalog bridge for bead and identity targets without blocking editor requests.

## Notes

[2026-08-20T19:15:33Z · sase-rj.2] Verified LSP directive completion is driven from the shared sase-core contract: wait/id/clan keywords and values (including %wait bead= and kind-filtered clan/family/tribe), static time/int/bool/repeat examples, %model(...) alias keys and override values with self-reference suppression, UTF-16 mid-clause edits, helper-failure/mixed-schema degradation, and snippet vs non-snippet clients. Extended editor helper agent-catalog with optional bounded bead rows (backward-compatible). just check passed in sase-core; just check passed in sase (scoped lane escalated to the full suite). No leftover --epic-symbol entries.

[2026-08-20T19:16:41Z · sase-rj.2] Verified LSP directive completion is driven from the shared sase-core contract: wait/id/clan keywords and values (including %wait bead= and kind-filtered clan/family/tribe), static time/int/bool/repeat examples, %model(...) alias keys and override values with self-reference suppression, UTF-16 mid-clause edits, helper-failure/mixed-schema degradation, and snippet vs non-snippet clients. Extended editor helper agent-catalog with optional bounded bead rows (backward-compatible). just check passed in sase-core; just check passed in sase (scoped lane escalated to the full suite). No leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-rj.1](sase-rj.1.md) ✓ · ⧖ 2026-08-20
- **Blocks:** [sase-rj.4](sase-rj.4.md) ◐ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rj.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rj.2/README.md) | [sase-rj.2](sase-rj.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@16b1594`](https://github.com/sase-org/sase-core/commit/16b15944e4fb5fd73c8a8e22d25d2fc6944708a6) | feat(editor): drive xprompt LSP directive completion from the shared contract | [sase-rj.2](sase-rj.2.md) | 2026-08-20 15:18:20 EDT |
| sase | [`eadc738`](https://github.com/sase-org/sase/commit/eadc7389ccee0b7ab73cb803bf6644216ecdaa57) | feat(editor): include bounded bead rows in helper-bridge agent-catalog | [sase-rj.2](sase-rj.2.md) | 2026-08-20 15:22:36 EDT |
