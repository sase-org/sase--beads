# Bead: sase-1sd.4 — Stop continuation capture from nesting fork ancestry past the 256 KiB cap (sase-1o1)

[Bead Pages](../README.md) / [sase-1sd](README.md) / sase-1sd.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bp.md) · **Assignee:** `sase-1sd.4` · **Size:** large
**Created:** 2026-11-12 05:26:16 EST
**Plan:** [202611/next\_seven\_salvage\_and\_unstrand.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_seven_salvage_and_unstrand.md)

## Description

continuation-capture: persist_agent_delta records the #fork-expanded step prompt as authored_local_request and replay renders it as the parent user block, so every session member re-nests its whole ancestry; a live athena land session is at 708,391 bytes against the 262,144-byte validator cap, and an over-cap turn fails capture and settles the next monitor follow-up not-launchable. Capture only the local pre-fork request, make replay walk the parent chain, keep fork-replay output byte-stable, and add a repair or explicit error for in-flight over-cap sessions. Needs sase-core and sase changes.

## Notes

[2026-11-12T14:51:18Z · sase-1sd.4] Planning only: inspected clean sase 8eef093fa9 and sase-core afc64b10. Bug remains: deferred launch fork expansion precedes anonymous workflow preparation, which labels the expanded step prompt and its local_authored segment as local. Exact parent hydration already exists; the 100-handoff regression bypasses this launch boundary. Prepared a medium tale with launch-provenance transport, existing replay compatibility, Rust byte-count diagnostics, and tested checkpoint resume for over-cap legacy capture. No source edits or implementation tests yet: checkout venv lacks sase_core_rs, so boundary probes failed at import. Current agent scan found no live sase-1ra worker and the sase-1n6.11 steward waiting on its GitHub-settings monitor; no continuation edits overlap observed. No phase epic-symbol entries. Historical 708391-byte session not reproduced by current listed-agent scan; cited research artifact did not resolve. Implementation scope remains entirely with the approved tale successor; keep this phase in progress.

## Dependencies

- **Depends on:** [sase-1sd.3](sase-1sd.3.md) ✓ · ⧖ 2026-11-12
- **Blocks:** [sase-1sd.5](sase-1sd.5.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sd.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sd.4.md) | [sase-1sd.4](sase-1sd.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@fae59b4`](https://github.com/sase-org/sase-core/commit/fae59b46a9db7e7c37656bea7d1e7fa98ebaabc6) | fix(continuation): report authored request byte limits | [sase-1sd.4](sase-1sd.4.md) | 2026-11-12 12:10:02 EST |
| sase | [`1087ccd`](https://github.com/sase-org/sase/commit/1087ccd7f15f09f9cd2267a4cef598a1219432ca) | fix(continuation): preserve local request provenance | [sase-1sd.4](sase-1sd.4.md) | 2026-11-12 12:11:33 EST |
