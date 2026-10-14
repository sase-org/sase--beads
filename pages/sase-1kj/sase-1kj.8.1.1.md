# Bead: sase-1kj.8.1.1 — Capture artifact-link parity and performance baselines

[Bead Pages](../README.md) / [sase-1kj.8.1](sase-1kj.8.1.md) / sase-1kj.8.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1kj.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kj.8.md) · **Assignee:** `sase-1kj.8.1.1` · **Size:** small
**Created:** 2026-10-13 17:50:21 EDT · **Closed:** 2026-10-13 18:23:10 EDT
**Plan:** [202610/artifact\_link\_inverted\_index.md](https://github.com/sase-org/sase--plans/blob/main/202610/artifact_link_inverted_index.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:3a5bf4d354280c501f5612e1 | attached via sase artifact create --bead |
| related | file:explicit:80e99d7bd0dd70b772bc0d36 | attached via sase artifact create --bead |
| related | file:explicit:b40f51f8be770b1faebef99a | attached via sase artifact create --bead |
| related | file:explicit:d2542373c3e77e5e669916e9 | attached via sase artifact create --bead |
| related | file:explicit:eeb8a379bc66ce2ef413446a | attached via sase artifact create --bead |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

parity-baseline: freeze current chips, targets, and Patch-edge outputs in fixtures and record reproducible CPU and wall-time baselines on a saved real aggregate before either implementation changes.

## Notes

[2026-10-13T22:22:57Z · sase-1kj.8.1.1] Parity-baseline evidence for later native-index / python-integration phases.

Sanitized oracle (in git): tests/ace/tui/fixtures/artifact_link_parity/{input,expected_chips,expected_patch_index}.json
Helper: tests/perf/artifact_link_index_bench.py
Tests: tests/ace/tui/test_link_index_parity.py, tests/ace/tui/test_artifacts_relation_sources_artifact_links.py::test_parity_fixture_pins_every_patch_relation_edge_and_target, tests/perf/test_artifact_link_index_bench.py (14 focused tests passed).

Real aggregate captured via load_artifact_links_snapshot('gh_sase-org__sase'): 41295 rows, input_hash 6907c9500c61e00055a6cb2ebbe2b4b3ee5dd80f1e8383803736e8fb8e0a48fe, 154710 chips / 64259 refs. Live aggregate has no patch: refs, so Patch projection emitted 0 link edges over 3 frozen patches (still paid the full-row walk). Host was busy (loadavg ~21). Identity pinned from AgentIdentitySnapshot.current() at capture (bbugyi200/athena). Unknown document-kind accents use the no-descriptor external fallback so later phases match.

Durable artifacts (consume with sase artifact read, never a sidecar-file read):
- aggregate: file:explicit:3a5bf4d354280c501f5612e1
- expected chips: file:explicit:eeb8a379bc66ce2ef413446a
- expected Patch RelationIndex: file:explicit:d2542373c3e77e5e669916e9
- frozen patches: file:explicit:80e99d7bd0dd70b772bc0d36
- timings/metadata: file:explicit:b40f51f8be770b1faebef99a

Baseline timings (wall_s / cpu_s): input_load 0.290/0.289; cold _build_link_index 2.039/2.038; eager by_ref consume 0.002/0.002; representative queries 0.212/0.212; full Patch projection 0.574/0.574; public cold link_index_for_snapshot 2.197/2.181; warm reuse 9e-6/1e-5. python 3.14.7, sase-core-revision d30e1337a848f0bef8978153de3731badee00d46.

Reproducible commands:
.venv/bin/python -m tests.perf.artifact_link_index_bench write-fixture-goldens
.venv/bin/python -m tests.perf.artifact_link_index_bench capture --project gh_sase-org__sase --output-dir /tmp/artifact-link-parity
.venv/bin/python -m tests.perf.artifact_link_index_bench measure --aggregate <sase-artifact-read-aggregate> --patches <sase-artifact-read-patches>
.venv/bin/python -m tests.perf.artifact_link_index_bench compare --expected <saved> --actual <new>
sase artifact read file:explicit:3a5bf4d354280c501f5612e1 "Need the frozen aggregate"
build_synthetic_scale_rows() is available if a later host has no nonempty real aggregate; do not treat it as real-data parity.

[2026-10-13T22:23:04Z · sase-1kj.8.1.1] PROPOSED FOLLOW-UP: Stale Justfile --epic-symbol sase-1kj.7(patch_relation_index_real_build_count) — sase-1kj.7 is closed; just check / sase tool run check fails on this checkout identically with the same error on HEAD before this phase (symvision: bead is closed. Remove this stale --epic-symbol entry). No task bead found tracking the leftover.

[2026-10-13T22:23:10Z · sase-1kj.8.1.1] Pinned sanitized LinkChip and Patch RelationIndex goldens; captured real gh_sase-org__sase aggregate (41295 rows, hash 6907c9500c61e00055a6cb2ebbe2b4b3ee5dd80f1e8383803736e8fb8e0a48fe) as file:explicit:3a5bf4d354280c501f5612e1 plus chips/patch/timings artifacts; 14 focused tests passed; just fmt passed; sase tool run check failed only on preexisting stale --epic-symbol sase-1kj.7 (closed) which reproduces on HEAD. This phase has no --epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1kj.8.1.2](sase-1kj.8.1.2.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kj.8.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.8.1.1/README.md) | [sase-1kj.8.1.1](sase-1kj.8.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bad0d0a`](https://github.com/sase-org/sase/commit/bad0d0ac361be172f5d200f86390f64f6a8fc5f6) | test(artifact-links): pin link-index parity oracle and perf baseline helper | [sase-1kj.8.1.1](sase-1kj.8.1.1.md) | 2026-10-13 18:24:51 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kj.8.1.1][1] | Need remaining notes, decisions, and full description | 2 |
| read-by | [agent:sase-1kj.8.1.2][2] | Need DECISIONS, prior notes, and parent epic context | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.8.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.8.1.2/README.md

<!-- sase:referenced-by:end -->
