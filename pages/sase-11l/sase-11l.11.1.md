# Bead: sase-11l.11.1 — Unify hold selectors and effective tribe identity

[Bead Pages](../README.md) / [sase-11l.11](sase-11l.11.md) / sase-11l.11.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.land.md) · **Assignee:** `sase-11l.11.1` · **Size:** medium
**Created:** 2026-09-18 18:08:41 EDT · **Closed:** 2026-09-18 21:29:01 EDT
**Plan:** [202609/hold\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_landing_repairs.md)

## Description

selector-parity: share Rust selector expansion across CLI and directives, integrate stored and contextual tribe membership into admission and display, and correct required CLI operands.

## Notes

[2026-09-19T01:29:01Z · sase-11l.11.1--3] Verified selector-parity: CLI and %hold share Rust hold_fields_to_selectors (families/clans/workflows plus stored/contextual job-vs-chop tribe identity); admission and TUI capacity records overlay posthoc tribes and clan-generation precedence; matcher uses tribes membership; CLI create takes positional SELECTOR names/@tribes, show requires ARMER_KEY, release takes optional ARMER_KEY with -n/-t/-k aliases. Guarded AXE percent-copy against None keys; PyO3 binding test passes identity arg. sase-core just check and sase just check both passed (monitor arvyevy8gm1g, exit 0). Pin bump deferred until the unpublished core commit is released.

## Dependencies

- **Blocks:** [sase-11l.11.2](sase-11l.11.2.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.11.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.11.1.md) | [sase-11l.11.1](sase-11l.11.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0e4cfe9`](https://github.com/sase-org/sase/commit/0e4cfe92cb9a0f007de7e44149c47e4495686cab) | feat(hold): unify CLI and directive selector parity | [sase-11l.11.1](sase-11l.11.1.md) | 2026-09-18 22:41:35 EDT |
| sase-core | [`sase-core@7e95d3f`](https://github.com/sase-org/sase-core/commit/7e95d3fe272beccc484cfa1270cdb41e55ed2c43) | feat(hold): unify CLI and directive selector identity | [sase-11l.11.1](sase-11l.11.1.md) | 2026-09-18 22:47:06 EDT |
