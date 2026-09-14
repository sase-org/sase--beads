# Bead: sase-110.3 — Ratchet the core pin and dependency floor past the runner surface

[Bead Pages](../README.md) / [sase-110](README.md) / sase-110.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0kl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0kl.md) · **Assignee:** `sase-110.3` · **Size:** small
**Created:** 2026-09-14 11:33:16 EDT · **Closed:** 2026-09-14 13:58:12 EDT
**Plan:** [202609/agent\_sudo\_requests.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_sudo_requests.md)

## Description

core-pin: ratchet sase-core-revision.txt and the sase-core-rs floor to the release carrying the sudo runner and bindings, keeping binding validators green.

## Notes

[2026-09-14T17:58:12Z · sase-110.3] Ratchet verified: sase-core-revision.txt -> 3566872b4916123fedf100b7c5684c701085655c (sase-core v0.34.28), pyproject/uv.lock floor -> sase-core-rs>=0.34.28,<0.35.0; .venv installed 0.34.28 with sudo_runner_main and classify_disk_pressure bindings; validate_sase_core_rs_version --published-minimum, check_sase_core_rs_bindings, validate_sase_core_rs, git diff --check, and final just check passed; sase bead epic-symbols sase-110.3 reported no entries.

## Dependencies

- **Depends on:** [sase-110.1](sase-110.1.md) ✓ · ⧖ 2026-09-14
- **Blocks:** [sase-110.4](sase-110.4.md) ✓ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-110.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-110.3/README.md) | [sase-110.3](sase-110.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dd672fd`](https://github.com/sase-org/sase/commit/dd672fd6cbd3e5bcf89ae51ea12e77ce62f1228d) | chore(core): ratchet sudo runner core floor | [sase-110.3](sase-110.3.md) | 2026-09-14 13:59:50 EDT |
