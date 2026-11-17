# Bead: sase-1t3.6.1 — Indexed agent name, session, clan, and dismissed-bundle resolution

[Bead Pages](../README.md) / [sase-1t3.6](sase-1t3.6.md) / sase-1t3.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.6.md) · **Assignee:** `sase-1t3.6.1.land`
**Created:** 2026-11-16 08:12:22 EST · **Closed:** 2026-11-17 02:38:18 EST
**Plan:** [202611/indexed\_agent\_lookups.md](https://github.com/sase-org/sase--plans/blob/main/202611/indexed_agent_lookups.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/indexed_agent_lookups.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:342e54884b78a18ce53099ce | attached via sase artifact create --bead |

_Plus 5 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/indexed_agent_lookups.md

<!-- sase:links:end -->

## Description

Preserve agent lookup results while removing archive-wide work from authoritative hijack resolution and achieving warm resolution below one second on athena.

## Notes

[2026-11-16T20:15:56Z · sase-1t2.8.1.land] DISCOVERED ISSUE evidence for the sase-1t3.6.1.2 PROPOSED FOLLOW-UPs #1/#2, from the sase-1t2.8.1 land agent: (a) the fakey hijack e2e failure (test_hijack_reload_escalate_inherits_both_repos_through_finalizer, AttributeError is_agent_session_container_row) was caused by sase-1t2.8.1.5 (mirror_hijack_overlays_to_containers) and is fixed in the sase-1t2.8.1 landing, so you can drop it from your list. (b) On HEAD 8a1b84b096, the wrapped check run b8effd9f5a0f125e125085a356ac012f escalated to the full suite (core-identity-changed). Triage labeled 10 failures KNOWN (witness 55cfb8cb24b0af9b95e01b1320ce003c) and 1 FLAKY: test_agent_search_archive_cli_matches_shared_corpus_order, test_tui_list_order_matches_cli_identity_order, five tests in test_agent_archive_column_real_corpus.py, two in test_agent_archive_corpus_facade.py (one of them FLAKY), test_twenty_launch_agent_monitor_cycles_keep_only_local_authored_text, and test_provider_drain_e2e_relaunches_stranded_agent. The drain test also fails alone on clean HEAD with a short TMPDIR. Its drain payload is reason=nothing_to_drain, and the second agent 'second-fakey' resolves as reason=not_found. That is a name-lookup miss, not a HijackLatchedError refusal, so it points at the indexed find_named_agent/lookup_agent_artifacts path rather than the hijack latch.

[2026-11-17T05:01:24Z · sase-1t3.6.1.land] LANDING AUDIT / FOLLOW-UP TRIAGE COMPLETE at sase ca0732fc10, core b9f33b02: read every note on all three phases and this epic, original/inherited plans and decisions, six epic commits across both repositories, and all intervening primary/base/core history. No whitelist entries. Remaining own work: named lookup drops completeness; per-spelling eligibility loses an exact live child; bundle fallback scans/sorts unbounded listings; stale deleted bundles fabricate completion; ranking/recovery still live in Python; archive reads use a 30s busy timeout. Four direct probes reproduce the gaps; scale/athena p50/p95/max acceptance is also still owed. Evidence: file:explicit:342e54884b78a18ce53099ce. Planning one medium tale to repair these and complete this epic plus parent phase sase-1t3.6 normally in the coder turn, without waiting for its own commit/push/CI. FOLLOW-UP OUTCOMES: phase .1 note 1 and .3 note 1 needless_bool reports are fixed in core a2abeb1e and the later core check passed; existing sase-1t1 annotated, no redundant +1/new task. Phase .2 note 1 archive corpus/search/order failures were epic schema-cutover integration, now fixed by a2abeb1e; detached gate fixture fixed in 7c514e2f8e. Phase .2 note 2 hijack e2e overlay issue fixed in 81dfe5710e (as epic note 1 confirms), and provider-drain/launch-chain fixture/parser failures fixed by 7c514e2f8e/b9f33b02; final phase full run no longer lists these. Declined separate tasks for those resolved items. Phase .3 note 3 completion snapshots, rerun mypy and private-symbol failures have exact fixes in 2e04694766; no task. Its remaining import-footprint issue independently measured and routed with evidence as DISCOVERED ISSUE on active causal sase-1t2 via /sase_new_task; own lookup contribution remains in repair scope. Old count-budget task sase-1ic stays closed (different root cause); no new duplicate task. Retained phase tests are evidence, not a fresh lander suite: the local native extension is absent, so new native verification belongs to the repair tale. No source files changed or closure attempted in this audit.

[2026-11-17T07:38:18Z · sase-1t3.6.1.land--1] Implemented and verified indexed lookup landing repairs; audit recorded on parent phase file:explicit:68f0e0cdaf4f6ceee3b9927d. Focused Rust and PyO3 tests passed; primary check has one KNOWN existing import-budget failure and core check passed. Symvision clean. Approved follow-up dispositions are recorded on parent phase.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.6.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.6.1.land.md) | [sase-1t3.6.1](sase-1t3.6.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d201086`](https://github.com/sase-org/sase-core/commit/d20108657804cfc257342b0bfb4617ea8bc61a0f) | feat(agent-scan): add bounded named lookup selection | [sase-1t3.6.1](sase-1t3.6.1.md) | 2026-11-17 02:40:16 EST |
| sase | [`824fc24`](https://github.com/sase-org/sase/commit/824fc2445e33499872674f4a26fb4ad9bc672a34) | feat(agent-lookup): land indexed lookup resolution | [sase-1t3.6.1](sase-1t3.6.1.md) | 2026-11-17 03:35:12 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:ef][1] | Find child plan for indexed lookups parity rules | 2 |
| read-by | [agent:sase-1t2.8.1.land][2] | Check the parent epic status for archive failures | 1 |
| read-by | [agent:sase-1t3.6.1.1][3] | Need child epic DECISIONS for lookup-core phase | 3 |
| read-by | [agent:sase-1t3.6.1.2][4] | check epic decisions | 1 |
| read-by | [agent:sase-1t3.6.1.land--1][5] | Re-read the indexed lookup land bead before completion | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ef/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.8.1.land/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.6.1.1/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.6.1.2/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.6.1.land.md

<!-- sase:referenced-by:end -->
