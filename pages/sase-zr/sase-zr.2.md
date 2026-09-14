# Bead: sase-zr.2 — Separate durable decision acceptance from slow execution

[Bead Pages](../README.md) / [sase-zr](README.md) / sase-zr.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0js` · **Assignee:** `sase-zr.2` · **Size:** medium
**Created:** 2026-09-12 05:06:14 EDT · **Closed:** 2026-09-14 08:57:12 EDT
**Plan:** [202609/prompt\_gate\_approval.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_gate_approval.md)

## Description

durable-approval-publication: Implement shared acceptance and execution policy in sase-core with thin sase orchestration. Validate and durably reserve one decision and its supervised proc before publishing approval and dismissing the notification. Keep response.json's existing execution-complete contract and required host archive receipts; project accepted plan decisions separately from terminal shell state. Route ACE-facing plan APIs, CLI, mobile, and auto approval through the same policy. Move archive/network/launch work behind the acceptance boundary, publish terminal shell state before follow-up, and make crash recovery and retry ownership explicit. Preserve branch inputs, source, archive protocol, wait and coder choices, cancellation, and partial attempts. Prove acceptance remains visible while archive/launch barriers are blocked, and prove duplicate or racing submissions cannot duplicate work.

## Notes

[2026-09-14T01:48:29Z · sase-zr.2] STATUS: sase-core (Rust) implementation and Python (sase) implementation for the durable decision-acceptance boundary are code-complete and statically validated (cargo fmt/clippy/test all green in an isolated checkout before disk exhaustion hit; ruff check/format and py_compile clean on the Python side), but full verification (just check in sase-core, pytest in sase) is BLOCKED: host root disk is at 100% (dropped from ~2.1GB to <900MB free and still falling during this session, unrelated to my own build activity which I stopped once I noticed). `sase disk reap` finds nothing currently reclaimable (everything under SASE management is within its protective TTL). Also discovered: the actual sase_core_rs binding this workspace imports is built from sase/repos/linked/sase-core, a separate local checkout from the sase/repos/external/gh/sase-org/sase-core one `sase repo open gh:sase-org/sase-core` opens (sase repo open sase-core itself is not a registered repo name for this project); I mirrored the same Rust diff into both so either can be used to rebuild. Will resume verification once disk headroom returns; not closing until just check and pytest both pass.

[2026-09-14T01:49:09Z · sase-zr.2] PROPOSED FOLLOW-UP: Host root disk hit 100% full during this session (dropped from ~2.1GB to <900MB free over roughly an hour with no cargo builds running on my side for most of that window), actively blocking cargo/rustc compilation ("No space left on device") for any agent on this host. `sase disk reap` (dry run) reported 0 B reclaimable across every owner (managed_tmp_reaper 25.3GiB, workspace_cleanup_and_compact 25.4+2.5GiB, rust_prebuild_cache 5.5GiB) because everything present is within its protective TTL/retention horizon, and ~100GB of the 191GB used is outside SASE's own disk accounting entirely (not covered by `sase disk list`). Needs a human or ops agent to either identify what the other ~100GB is, tighten the reap TTLs, or expand the volume; automated reap cannot help as currently configured.

[2026-09-14T01:49:47Z · sase-zr.2] PROPOSED FOLLOW-UP: `sase repo open sase-core` fails with "Unknown repo 'sase-core'" even though this project's own Justfile/AGENTS.md tell developers to run exactly that command to refresh a stale sase-core checkout, and a real local dev checkout already exists at sase/repos/linked/sase-core (used by `just rust-install` for the editable sase_core_rs binding, distinct from an externally-opened gh:sase-org/sase-core clone). Either sase-core should be registered as a proper linked repo for this project, or the AGENTS.md/Justfile guidance pointing at `sase repo open sase-core` should be corrected to describe the actual mechanism.

[2026-09-14T12:57:12Z · sase-zr.2--1] Verified: just _lint-symvision passed after making monitor store lookup helpers private; focused monitor/audit reruns passed (39 monitor tests and 4 prior full-suite failures); just check passed, with test-scoped escalating to the full suite due core-identity-changed; sase bead epic-symbols sase-zr.2 reported no entries.

## Dependencies

- **Depends on:** [sase-zr.1](sase-zr.1.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zr.3](sase-zr.3.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zr.4](sase-zr.4.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-zr.2.md) | [sase-zr.2](sase-zr.2.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c8152f4`](https://github.com/sase-org/sase/commit/c8152f4978272b6c6cce30ec9f23470926fff144) | feat(gate-shell): accept gate decisions durably before slow execution | [sase-zr.2](sase-zr.2.md) | 2026-09-13 21:51:48 EDT |
| sase-core | [`sase-core@809f45e`](https://github.com/sase-org/sase-core/commit/809f45ed26a656d8fb8152afb1f077dd6070f022) | feat(gate\_decision): add durable decision-acceptance policy and binding | [sase-zr.2](sase-zr.2.md) | 2026-09-13 21:53:32 EDT |
| sase | [`d2ba89c`](https://github.com/sase-org/sase/commit/d2ba89cb420aea18ac27b4192e6bb49731729cbd) | fix(monitor): keep lookup helpers private | [sase-zr.2](sase-zr.2.md) | 2026-09-14 08:59:17 EDT |
