# Bead: sase-rj.4 — Lock runtime, widget, and LSP parity with tests and documentation

[Bead Pages](../README.md) / [sase-rj](README.md) / sase-rj.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08s](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08s.md) · **Assignee:** `sase-rj.4` · **Size:** medium
**Created:** 2026-08-20 13:44:21 EDT · **Closed:** 2026-08-21 05:36:37 EDT
**Plan:** [202608/xprompt\_directive\_completion\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_directive_completion_parity.md)

## Description

parity-verification: add exhaustive contract and interaction coverage for every directive and keyword, verify matching ACE/LSP behavior including failure degradation and UTF-16 edits, and document the complete completion matrix.

## Notes

[2026-08-21T09:35:44Z · sase-rj.4] PROPOSED FOLLOW-UP: closed flag bead blocks check — feature-flag lint reports closed flag bead sase-rk still has surviving admin_center_config_hub definition.

[2026-08-21T09:36:37Z · sase-rj.4] Implemented directive completion parity coverage and docs; fixed ACE %model alias self-reference omission to match LSP. Verified: just test tests/test_xprompt_directive_completion_parity.py passed (21 tests); just check passed formatting, keep-sorted, ruff, and mypy, then failed on unrelated feature-flag lint for closed flag bead sase-rk/admin_center_config_hub; sase bead epic-symbols sase-rj.4 reported no entries.

[2026-08-21T09:38:18Z · sase-rj.4] Verified directive completion parity with focused pytest; epic-symbols reported no entries; just check reached an unrelated closed-flag lint already recorded as proposed follow-up.

## Dependencies

- **Depends on:** [sase-rj.2](sase-rj.2.md) ✓ · ⧖ 2026-08-20
- **Depends on:** [sase-rj.3](sase-rj.3.md) ✓ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rj.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rj.4/README.md) | [sase-rj.4](sase-rj.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0e80b9f`](https://github.com/sase-org/sase/commit/0e80b9f96a6b4c599be747818e39894ff4319ef5) | fix(ace): omit model alias self references from completion | [sase-rj.4](sase-rj.4.md) | 2026-08-21 05:39:34 EDT |
