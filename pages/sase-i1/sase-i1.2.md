# Bead: sase-i1.2 — Adopt the released core in the sase dependency floor

[Bead Pages](../README.md) / [sase-i1](README.md) / sase-i1.2

**Status:** ✓ closed · **Resolution:** canceled · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.w8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.w8/README.md) · **Assignee:** `sase-i1.2` · **Size:** small
**Created:** 2026-08-09 07:41:53 EDT · **Closed:** 2026-08-09 08:18:10 EDT
**Plan:** [202608/bead\_search\_regex.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_search_regex.md)

## Description

floor: after sase-core publishes the release that carries the regex binding, raise the `sase-core-rs` minimum in pyproject.toml, refresh uv.lock, and confirm the published-core minimum smoke tooling accepts the new floor.

## Notes

[2026-08-09T12:17:44Z · sase-i1.2] PROPOSED FOLLOW-UP: Publish the sase-core release carrying regex bead_search before rerunning the floor bump — core master has 721f20d feat(bead): add regex search support, but tags and PyPI still stop at 0.21.1.

[2026-08-09T12:18:10Z · sase-i1.2] Verified no dependency floor bump is possible yet: PyPI latest for sase-core-rs is 0.21.1, core tags stop at v0.21.1, core master contains 721f20d feat(bead): add regex search support after the v0.21.1 release, no open sase-core release PRs were present, tools/smoke_sase_core_rs_telemetry --print-minimum still reports 0.21.1, and tools/validate_sase_core_rs_version --published-minimum passes only for the existing floor. pyproject.toml and uv.lock were left unchanged.

## Dependencies

- **Depends on:** [sase-i1.1](sase-i1.1.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-i1.3](sase-i1.3.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i1.2/README.md) | [sase-i1.2](sase-i1.2.md) | 0 |
