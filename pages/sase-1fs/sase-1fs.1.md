# Bead: sase-1fs.1 — Accept intact legacy session manifests through the Rust core

[Bead Pages](../README.md) / [sase-1fs](README.md) / sase-1fs.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.4s.f1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.4s.f1.md) · **Assignee:** `sase-1fs.1` · **Size:** medium
**Created:** 2026-10-03 12:42:02 EDT · **Closed:** 2026-10-03 15:04:15 EDT
**Plan:** [202610/bob\_cli\_agents\_publication\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202610/bob_cli_agents_publication_recovery.md)

## Description

manifest_compatibility: narrowly accept the historical family-only file set, preserve integrity checks, expose the Rust policy to Python, and prove cross-owner publication.

## Notes

[2026-10-03T19:03:20Z · sase-1fs.1] PROPOSED FOLLOW-UP: pre-existing mypy error src/sase/doctor/checks_config_retired.py:322 EntryPoints has no attribute get reproduces on clean base; sase tool run check fails there

[2026-10-03T19:03:48Z · sase-1fs.1] PROPOSED FOLLOW-UP: pre-existing symvision unused-public hits (KillProvenance, classify_runner_kill, format_kill_classification, oom_kill_evidence, reset_oom_baseline in axe/runner_kill_provenance.py; discover_macro_plugin_entry_points in main/plugin_discovery.py) reproduce on clean base

[2026-10-03T19:04:15Z · sase-1fs.1] Manifest compat done: Rust agent_session_manifest policy + sase_core_rs classify binding + Python facade; hood_file_set and validation delegate to it behind sunset flag agents_session_manifest_compat (bead sase-1ft, default on). Verified: 9 Rust core tests, 1 binding test, 11/11 test_publication_manifest.py (legacy cross-owner publish incl. bob/zeus, both flag states, slim/no-session/repeat, corruption negatives), 25 adjacent publication/rendering/repair tests, 140 flag tests, ruff clean. Pre-existing base failures recorded as follow-ups (mypy checks_config_retired, 6 symvision hits). Changed repos: sase + linked sase-core (land core first, ratchet sase-core-revision.txt past the new binding).

## Dependencies

- **Blocks:** [sase-1fs.2](sase-1fs.2.md) ✓ · ⧖ 2026-10-03
- **Blocks:** [sase-1fs.3](sase-1fs.3.md) ✓ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1fs.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1fs.1/README.md) | [sase-1fs.1](sase-1fs.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d7f2dbf`](https://github.com/sase-org/sase-core/commit/d7f2dbf0e51440910035aa9ecd3fdca1b96fe983) | feat(agent-session-manifest): canonical file-set derivation and classification | [sase-1fs.1](sase-1fs.1.md) | 2026-10-03 15:05:40 EDT |
| sase | [`1466f1a`](https://github.com/sase-org/sase/commit/1466f1a67b26ef34bd172ec03ab2476e3c0f9691) | feat(agents-sync): accept legacy family-only session manifests via Rust core | [sase-1fs.1](sase-1fs.1.md) | 2026-10-03 15:09:07 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1fs.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1fu.3--1][2] | Check whether this existing bead tracks the KNOWN Symvision findings in runner_kill_provenance.py | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1fs.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1fu.3.md

<!-- sase:referenced-by:end -->
