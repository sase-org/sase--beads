# Bead: sase-196.4 — Adopt the scoped seal in sase

[Bead Pages](../README.md) / [sase-196](README.md) / sase-196.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ry.f0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ry.f0.md) · **Assignee:** `sase-196.4` · **Size:** small
**Created:** 2026-09-25 09:05:38 EDT · **Closed:** 2026-09-25 11:39:26 EDT
**Plan:** [202609/agents\_sidecar\_orphan\_objects.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_sidecar_orphan_objects.md)

## Description

seal-scope-adopt: move the sase-core revision pin, add Python regression tests for the incident shape, and document which repositories prepare inspects and fingerprints.

## Notes

[2026-09-25T15:38:35Z · sase-196.4] PROPOSED FOLLOW-UP: `sase tool run check` is blocked at SASE prompt-archive validation by the three untracked and one missing agents-sidecar objects already tracked by ready bug sase-17u; all formatter and lint stages passed.

[2026-09-25T15:39:26Z · sase-196.4] Moved the sase-core pin to 9e1ac1dae034, added scoped seal regressions for protected sidecar dirt and unrelated sidecar commits, and documented decision-scoped eligibility/fingerprints. Verified focused pytest (14 passed); recorded the clean-base prompt-archive validation blocker under sase-17u after all formatter and lint stages passed.

## Dependencies

- **Depends on:** [sase-196.3](sase-196.3.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-196.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-196.4/README.md) | [sase-196.4](sase-196.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`45a2e61`](https://github.com/sase-org/sase/commit/45a2e61be9b8d5146f05ff360a24577311aab144) | fix(finalizers): adopt decision-scoped completion seal | [sase-196.4](sase-196.4.md) | 2026-09-25 11:40:50 EDT |
