# Bead: sase-1tz.3.1 — Targeted defect fixes for the prompt\_prose wire, update races, Telegram transport, bundle caps, and triage conflicts

[Bead Pages](../README.md) / [sase-1tz.3](sase-1tz.3.md) / sase-1tz.3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.land`
**Created:** 2026-11-20 09:19:04 EST · **Closed:** 2026-11-20 13:37:49 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/defects_wire_swap_telegram_bundles_triage.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 10 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md

<!-- sase:links:end -->

## Description

Host-produced artifact-link origins, including prompt_prose, round-trip through the real sase_core_rs binding, and a contract test fails on any future origin drift. Jobs and launches that overlap a code swap defer and retry instead of failing, an update-overlap reproducer guards that behavior, and a prebuilt-artifact cache miss is a miss rather than a failure. Telegram falls back to plain text only on entity-parse errors, retries per chunk without resending delivered chunks, reports credential and network outages once per state transition, and runs its outbound job only on the sending machine. Every provider root bundle fits its declared max_bytes through compile-time compaction, with a doctor check and a just-check test that catch growth. bead_task_triage recovers from request_id_conflict by advancing the generation.

## Notes

[2026-11-20T18:37:49Z · sase-1tz.3.1.land] LANDED. All 11 phases were closed and every phase note was reviewed. The code and commits match the plan and the parent DECISIONS: codex_bundle=trim (Codex keeps max_bytes at 32 KiB and the fix is compile-time compaction), and held_heartbeat/blocked_waiters had no effect here.

WHAT LANDED
- prose_wire: sase eca97ab5a7; sase-core 09391374 adds PromptProse to ArtifactLinkOriginWire. Pin 0939137425 contains it, and 41f95c82cf contains sase-core 142ed421. ARTIFACT_LINK_HOST_ORIGINS is the single source, with derived subsets, and the binding contract test is in place.
- swap_repro: 9bbdeec5f4 adds the harness and tools/swap_overlap_census.
- swap_chop_guards: 3ae6b09b72 adds the last-swap stamp shared with the installer, no starts under a writer, the 120 s missing-script grace, and post-exit overlap classification.
- swap_launch_guards: 7c73ee3866 covers sase run, bead work, and runner defer/re-exec; routine exit-75 restart; and finalizer and sase_core_rs preload in supervisors.
- prebuild_miss: f9b8800341. A cache miss exits 0 and records status miss; install.dev and install.pypi count as writers.
- tg_transport: sase-telegram 60a94ab. Parse-only fallback, per-chunk retry, and partial-delivery resume.
- tg_degraded: sase-telegram ceffb63. Persisted degraded states, one notice per transition, and a 60 s token negative cache.
- tg_scope: chezmoi 3623450f moves the telegram routine into sase_athena.yml only.
- bundle_trim: 41f95c82cf. Compaction ladder; under-cap bundles stay byte-identical.
- bundle_gate: f6b4344d87. Deep doctor check instructions.bundle_size plus a just-check contract test.
- triage_conflict: b6f6c63e3e. Cancel, advance and persist the generation, retry once per pass.

VERIFICATION
- No reproducer xfail remains in tests/dev_update/test_swap_repro_*.py.
- After rebuilding this workspace venv (sase tool run install-venv 5b46f746, cached wheel at the pin), the focused epic suites passed 278/278: the swap repro, stamp, parity, guard, epoch, launch retry, bead work, launch query, runner, entry, origin contract, compaction, size gate, doctor, triage, prebuild, progress, reconcile, source skew, orchestrator, and lumberjack tests.
- The per-phase sase tool run check results are on each phase bead (bundle_gate 3affb70e7008 escalated to the full suite and was green on the tree that is HEAD). The lander changed no tracked files, so no new check was needed.
- sase-telegram check: 876 passed plus 4 pre-existing ERRORs from a stale patch, reproduced on the clean base. Filed as sase-1ug.
- Every measuring phase recorded before-numbers and an after-install command on its own bead with a summary on sase-1tz.3. The lander added the missing triage_conflict summary there.

INTEGRATION
- Since the epic started, only 2 unrelated commits landed in sase (d759499674 and 6ab880ad62), plus 1 unrelated chezmoi commit (c1481594). None landed in sase-core or sase-telegram.
- d759499674 split tests/dev_update/test_progress.py. The prebuild hit, miss, and consume-error tests survived in test_progress_execute.py.
- No remaining literal artifact-link origin call sites need the new constant.
- No epic-symbol entries.

FOLLOW-UP TRIAGE
- New ready tasks:
  - sase-1uc: origin capability probe (from .1 #2).
  - sase-1ud: atomic maturin/sase_core_rs install (from .2 #4).
  - sase-1ue: lazy sase.dev_update init (from .4 #3).
  - sase-1uf: arm the swap retry for sase prompt run (from .4 #5).
  - sase-1ug: sase-telegram stale _project_display_name_map_cached patch (from .6 #1 and .7 #2).
  - sase-1uh: sase-telegram AGENTS.md module list (from .7 #3). It is a task because the plan forbade AGENTS.md edits.
  - sase-1ui: prettier SKILL.md test fails under bare pytest (from .9 #4 and .4 #6). The lander reproduced it.
- Corroborated with a +1: sase-1tn (gate-capacity e2e flake from .2 #6; it is the node-specific bead, not the sase-1q8 umbrella), sase-1kr (.9 #3), and sase-1ry (.11 #2).
- sase-t6 already had this epic's +1 (.5 #4). Got a supplementary note for .2 #6.
- Declined:
  - .2 #5 (stale code-swap.lock doc path): already fixed by .3 in plugins-update.md.
  - .4 #4 (host-completion defer and re-drive): conditional on post-install field evidence that does not exist yet (corpus-before-mechanism). Its check is the census command on .4 #6 and sase-1tz.3 #3.
  - .10 #2 (trim bob-cli always-inlined memory): bob-cli project memory, read-only for this epic. bob-cli fits after compaction and the new doctor check WARNs on it on every deep run, so the signal is durable. Left for bob-cli owners.

LIVE ACCEPTANCE (human)
Install, run chezmoi apply on each host, and run sase agent sync -p sase -q. Then run the after-install commands recorded on each phase bead.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.land/README.md) | [sase-1tz.3.1](sase-1tz.3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@0210bca`](https://github.com/sase-org/sase--plans/commit/0210bca3373e82a82087becae6a6af4d3cb1a1bf) | chore(plans): mark defects\_wire\_swap\_telegram\_bundles\_triage done after landing sase-1tz.3.1 | [sase-1tz.3.1](sase-1tz.3.1.md) | 2026-11-20 13:39:46 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.3.1.1][1] | Need epic decisions and context | 1 |
| read-by | [agent:sase-1tz.3.1.10][2] | Need epic decisions | 1 |
| read-by | [agent:sase-1tz.3.1.11][3] | Need parent epic decisions governing this phase | 1 |
| read-by | [agent:sase-1tz.3.1.2][4] | Check sibling phase state and epic decisions before swap_repro work | 1 |
| read-by | [agent:sase-1tz.3.1.3][5] | Check epic decisions for swap_chop_guards phase | 1 |
| read-by | [agent:sase-1tz.3.1.4][6] | Need epic decisions | 1 |
| read-by | [agent:sase-1tz.3.1.7][7] | Need epic decisions and notes | 2 |
| read-by | [agent:sase-1tz.3.1.9][8] | Need epic DECISIONS | 1 |
| read-by | [agent:sase-1tz.3.1.land][9] | Need the epic scope, children, and linked plan file | 1 |
| read-by | [agent:sase-1uj.land][10] | Check whether prompt_prose parent is still open | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.10/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.11/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.2/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.3/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.4/README.md
[7]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.7/README.md
[8]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.9/README.md
[9]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.land/README.md
[10]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1uj.land/README.md

<!-- sase:referenced-by:end -->
