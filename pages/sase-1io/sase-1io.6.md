# Bead: sase-1io.6 — Merge the release PR and publish v0.18.0

[Bead Pages](../README.md) / [sase-1io](README.md) / sase-1io.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ys](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ys.md) · **Assignee:** `sase-1io.6` · **Size:** medium
**Created:** 2026-10-09 03:55:09 EDT · **Closed:** 2026-10-09 06:20:57 EDT
**Plan:** [202610/release\_v0\_18\_0.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_v0_18_0.md)

## Description

ship: merge the 0.18.0 release PR once its gates hold, run the publish workflow, and verify the release installs from PyPI.

## Notes

[2026-10-09T10:20:42Z · sase-1io.6] PROPOSED FOLLOW-UP: sase-core concurrent_readers_see_consistent_snapshots shows third macOS-only failure mode (ENOENT mid-test) — run 37912585861 on 6faaa653: main thread unwrap at parity.rs:914 "unable to open database file .../bead-read-model-*.sqlite" plus reader unwraps at :894 missing store/events/streams, all inside one live TempDir (guard held, joined before drop), with /private/var vs /var canonical split between the two error paths; earlier modes were no-such-table meta (run 37904251133) and SIGBUS (run 37908024251); passes on Linux (single test ok, full parity binary 6/6 ok locally at 6faaa653), so not reproducible off-mac; needs macOS diagnosis of the sqlite-cache vs event-store concurrent lifecycle, then the 0.37.1 cut

[2026-10-09T10:20:57Z · sase-1io.6] RELEASE NOT SHIPPED: PR 299 (chore(master): release 0.18.0) not merged — release-core-floor-smoke fails because PyPI floor is still sase-core-rs 0.37.0, missing 5/807 bindings (bead_probe_target_owner, classify_auto_directive, instruction_manifest_wire_schema_version, normalize_instruction_manifest, wait_epic_follow_reduce); no 0.37.1 on PyPI (sase-core-rs latest is 0.37.0, sase latest is 0.17.1). Blocker is the macOS-only sase-core parity race (see PROPOSED FOLLOW-UP note on this bead; also sase-1io.2 notes 3-4, sase-1io.5 note 1): latest sase-core CI 37912585861 red on macOS leg only. ci_watch conditions unmet: Master Gate tip run 37915170978 in progress while prior tip run 37914769130 failed lint on the already-triaged symvision residual in declared_commands.py (sase-1io.5 note 2); no green Full CI within 6h (37909515949 in progress on a pre-fix tip); PR 299 checks red. Verified locally at sase-core tip 6faaa653: parity test passes on Linux (full binary 6/6). No files changed in sase or sase-core checkouts; nothing merged. Land agent path: fix parity race on macOS, cut 0.37.1 via release-plz, wait PyPI + ratchet, re-run publish.yml, confirm PR 299 green, merge, publish, verify pip install sase==0.18.0.

## Dependencies

- **Depends on:** [sase-1io.5](sase-1io.5.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.6/README.md) | [sase-1io.6](sase-1io.6.md) | 0 |
