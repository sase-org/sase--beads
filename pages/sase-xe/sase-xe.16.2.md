# Bead: sase-xe.16.2 — Ratchet the core pin and dependency floor past the new surface

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.2` · **Size:** small
**Created:** 2026-09-08 10:21:33 EDT · **Closed:** 2026-09-08 12:41:17 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

## Description

core-pin-and-floor: in the sase repo, once sase-core's remote HEAD contains core-fleet-surface, run `just ratchet-core-revision` to advance sase-core-revision.txt (this also finally ratchets past the sase-xe flag-removal commit that the sase-y9 five-node directive skew is waiting on), bump the `sase-core-rs` floor in pyproject.toml to the release that carries the new surface once it is published, and keep `tools/check_sase_core_rs_bindings` / `tools/validate_sase_core_rs` green. Wait for the release with /sase_monitor; if the release-plz release PR needs a human merge, raise it with /sase_questions instead of guessing.

## Notes

[2026-09-08T16:40:47Z · sase-xe.16.2] PROPOSED FOLLOW-UP: repair missing consolidated research artifact ref — plan-required reads of research:202609/tailnet_dispatch_setup/tailnet_dispatch_setup.md and research:202609/remote_dispatch_and_fleet_focus/remote_dispatch_and_fleet_focus.md resolve as status=missing even though prior consumption is recorded.

[2026-09-08T16:41:17Z · sase-xe.16.2] Ratcheted sase-core-revision.txt to 4d8fa79466d0e62a9f1b579eac3083efac920854 and raised sase-core-rs floor/lock to 0.32.46. Verified linked core HEAD contains the fleet setup surface, check_sase_core_rs_bindings, validate_sase_core_rs, validate_sase_core_rs_version --published-minimum, fresh pip install of sase-core-rs==0.32.46, ratchet-core-revision --check, ratchet-core-window --check, sase bead epic-symbols sase-xe.16.2, and just check.

## Dependencies

- **Depends on:** [sase-xe.16.1](sase-xe.16.1.md) ✓ · ⧖ 2026-09-08
- **Blocks:** [sase-xe.16.10](sase-xe.16.10.md) ◐ · ⧖ 2026-09-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.2/README.md) | [sase-xe.16.2](sase-xe.16.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5015d76`](https://github.com/sase-org/sase/commit/5015d76e9561cc68e0526627473aef9e159bc647) | chore(deps): ratchet sase-core pin and floor | [sase-xe.16.2](sase-xe.16.2.md) | 2026-09-08 13:33:48 EDT |
