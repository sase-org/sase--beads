# Bead: sase-1aa.5.3 — Prove a synthetic manifest update across model surfaces

[Bead Pages](../README.md) / [sase-1aa.5](sase-1aa.5.md) / sase-1aa.5.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1aa.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aa.land.md) · **Assignee:** `sase-1aa.5.3` · **Size:** medium
**Created:** 2026-09-26 08:43:43 EDT · **Closed:** 2026-09-26 10:56:54 EDT
**Plan:** [202609/finish\_model\_catalog\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_model_catalog_landing.md)

## Description

exercise_manifest: demonstrate that one manifest edit reaches routing, alias resolution, TUI picker/completion, and the LSP payload, with generated docs as the only derived file.

## Notes

[2026-09-26T14:56:07Z · sase-1aa.5.3--1] PROPOSED FOLLOW-UP: just check symvision gate fails on stale sase-19x.4 --epic-symbol entries (phase_card_block, block_meta_for_session_shell, session_reply_heading) left in Justfile after that phase closed; already tracked by task bead sase-o7; failure is in src/sase scan and reproduces without this phase untracked tests/ file

[2026-09-26T14:56:25Z · sase-1aa.5.3--1] PROPOSED FOLLOW-UP: monitored just check (13c144635hmb) timed out at the 60m budget (exit -9, killed during test lane after lint stage); this phase adds only two ~8s tests, so the timeout is host capacity, not this change

[2026-09-26T14:56:54Z · sase-1aa.5.3--1] Phase-3 proof done: new tests/test_manifest_synthetic_exercise.py derives a synthetic manifest edit (new claude model + tier + medium-selector retune) from shipped models.yml and verifies generated-docs regeneration is a clean no-op second render plus registry hooks, routing, alias resolution, picker visibility, TUI completion, and LSP payload all observe it with no Python change. Verified: 2 new tests pass, 32 neighboring manifest/render/completion tests pass, ruff+mypy clean on the new file, just fmt clean, epic-symbols empty for this bead. Full just check could not go green: symvision fails on pre-existing stale sase-19x.4 Justfile entries (tracked by sase-o7, recorded as follow-up) and the monitored run hit the 60m timeout in the test lane.

## Dependencies

- **Depends on:** [sase-1aa.5.1](sase-1aa.5.1.md) ✓ · ⧖ 2026-09-26
- **Depends on:** [sase-1aa.5.2](sase-1aa.5.2.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aa.5.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aa.5.3.md) | [sase-1aa.5.3](sase-1aa.5.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fedf207`](https://github.com/sase-org/sase/commit/fedf207c1a557d4279656be8ff9eed72b1398435) | test(models): prove synthetic manifest update reaches all model surfaces (sase-1aa.5.3) | [sase-1aa.5.3](sase-1aa.5.3.md) | 2026-09-26 10:58:55 EDT |
