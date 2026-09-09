# Bead: sase-xe.16.11 — Finish remote dispatch setup correctness and live acceptance

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.11

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xe.16.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.land.md) · **Assignee:** `sase-xe.16.11.land`
**Created:** 2026-09-09 04:38:25 EDT
**Plan:** [202609/remote\_dispatch\_landing\_remaining.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_landing_remaining.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/remote_dispatch_landing_remaining.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_landing_remaining.md

<!-- sase:links:end -->

## Description

Remote setup preserves discovery failures, activates enrollments through durable operations, uses Rust-owned shared policy, and has real fault and Athena-to-Apollo evidence sufficient to resume the interrupted sase-xe.16 landing.

## Notes

[2026-09-09T12:35:55Z · research.1p.final] DISCOVERED ISSUE: Independent live Apollo Fleet/Focus contract reproduction on 2026-09-09 08:28-08:35 EDT, SASE 27bbd2f4e4bcab9c364b175ad44c3fa24e13250d and reviewed core 7af26400fbca87eb70102c7082a1b029c65e310b. Authenticated hello and Serve work. ACE sends catalog limit 250 but the gateway caps 100; legal pages return 152 records (90 DONE) yet project_fleet_agents returns zero rows and no diagnostic because it ignores hosts[].payload.page.rows and hosts[].error. include_terminal is omitted; no continuation is consumed. Traversal-only projection yields 100 attempt-0 rows with missing provider/origin and a false count of 100 versus authoritative running=1. Raw worker hosts also fail the Rust count input schema. Additional lead finding: Focus sends logical_locators where FleetLogicalBatchRequestWire requires logical_keys; live equivalent requests fail with mismatched request_id versus resolving the known DONE record successfully. These block live phase sase-xe.16.11.5 and are absent from the current assigned repair scopes. Recommend explicit Fleet/Focus wire repair inside this epic before .5, with real ACE-request/worker-response regression coverage, terminal paging, authoritative counts, correct metadata/origin, and host-error visibility. Preserve current setup work and require known recent DONE plus active remote launch/follow/output/stop/restart evidence. No standalone task or dependency changes made. Consolidated evidence: research:202609/apollo_fleet_contract_repair/apollo_fleet_contract_repair.md; immutable snapshot file:explicit:42276af3c0f32fd66859f99d. Researcher A/B preserved unchanged alongside it.

[2026-09-09T12:51:37Z · sase-yt.land] DISCOVERED ISSUE from proposing bead sase-yt.2 note #1: On Athena on 2026-09-09, sase machine status apollo -j returns ok=false, state=error, message="machine alias is not configured", with empty endpoint/installation/provider because the loaded dispatch.machines map is empty. This is independent of sase-yt gateway supervision: both managed gateways are enabled/active, loopback-only, cross-tailnet healthy, and Apollo authenticated hello was separately proven. The linked chezmoi source home/dot_config/sase/sase_athena.yml has no dispatch entry. This is causally owned by this active remote-dispatch epic, especially phase sase-xe.16.11.5 canonical machine init plus authenticated status acceptance; ensure its live workflow durably creates/restores the apollo alias. /sase_new_task duplicate searches and recent-task sweep found no matching standalone task, so none was created.

[2026-09-09T13:29:45Z · 0ha] REPAIR SCOPE (supplements the existing Fleet/Focus discovered-issue note): The report recommends explicitly assigning one coherent cross-repository contract repair within this epic before live acceptance .5. Existing discovery/activation work does not itself assign these fixes. Put shared request validation, response normalization, diagnostics/freshness, and count aggregation in Rust core behind a thin Python binding; retain Textual row construction/rendering in Python and keep the transport-free core independent of the gateway crate.

Normalize the distinct real envelopes: catalog hosts[].payload.page.rows, followed-batch hosts[].payload.entries[].summary, and summary responses carrying counts/freshness rather than rows. Followed requests must use logical_keys. Fully map ResolvedAgentSummaryWire: labels.agent_label, provider, intent, host installation_id, project, enum-string lifecycle/liveness, freshness/observation time, capabilities, and original locators/revisions. content describes available content, not agent metadata.

Request pages <=100, include recent terminal records, and consume per-host cursors on demand; 250 may be an overall UI/cache bound but must not silently make later results unreachable. Fleet running counts must use authoritative payload.counts independently of catalog page/search filters; remote Focus counts use the complete bounded followed set with shared Rust semantics. Preserve unknown/stale host state and expose status/error plus payload freshness/partial state instead of swallowing errors or falling back to row counts.

Source: research:202609/apollo_fleet_contract_repair/apollo_fleet_contract_repair.md (2026-09-09 08:28-08:35 EDT research snapshot; supplemental guidance, not a new live reproduction).

[2026-09-09T13:30:23Z · 0ha] REGRESSION AND LANDING ACCEPTANCE (from the consolidated Apollo report): Existing UI/facade fixtures invent hosts[].summaries, mapping-valued liveness, and content metadata that disagree with the worker wire types. Passing those tests/screenshots does not establish live integration. Add coverage that drives ACE-generated requests through actual serialized worker/gateway envelopes, including mixed healthy/failed hosts, legal paging, active plus recent-DONE rows, readable names/providers and exact identity, completed follows outside page one, and authoritative counts unchanged by paging/filtering. Update affected fixtures, goldens, and fault benchmarks to the real shape.

After publishing/installing matching SASE/core builds and refreshing gateway, worker, AXE, and ACE processes, .5 should record live pane evidence for a known recent completed Apollo agent plus a new active launch, follow into Focus, output, stop, a second-page check, honest host failures, and recovery in the same ACE session after gateway restart. Preserve hidden-Fleet/zero-machine laziness and the navigation budget. Hello/health success or a newly launched active agent alone cannot establish these requirements; process restarts alone cannot fix the reproduced schema defects.

The snapshot's 152 catalog records (90 DONE) versus one logical running agent and zero occupied runner slots are historical evidence, not fixed expected values for a later run. The gateway covers active plus bounded recent records (recent limit 512, include_full_history=false); two-page success does not prove arbitrary archive history. Any full-history claim needs a tested history-query path. The report's earlier successful Apollo hello also does not supersede the later alias-configuration observation already recorded on this epic.

Source: research:202609/apollo_fleet_contract_repair/apollo_fleet_contract_repair.md; immutable report snapshot file:explicit:42276af3c0f32fd66859f99d. No implementation or live acceptance was performed while adding these notes.

[2026-09-09T16:15:27Z · sase-xe.16.11.land] LANDING AUDIT / REMAINING WORK: Read this epic and all four original epic notes, all five child beads and all sixteen original child note entries; read the linked plan and consolidated Apollo contract research using audited artifact reads. Verified core commits 0318b31, 06025ba, a6d40ba and SASE d015f48cb, 20c7b9804, b7c6bc006 against current source. Setup and follow-promotion policies/bindings/adapters, detailed discovery, shared activation, repair credential retention, tracked apply, setup guidance, bootstrap round-trip tests and actual benchmark overlap are implemented. Reopened .3 (fast connection refusal is not a successful healthy host; instance test fabricates the old locator) and .5 (automatic close contradicts explicit unmet live gate). No epic or linked plan is marked done.

SOURCE AND PROBE FINDINGS: worker RemoteHost ignores plan.tls; fast-host deadline test expressly asserts status != ok. New Python Fleet traversal handles rows and some metadata but still duplicates shared backend policy; the real count binding rejects raw worker hosts on alias and fallback swallows it. A followed DONE row inherited host-wide running=9 as Focus remote=9, partial=True at payload.freshness became projection.partial=False, and summary observed_at became None. One global cursor is broadcast across hosts and a hard three-page loop has no continuation. The original synthetic fleet_fixture and much coverage still use hosts.summaries and invented metadata. Target launch synchronously waits for agent_bridge launch_text before returning a settled receipt; controller uses the generic short request timeout, while source notes prove an agent started after its reply deadline and remained absent from the catalog. Recovery and same-session output/stop remain required.

INTEGRATION: Fetched origin/master equals HEAD b7c6bc006; inspected all SASE commits since epic creation (earlier than the first Python epic commit), plus core history from 0318b31 to 3baa689 (0.32.55). Queue unconditional/floor changes, star model completion/LSP, checkpoint evidence, usage/pager chrome, hidden-sidecar deadlines, and test-cost updates do not repair these gaps. Preserve queue/dispatch rejection, shared model alias/LSP parity, current core floor and the pytest_plugins benchmark fixture registration from f4ca78c0f. Later core release/model-shortcut commits remain compatible; republish and ratchet when new bindings are consumed. No outstanding base commits at audit time.

ALL PROPOSED FOLLOW-UP DISPOSITIONS: .3#1 TLS -> absorb into missing authenticated healthy-host proof; .3#2 merged Fleet panel/performance -> absorb into realistic fixture/navigation and machine-section integration, since it arises from epic Fleet rows and its stress contract (do not blindly set a local tribe). .5#5 Rust extraction -> mandatory epic backend-boundary repair, not optional debt. .5#6 late launch receipt/diagnostics -> mandatory reliable dispatch and live acceptance work. .5#7 missing launched catalog row/stop identity -> mandatory launch visibility/recovery and exact-instance management work; diagnose owner snapshot/cache/identity instead of assuming one cache-bust fixes it. No proposals were discarded; standalone tasks declined because all five belong to this active epic. /sase_new_task usage recorded; bug and all-type searches, complete recent-task sweeps and active-epic/related-phase inspection found no duplicate task. sase-ya is only documentation memory work, not a repair duplicate.

VERIFICATI

… and 748 more characters

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.11.land.md) | [sase-xe.16.11](sase-xe.16.11.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.1p.final][1] | Record the active epic ownership and current Fleet repair gap for the consolidated research | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.1p.final/README.md

<!-- sase:referenced-by:end -->
