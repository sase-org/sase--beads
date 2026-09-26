# Bead: sase-1ah.3 — Pin the released core before catalog adoption

[Bead Pages](../README.md) / [sase-1ah](README.md) / sase-1ah.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0st](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0st.md) · **Assignee:** `sase-1ah.3` · **Size:** medium
**Created:** 2026-09-26 07:29:32 EDT · **Closed:** 2026-09-26 10:07:39 EDT
**Plan:** [202609/tool\_e4\_verified\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e4_verified_completion.md)

## Description

core-pin-catalog: ratchet sase to a published receipt-capable core, create the beta flag, then declare per-tool accept and TTL policy without moving definition identity.

## Notes

[2026-09-26T14:06:56Z · sase-1ah.3] PROPOSED FOLLOW-UP: full-suite check lane not observed green in-turn; sase/sase.yml is a src-data-asset so test selection escalates to all 4405 files and exceeds the 9-min agent transport cap (same as sase-1ah.1); all lint gates passed and 172 affected-suite tests passed, CI/land agent owns the full lane

[2026-09-26T14:07:16Z · sase-1ah.3] PROPOSED FOLLOW-UP: no published sase-core-rs contains the receipt bindings yet (PyPI latest 0.34.73 predates 9f86897); published-wheel installs fail closed on receipt: until release-plz publishes a new sase-core-rs — land agent to confirm before broadening rollout

[2026-09-26T14:07:39Z · sase-1ah.3] core-pin-catalog done: pin ratcheted 3568b38->9f86897 (ratchet --check clean); tool_receipts beta flag created via sase flag new (bead sase-1am, default off) with registry+schema+resolver coverage; check declares receipt accept [pass,no_new_failures] ttl 2h while check-full/install/ad-hoc stay receipt-less; loader validates policy in both branches but exposes it only when the flag is on (off catalog byte-identical to today); digest-stability, probe-moves-digest, TTL/accept rejection, and off-hides-policy tests added. Verified: rebuilt sase_core_rs has receipt bindings; bindings gate 706/706; 172 affected-suite tests passed; sase tool run check lint gates all green (fmt/ruff/mypy/flags/keep-sorted/validation); symvision shows only the 3 pre-existing KNOWN stale sase-19x.4 symbols owned by another epic; epic-symbols clean for this phase.

## Dependencies

- **Depends on:** [sase-1ah.2](sase-1ah.2.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ah.4](sase-1ah.4.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ah.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.3/README.md) | [sase-1ah.3](sase-1ah.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4e85d4b`](https://github.com/sase-org/sase/commit/4e85d4bc0553290c9edfd2af1ec22d5922d6c885) | feat(tool): pin receipt-capable core and adopt catalog receipt policy | [sase-1ah.3](sase-1ah.3.md) | 2026-09-26 10:14:58 EDT |
