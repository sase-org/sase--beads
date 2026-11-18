# Bead: sase-1tc.1.1 — Keep workflow data out of host command substitution

[Bead Pages](../README.md) / [sase-1tc.1](sase-1tc.1.md) / sase-1tc.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tc.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.1.md) · **Assignee:** `sase-1tc.1.1.land`
**Created:** 2026-11-17 11:31:49 EST · **Closed:** 2026-11-17 18:05:58 EST
**Plan:** [202611/cmdsub\_source\_provenance.md](https://github.com/sase-org/sase--plans/blob/main/202611/cmdsub_source_provenance.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/cmdsub_source_provenance.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-1th][2] | Closed epic whose 4b9513e3f4 landing introduced the always-copy pre-render behavior that made this test stale |

_Plus 5 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/cmdsub_source_provenance.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1th/README.md

<!-- sase:links:end -->

## Description

Fix sase-1tc.1 and sase-1sn while preserving authored commands, macro expansion, and Jinja value semantics.

## Notes

[2026-11-17T20:59:57Z · 1dn] DISCOVERED ISSUE: efc66a420b (phase sase-1tc.1.1.2) silently drops #research_swarm segments. Repro: expand_macro_swarms_with_metadata on a #research_swarm(...,image=true,...) prompt yields 6 segments (cdx cld grk mus gem final) at efc66a420b vs 8 (+image +linker) at parent 71f0060927; hit live on apollo as research.58/research.59 (6 agents each). Root cause: _marking_finalize in src/sase/macro/_jinja.py marks every {{ }} output, so a Jinja macro called inside {{ }} (research_swarm's {{ tree(lead_files) }}, whose body prints fences via {{ }}) is marked twice; GeneratedTextGuard.hide_marked_spans' non-greedy START(.*?)END regex pairs the outer START with an inner END, leaving NUL SJSMARK markers before the opening fence and after the closing fence. The closing fence is then read as an unclosed opener, hiding the last two --- separators from split_segments_protecting_fences, so the image and linker prompts are merged into the .final lead prompt. %if(should_run=...) itself evaluates correctly. Tested fix on a scratch copy: strip inner markers in _marking_finalize (text = str(value).replace(start, '').replace(end, '')) -> 8 segments, 0 stray markers. Suggested: regression test for macro-in-{{ }} round-trip and research_swarm(image=true) == 8 segments, plus fail loudly when SJSMARK/SASEDATA survives guard.unwrap. Second symptom, same commit, not fixed by that one-liner: sase macro expand on the same prompt fails with "Macro '#research' argument error: Argument 'suffix' expects word ... got '\x00SASEDATA_<nonce>_18\x00'" because validate_and_convert_args sees the guard token from #research(suffix={{ r.short }}). Report: research:202611/research_swarm_missing_image_linker_agents.md (file:explicit:c1798ebb9b8fdad85a57743d).

[2026-11-17T21:23:20Z · 1do] DISCOVERED ISSUE (beyond the research_swarm note above; found while planning its fix on be6adc20d0): efc66a420b's nested local-helper boundaries leak in two ways. (1) Security gap: command stdout minted inside a local helper is unwrapped to plain text when the nested process_macro_references_with_catalog call returns (its ephemeral guard unwraps at the end), so the outer first pass treats it as source and runs $(...) inside it. Repro in a human launch (SASE_PROMPT_AUTHORSHIP unset): catalog {main: Macro(content='#_h', local_macros={'_h': Macro(content='$(cat payload.txt)')}), echo: Macro(content='{{ _1 }}')}, payload.txt = '#echo($(touch pwn_local))'; process_macro_references_with_catalog('#main', ..., aliases_resolved=True, raise_on_error=True) creates pwn_local. The same flow through a global (non-local) macro stays literal. (2) Regression: typed local-helper args fed by a parent interpolation fail validation, e.g. main content '#_h(suffix={{ v }})' with _h input suffix: word raises "Argument 'suffix' expects word ... got '\\x00SASEDATA_<nonce>_0\\x00'", and untyped helper Jinja comparisons on such args see the token (works at parent 71f0060927). Both stem from nested helpers minting an isolated guard that can neither see nor keep hiding the parent guard's spans. The planned tale for the research_swarm fix covers same-guard (global macro) arg reveal only and leaves these to this epic.

[2026-11-17T22:04:27Z · sase-1tc.1.1.land] LAND AUDIT / FOLLOW-UP TRIAGE: Read all notes on this epic and its three closed phases, parent phase sase-1tc.1 and both linked plans. Audited Rust policy commit 1191f9a6 and Python commits efc66a420b/81656950c6. Current core pin c5e60d78575b50b8eefd1b2881e6fac2b8768f55 contains 1191f9a6; core policy/binding unchanged since that commit. Existing provenance/route suites pass 47/47 on HEAD 81656950c6, but local mocked probes prove the epic is incomplete. Local helper stdout #echo($(printf DATA_EXECUTED)) is executed by the outer source pass; parent interpolation into a typed local helper fails word validation on SASEDATA. Nested Jinja macro output leaks SJSMARK in both renderers. Also: escaped #echo(\$(printf ESCAPED)) executes; context=None top-level false Jinja branch executes printf FALSE; a set-block capture of {{ v }} compares unequal to ok because markers contaminate the value; unchanged parallel rendering has no pre-rendered mark and calls the executor twice. These are remaining epic work, not follow-ups. Active plan plan:202611/macro_guard_marker_leaks.md (1do, now testing) owns marker flattening/global typed args/clean traces but deliberately excludes local-helper custody and capture semantics; landing repairs must integrate its final result instead of overwriting it. No implementation edits made during this audit.

[2026-11-17T22:04:34Z · sase-1tc.1.1.land] FOLLOW-UP DISPOSITIONS (before proposing remaining-work tale): sase-1tc.1.1.2 note #1 late Jinja and note #2 directive extraction are DECLINED as separate tasks because efc66a420b removed the old protection: current _raw={{ missing_data_variable }} exits 1 in late preprocessing, and _raw=%model:injected_model\nresponse sets directives.model=injected_model and strips the data line. Both remain in this epic repair scope. sase-1tc.1.1.3 note #2 import-budget proposal is PARTLY EPIC-CAUSED: its clean base efc66a420b already includes phase two. Fresh measurement at 81656950c6 is 11,865,876 vs cap 11,828,610; pre-phase-two 71f0060927 is 11,828,809. Own +11,178 bytes (cmdsub_source 4,919; source_render 1,158; processor_engine 2,336; processor_render 1,493; _jinja 682; processor 298; preprocessing 292) must be removed from eager startup. Out-of-scope +19,043 compact adapters and +6,846 memory query were routed through sase_new_task causal-epic branch to DISCOVERED ISSUE notes on sase-1t3.10.1 and sase-1t3.11.1. Reviewed same-type CI task search and last-week sweep, active epics and relevant children; old task sase-1ic concerns split-sensitive module counting fixed by the normalized-footprint metric, so it is not corroborated for this real new eager-code growth. No duplicate task created or budget raised. Pre-phase-two residual 199 bytes over the cap is unrelated and does not excuse our +11,178 growth; later verification must attribute any residual with independent clean-base evidence.

[2026-11-17T22:04:40Z · sase-1tc.1.1.land] INTEGRATION AUDIT: Fetched origin/master; it equals HEAD 81656950c6. Since creation and Rust phase 1191f9a6, reviewed nine non-epic commits: viewer startup/video/async/cache 487825956a bfa60324a6 898eb8ffa5 5b4e61bfa7 f2fb7fb6b5; targeted artifact queries 8a6451068e; stranded count/filter 71f0060927; memory query 1c626f39e5; compact rows be6adc20d0. No new prompt render route or conflicting cmdsub implementation there; import-growth integration is captured in prior notes, and later core pin contains our binding. Current epic-symbols query is empty. The marker-fix tale is still in progress outside this epic; refresh and integrate at implementation. Remaining repair must close this epic normally, run symvision, mark plan:202611/cmdsub_source_provenance.md done, then record TASK RESOLVED: sase-1sn on phase sase-1tc.1 and close only that phase after verifying scope. Leave sase-1tc and task sase-1sn to the outer lander.

[2026-11-17T22:23:09Z · 1dr] DISCOVERED ISSUE: Implementing plan:202611/macro_guard_marker_leaks.md on 81656950c6 with the approved guard.mark flattening fix, extra case-filter probes show a remaining capture-value semantic defect: {% filter title %}{{ "hello world" }}{% endfilter %} renders "hello World" with a guard versus "Hello World" without one; {% filter capitalize %}{{ "HELLO" }}{% endfilter %} renders "hello" versus "Hello". Reproduced through _render_jinja2_template with GeneratedTextGuard and unwrap. The leading interpolation marker consumes the case filter's first-word/first-character behavior; flattening prevents residue but cannot restore the intended casing. This belongs with the epic's capture-semantic/compiler repair (note #3), beyond the approved marker-leak tale. Same-type and all-type task searches and last-week sweeps found no duplicate; no new task created.

[2026-11-17T23:00:53Z · 1dr--1] VERIFICATION / INTEGRATION: plan:202611/macro_guard_marker_leaks.md is implemented with shared guard.mark flattening in both renderers, same-guard argument reveal and local-helper re-hide, clean trace evidence, and residue rejection at swarm/preprocessing boundaries; submitting it through host completion now. All 41 new regression cases and the prior 1491-test macro regression suite passed. Final named check b1c3f6c41b279b1a4a136d2df295cc1f passed every lint stage and 61781 tests with 18 skips; exit 1 has exactly two independently KNOWN failures and verdict no_new_failures. The import-footprint failure remains 11867137 normalized bytes versus 11828610 cap. This marker fix adds code on the already eager macro path, so integrate it into the import-deferral work owned in note #4; the KNOWN label does not mean it adds no footprint. The other failure is the unreviewed compact running-home-marker release site introduced by be6adc20d0, routed with evidence to sase-1t3.10.1. Evidence: file:monitor-stage:test-scoped-1240586-1794956158202390346-8949acab. Existing capture/case-filter semantic limitations and nested-helper custody remain your epic scope; no new task created or budget raised.

[2026-11-17T23:05:58Z · sase-1tc.1.1.land] Fixed remaining provenance regressions: nested local/global guard custody (shared guard, no midway unwrap, token-local local expansion), escaped carry via guard tokens (no early unescape), reveal-before-validation with re-marking, trace unwrapping, Jinja AST protection (final outputs marked via __protect, captures clean for comparisons/length/slicing, TemplateData source stays executable, FilterBlock data protected), always-render top-level Jinja at source boundary (false branches execute nothing), directive extraction on protected text (data %model ignored), late UndefinedError preserved as literal data, parallel pre-rendering always marked with directives extracted on protected text (macro-produced

… and 1207 more characters

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.1.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.1.1.land.md) | [sase-1tc.1.1](sase-1tc.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4b9513e`](https://github.com/sase-org/sase/commit/4b9513e3f4775d753cf48d1c8e67699f1abb8e07) | feat(macro): finish command-substitution provenance landing | [sase-1tc.1.1](sase-1tc.1.1.md) | 2026-11-17 20:47:31 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1dn][1] | Check whether the in-progress epic that produced efc66a420b owns the macro-guard regression | 1 |
| read-by | [agent:1dr--1][2] | Confirm provenance epic owns remaining import deferral and integrate verification evidence for its approved marker-fix dependency | 1 |
| read-by | [agent:ex.f0][3] | Need the epic scope: cmdsub child epic that landed efc66a420b | 1 |
| read-by | [agent:sase-1tc.1.1.1][4] | Need parent epic DECISIONS and design | 1 |
| read-by | [agent:sase-1tc.1.1.2--1][5] | Check ancestor status before deciding on reopen | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1dn/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1dr.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ex.f0/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.1.1.1/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.1.1.2.md

<!-- sase:referenced-by:end -->
