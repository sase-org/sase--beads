# Bead: sase-1t3.6.1 — Indexed agent name, session, clan, and dismissed-bundle resolution

[Bead Pages](../README.md) / [sase-1t3.6](sase-1t3.6.md) / sase-1t3.6.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.6.md) · **Assignee:** `sase-1t3.6.1.land`
**Created:** 2026-11-16 08:12:22 EST
**Plan:** [202611/indexed\_agent\_lookups.md](https://github.com/sase-org/sase--plans/blob/main/202611/indexed_agent_lookups.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/indexed_agent_lookups.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 4 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/indexed_agent_lookups.md

<!-- sase:links:end -->

## Description

Preserve agent lookup results while removing archive-wide work from authoritative hijack resolution and achieving warm resolution below one second on athena.

## Notes

[2026-11-16T20:15:56Z · sase-1t2.8.1.land] DISCOVERED ISSUE evidence for the sase-1t3.6.1.2 PROPOSED FOLLOW-UPs #1/#2, from the sase-1t2.8.1 land agent: (a) the fakey hijack e2e failure (test_hijack_reload_escalate_inherits_both_repos_through_finalizer, AttributeError is_agent_session_container_row) was caused by sase-1t2.8.1.5 (mirror_hijack_overlays_to_containers) and is fixed in the sase-1t2.8.1 landing, so you can drop it from your list. (b) On HEAD 8a1b84b096, the wrapped check run b8effd9f5a0f125e125085a356ac012f escalated to the full suite (core-identity-changed). Triage labeled 10 failures KNOWN (witness 55cfb8cb24b0af9b95e01b1320ce003c) and 1 FLAKY: test_agent_search_archive_cli_matches_shared_corpus_order, test_tui_list_order_matches_cli_identity_order, five tests in test_agent_archive_column_real_corpus.py, two in test_agent_archive_corpus_facade.py (one of them FLAKY), test_twenty_launch_agent_monitor_cycles_keep_only_local_authored_text, and test_provider_drain_e2e_relaunches_stranded_agent. The drain test also fails alone on clean HEAD with a short TMPDIR. Its drain payload is reason=nothing_to_drain, and the second agent 'second-fakey' resolves as reason=not_found. That is a name-lookup miss, not a HijackLatchedError refusal, so it points at the indexed find_named_agent/lookup_agent_artifacts path rather than the hijack latch.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.6.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.6.1.land/README.md) | [sase-1t3.6.1](sase-1t3.6.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:ef][1] | Find child plan for indexed lookups parity rules | 2 |
| read-by | [agent:sase-1t2.8.1.land][2] | Check the parent epic status for archive failures | 1 |
| read-by | [agent:sase-1t3.6.1.1][3] | Need child epic DECISIONS for lookup-core phase | 3 |
| read-by | [agent:sase-1t3.6.1.2][4] | check epic decisions | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ef/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.8.1.land/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.6.1.1/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.6.1.2/README.md

<!-- sase:referenced-by:end -->
