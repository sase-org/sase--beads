# Bead: sase-1cp.3 — Pin the core, declare classes, and show them in sase tool list

[Bead Pages](../README.md) / [sase-1cp](README.md) / sase-1cp.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u2.md) · **Assignee:** `sase-1cp.3` · **Size:** medium
**Created:** 2026-09-29 16:48:02 EDT · **Closed:** 2026-09-29 17:40:32 EDT
**Plan:** [202609/tool\_inline\_routing.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_inline_routing.md)

## Description

catalog-duration-class: ratchet the sase-core pin, add the Python facades, declare check-full as long in sase/sase.yml using corpus evidence, and add a CLASS column plus calibration diagnostics to sase tool list, with docs.

## Notes

[2026-09-29T21:39:41Z · sase-1cp.3] Digests before/after (sase tool list -j): check f0b2638a=, check-full 62188d32=, install 9c175b5d=, test 2a8df7ac=, test-visual 3593a442= (all identical). check-full now CLASS=long, all others short; envelope schema_version stays 1; calibration null everywhere (check n=30 typical 150s short-silent; test n=3 below 10-sample minimum; check-full/test-visual no samples). Corpus: test-visual has a single signaled run with no duration; test TYPICAL 15m37s n=3 but args allow short subsets; check TYPICAL ~2m30s n=30 fails fast.

[2026-09-29T21:39:58Z · sase-1cp.3] PROPOSED FOLLOW-UP: declare test-visual duration class once its corpus supports a 600s floor (currently a single signaled run with no duration)

[2026-09-29T21:40:09Z · sase-1cp.3] PROPOSED FOLLOW-UP: just _lint-patch-stitch-terminology fails identically on the clean base tree (exit 1; 14 unclassified defects all in sase-core fixture crates/sase_core/tests/fixtures/note_attachment/at_bearing_notes.jsonl), blocking full just check; needs triage outside this phase

[2026-09-29T21:40:32Z · sase-1cp.3] catalog-duration-class done: pin ratcheted 43f744be->17b072b34f69 (core commit on origin/master), just install + bindings lint pass (753 bindings). Facades tool_run_duration_fit/calibration in core/tool_run.py. sase tool list gains CLASS column, per-tool duration_class + duration_calibration JSON (schema v1), stderr calibration diagnostics. check-full declared long; check/test/install/test-visual undeclared (short) with YAML rationale comments. Docs: configuration.md field row + tool.md Duration classes subsection; schema enum added. Verified: focused tests 24 pass (6 new), schema tests 17 pass, tests/tool+handler+catalog+schema 369 pass 1 skip; just fix clean; check gates all green except pre-existing patch/stitch terminology lint, reproduced identically on clean base (noted as follow-up). All 5 digests identical before/after; no epic-symbol leftovers. Note: machine-global uv-tool sase shim (published wheel) rejects duration_class until release; workspace .venv/bin/sase is the working path.

## Dependencies

- **Depends on:** [sase-1cp.1](sase-1cp.1.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cp.4](sase-1cp.4.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cp.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cp.3/README.md) | [sase-1cp.3](sase-1cp.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7ccdd71`](https://github.com/sase-org/sase/commit/7ccdd713a2a19e815a4861c145eed0fa7fabbdb9) | feat(tool-run): pin duration-class core, declare catalog classes, show CLASS in tool list | [sase-1cp.3](sase-1cp.3.md) | 2026-09-29 17:42:25 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cp.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cp.3/README.md

<!-- sase:referenced-by:end -->
