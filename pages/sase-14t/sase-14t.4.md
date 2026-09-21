# Bead: sase-14t.4 — Harden the installed-swarm fan-out regression

[Bead Pages](../README.md) / [sase-14t](README.md) / sase-14t.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oi](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oi.md) · **Assignee:** `sase-14t.4` · **Size:** small
**Created:** 2026-09-20 20:51:35 EDT · **Closed:** 2026-09-20 22:51:26 EDT
**Plan:** [202609/research\_swarm\_providers.md](https://github.com/sase-org/sase--plans/blob/main/202609/research_swarm_providers.md)

## Description

fanout: make the fakey runner-slot test that plans the installed research swarm independent of machine-wide provider-disable state and extend it to cover the new opt-in providers.

## Notes

[2026-09-21T02:50:18Z · sase-14t.4] PROPOSED FOLLOW-UP: just check stays red on lint (symvision) for unrelated symbols (AxeDesiredState, bead_touch_glyph, lifecycle_journal_path, read_recent_successful_starts, ordered_bead_verb_chips); pre-existing on this checkout, none in the fan-out test path

[2026-09-21T02:51:26Z · sase-14t.4] Hardened test_installed_research_swarm fan-out test: plans under empty SASE_HOME (verified a seeded codex disable drops default plan 3->2 without it); added provider-gating coverage (grok/muse/both/codex=false/codex-disable) guarded on installed plugin support. Verified: full tests/fakey/test_runner_slots_e2e.py 10 passed, ruff check+format clean, epic-symbols empty.

## Dependencies

- **Depends on:** [sase-14t.2](sase-14t.2.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14t.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14t.4/README.md) | [sase-14t.4](sase-14t.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`44577fb`](https://github.com/sase-org/sase/commit/44577fb8f9b9222e2fb8956df9fb64a36c2e8d26) | test(runner-slots): harden installed-swarm fan-out test against provider-disable state | [sase-14t.4](sase-14t.4.md) | 2026-09-20 22:53:37 EDT |
