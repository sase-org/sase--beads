# Bead: sase-16z.5 — Plugin polling floors, CLI fingerprints, and limit events that only mark due

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q3.md) · **Assignee:** `sase-16z.5` · **Size:** medium
**Created:** 2026-09-23 11:06:14 EDT · **Closed:** 2026-09-23 14:24:09 EDT
**Plan:** [202609/usage\_window\_collection\_service\_tree.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_collection_service_tree.md)

## Description

adaptive-admission: move the core pin, let plugins declare `min_probe_interval_seconds` (claude 300, muse 180, agy/grok/codex 120), compute CLI fingerprints, and pass floors, fingerprints, and `adaptive=True` through admission, attempts, and floor-aware reads. Limit events only mark providers due and no longer force explicit probes.

## Notes

[2026-09-23T18:24:09Z · sase-16z.5] Adaptive admission done: core pin already at cfe1902 with bindings check passing; plugin floors claude300/muse180/agy-grok-codex120 with registry validation and hookspec docs; new usage/_probe_meta floors+fingerprints; _admit_one and runner pass adaptive+floor+fingerprint; limit events mark-only (no submit, origins drop limit_event, tolerant normalize); load_provider_usage floor-aware with TUI workers still off-thread; docs updated. Verified: 10 new tests/llm_provider/test_usage_adaptive_admission.py pass; 74 pass across usage/refresh/registry/peek/eligibility/capability suites; ruff+mypy clean. sase tool run check otherwise green except pre-existing unrelated symvision stale symbol sase-170.5; epic-symbols for sase-16z.5 is empty.

## Dependencies

- **Depends on:** [sase-16z.2](sase-16z.2.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-16z.4](sase-16z.4.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16z.6](sase-16z.6.md) ◐ · ⧖ 2026-09-23
- **Blocks:** [sase-16z.8](sase-16z.8.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.5/README.md) | [sase-16z.5](sase-16z.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fcce8f2`](https://github.com/sase-org/sase/commit/fcce8f2f336199f4db80088c7a02531c34f66128) | feat(llm-provider): plugin polling floors, CLI fingerprints, and mark-only limit events | [sase-16z.5](sase-16z.5.md) | 2026-09-23 14:25:40 EDT |
