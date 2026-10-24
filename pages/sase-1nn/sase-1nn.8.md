# Bead: sase-1nn.8 — Finish the sase v0.18.1 release blockers left by sase-1nn and watch it to PyPI

[Bead Pages](../README.md) / [sase-1nn](README.md) / sase-1nn.8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.land.md) · **Assignee:** `sase-1nn.8.land`
**Created:** 2026-10-23 18:32:22 EDT
**Plan:** [202610/v0\_18\_1\_release\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_landing.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/v0_18_1_release_landing.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:8e0989eee98b211b259bfe9b | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_landing.md

<!-- sase:links:end -->

## Description

Master Gate and Full CI are green on a tip that contains the custom-gate resize wait fix, the hermetic TUI profiling env, and an exact sase-core-rs 0.42.3 pin; ci_watch merges release PR #321; Publish uploads sase 0.18.1 to PyPI; and the lander that observes it records the evidence artifact and closes this epic and sase-1nn.

## Notes

[2026-10-24T06:41:43Z · sase-1nn.8.land] LANDING AUDIT (sase-1nn.8.land, 2026-10-24): release acceptance is NOT met. PR #321 is OPEN at d1c884a13c96983aa09b670e4184ca4202128e69; PyPI sase/0.18.1 returns 404. Child sase-1nn.8.3 deliberately closed canceled after FULL_CI_RED. This epic and parent sase-1nn remain open. Evidence: file:explicit:8e0989eee98b211b259bfe9b.

Verified every child note and the actual source/commits. 43314db7ad supplies the screen.outer_size reflow wait in both sizing helpers, the PERF/CENSUS/TRACE autouse scrub, and the corrected perf golden. dd0c6d8d19 pins pyproject and uv.lock to 0.42.3. The core tag f726ca1e contains source pin 58aca5fe (merge-base check passed); PyPI has all five required suffixes. Fresh isolated published-wheel probes pass all 876 bindings and tools/validate_sase_core_rs exits 0. No core source-pin drift since this epic. Focused current-master audit: 26 passed in 54.81s with PERF/CENSUS/TRACE=1, covering all six custom-gate sizing tests, three environment nodes, the project-label audit, and parser tests on Python 3.14. The three env nodes also pass with flags unset (3 passed). Closed sase-1np and duplicate sase-1nq as resolved with this evidence.

DECISIONS honored: publish_dispatch=yes and gate_rerun=yes. Watch notes and run history show a Publish refresh and one Master Gate rerun per failed run, no hand merge or release.yml/steward-live dispatch. Cutover phase sase-1n6.9 remains in_progress. The watcher ran successfully for hours, then canceled on two real red Full CI runs; no timeout-parser recurrence. Both this epic and sase-1nn have no epic-symbol entries.

Integration inventory: HEAD == fetched origin/master == 102c6ee847. Non-epic commits after first epic commit 43314db7ad are a7996c3b77 (stranded detail, correct project-key identity exemption), a2a38005df (finalizer split), 1a5e01adba (doctor test split), and 102c6ee847 (stats repo breakdowns). The splits do not conflict with the release fixes. 102c6ee847 introduces two duplicate lines into the Python 3.12 project_help.txt golden; actual parser emits each once and the py313 golden is correct. Master Gate 40058175796 attempt 2 shard 4 and Full CI 40063272183 Python 3.12 fail only that node. Full CI 3.13/3.14 pass. Earlier overlapping bb81495765 from sase-1no.3 adds Help legend rows without updating agents_archive_help_120x40; latest Full CI visual job 120783473777 reports exactly 52757/1520532 changed pixels, matching the phase proposal. Older Full CI 40054807788 had this plus renamed-generic-session drift; newest Full CI has only archive-help. Do not accept the older transient candidate without current reproduction.

Follow-up triage (all PROPOSED FOLLOW-UP entries accounted for):
- sase-1nn.8.1 note 1, archive-help golden: causally owned by still-open sase-1no (phase .3, bb81495765). Added a DISCOVERED ISSUE note there under /sase_new_task; no duplicate task. Retain the actual golden repair in this release's remaining integration work because it blocks Full CI.
- sase-1nn.8.2 note 3, import budget: existing owner sase-1ic. Added a supplementary note relaying the phase ToolRun and witness; no duplicate and no extra +1 because triage already names the owner. Not reproduced in release CI; remains an out-of-scope local environment count issue.
- sase-1nn.8.2 note 4, stranded_project_key_for_agent audit: declined as already fixed by a7996c3b77. Source now has the identity-only exemption and the full presentation audit passes in the 26-test audit. sase-1ly is a different older site and stays closed; no task or reopen.
- New lander-found stats golden regression: created small ci task sase-1nt via /sase_new_task after same-type/all-type searches, last-week sweep, and active-epic review. The precise root cause is two duplicated golden additions in 102c6ee847, not the argparse spelling defect in sase-14p. Linked its dependency to this epic to avoid duplicate execution; the child repair owns it and the successful lander closes it.

HANDOFF: authoring a two-phase remaining-work child epic with parent_bead sase-1nn.8: repair the two deterministic goldens, then a self-closing release watch after the repair commit reaches master. This needs separate phases because verification/publication must observe a committed repair; a single tale cannot wait for its own end-of-turn commit. The child lander will verify actual release evidence and resume this epic and then sase-1nn. No source, golden, pin, memory, or Justfile edits were made in this audit turn; no just check-full was run.

## Dependencies

- **Blocks:** [sase-1nt](../sase-1nt/README.md) ◇ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.land.md) | [sase-1nn.8](sase-1nn.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nn.8.1][1] | Need parent epic scope, decisions, plan | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.8.1/README.md

<!-- sase:referenced-by:end -->
