# Bead: sase-hp.2 — Every definition-load surface targets its xprompt

[Bead Pages](../README.md) / [sase-hp](README.md) / sase-hp.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vy/README.md) · **Assignee:** `sase-hp.2` · **Size:** medium
**Created:** 2026-08-08 15:52:11 EDT · **Closed:** 2026-08-08 17:11:55 EDT
**Plan:** [202608/xprompt\_target\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_target_mode.md)

## Description

surfaces: audit every path that loads an xprompt definition into the prompt stack, add the missing "edit definition here" action to the Select XPrompt panel, stop the external-editor round trip from silently dropping the target, and lock the audit down with an invariant test.

## Notes

[2026-08-08T21:11:55Z · sase-hp.2] Implemented Select XPrompt ctrl+o target loading, shared definition-load helper, editor-return target preservation, and target-surface audit coverage. Verified focused pytest affected suite passed (57 tests), Symvision passed, and just check passed with scoped lane escalating to the full suite.

[2026-08-08T21:13:22Z · sase-hp.2] Verified focused affected pytest suite (57 passed), just _lint-symvision, and just check (scoped lane escalated to the full suite and passed).

## Dependencies

- **Depends on:** [sase-hp.1](sase-hp.1.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-hp.6](sase-hp.6.md) ◐ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hp.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hp.2/README.md) | [sase-hp.2](sase-hp.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3dfbb8a`](https://github.com/sase-org/sase/commit/3dfbb8af32e2ed07161354a9e3b0225b068cd235) | feat(tui): edit selected xprompts in the prompt bar | [sase-hp.2](sase-hp.2.md) | 2026-08-08 17:14:30 EDT |
