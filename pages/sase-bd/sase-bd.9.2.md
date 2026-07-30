# Bead: sase-bd.9.2 — Publish the release containing all four core commits

[Bead Pages](../README.md) / [sase-bd.9](sase-bd.9.md) / sase-bd.9.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bd.9.2` · **Size:** small
**Created:** 2026-07-30 20:15:06 UTC · **Closed:** 2026-07-30 20:54:55 UTC
**Plan:** [202607/bead\_close\_integrity\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_close_integrity_landing.md)

## Description

core-release: merge the refreshed release PR once master is green, then confirm the published wheel is actually installable from the package index and carry the real published version forward.

## Notes

[2026-07-30T20:54:55Z · sase-bd.9.2] Merged sase-core release PR #63 (chore: release v0.15.0) after master went green on 407965e. Verified before merging that the refreshed release branch contained all four target commits (160ff9e, 293ccb2, 81a82d5, 6468cb9) plus the clippy fix, that all PR checks passed (cargo fmt+clippy+test, maturin build+import smoke), and that the proposed bump was a breaking 0.14.2 -> 0.15.0. Post-merge: master CI run 30580458464 green, Release-plz run 30580460440 green through 'publish to PyPI', tag v0.15.0 -> 803ff81 (the merge commit). Confirmed publication from the index, not the repo: 'uv pip install --no-cache sase-core-rs==0.15.0' into a clean 3.12 venv succeeded, tools/check_sase_core_rs_bindings exited 0 ('exposes all 230 bindings required'), bead_doctor_report is present, and bead_show against the live beads sidecar returned sase-bd.3 instead of raising 'unknown variant note_appended'. Published version to carry into floor-bump: 0.15.0. No repo file changes in this phase.

## Dependencies

- **Depends on:** [sase-bd.9.1](sase-bd.9.1.md) ✓
- **Blocks:** [sase-bd.9.3](sase-bd.9.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bd.9.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bd.9.2/README.md) | [sase-bd.9.2](sase-bd.9.2.md) | 0 |
