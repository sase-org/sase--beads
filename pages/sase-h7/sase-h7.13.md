# Bead: sase-h7.13 — Close the gate-input epic's own gaps and land it

[Bead Pages](../README.md) / [sase-h7](README.md) / sase-h7.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-h7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.land/README.md) · **Assignee:** `sase-h7.13.land`
**Created:** 2026-08-07 23:11:52 EDT · **Closed:** 2026-08-08 00:45:13 EDT
**Plan:** [202608/gate\_inputs\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_inputs_landing.md)

## Description

The gate input-collection epic lands green: a custom gate whose option declares a raw required property is creatable and answerable again instead of rejected at creation, sase-telegram's custom-gate suite passes against this repo's validation, the conformance matrix asserts the mobile leg the epic actually shipped, submitted secrets stay out of journal.jsonl, and the epic's two input-enforcement layers agree.

## Notes

[2026-08-08T04:45:13Z · sase-h7.13.land] VERIFIED (steps 1-2). All 5 phases closed; every child note read and cross-checked against source and commits. h7.13.1 (f2c6f1889): _client_producible_input now builds the probe from input_schema.properties for options with no declared inputs, and _raw_schema_failure fails closed only on a required name nothing renders a control for; options with inputs keep full-probe schema validation. h7.13.2: landed in sase-telegram as b550ad2 (presentation.title on _custom_spec); confirmed present at that repo's HEAD 19167fb, and _hitl_spec's title-less presentation is kind=hitl so it is correctly unaffected. h7.13.3 (0a13ffed4): redact_secrets_in_result on the journal, (?![\\s\\S]) anchors on the word/agent/line/path fragments, recorded_rejection widened to every exception under 'adapter_rejected'. h7.13.4 (86a54a674): mobile Surface declares CAP_OPTION_INPUTS, _submit_via_mobile threads option_inputs, PENDING_CAPABILITY_PHASES holds standing reasons for the two real gaps, and test_every_surface_gap_states_why_it_cannot_submit guards that no deferral names a bead.

INTEGRATION. Only three non-epic commits landed after this epic bead was created (2026-08-07 23:11): 8b224aed4 and 20752def2 (toobig file splits of gate_branch_controls.py and plan_approval_modal.py) and 315a5f9ff (bead SDD materialization). All three are already on top of, or independent of, this epic's code; plan_approval_gate_data.HOST_COLLECTED_PROPERTIES is a deliberate per-screen superset of DEFAULT_HOST_COLLECTED_PROPERTIES, not a duplicate. Local master == origin/master, so no base-branch drift.

EPIC WORK FINISHED DURING LANDING (2 gaps, both epic-caused, both fixed here, uncommitted in the working tree per the no-commit-without-request rule):
1. Submitted secrets were still shipping in response.json. The epic plan's invariant 5 and docs/notifications.md both promise a secret: true value appears in response.json as {"$redacted": true}, and h7.13.3 delivered that for journal.jsonl only. Reproduced: an echo command's result put 'hunter2' in response.json's option_results in plaintext, and the conformance matrix's own secret_field case asserted that leak. The legacy shared 'input' key leaked the same value a second way. Fixed by scrubbing the result once and using it for both option_results and the journal (result_digest still covers the raw result), and by adding redact_shared_input for the shared value. secret_field now proves both halves from one result (token_len 7 could only come from the unredacted stdin; echoed is redacted), and the cli/mobile secret tests were asserting the leak too and now assert redaction.
2. tests/ace/tui/visual/snapshots/png/frontmatter_panel_raw_diagnostics_120x40.png was stale because of this epic's phase sase-h7.3: 8e52e4638 added InputType.ENUM, which appended ', enum' to the frontmatter panel's expected-types diagnostic. The h7.13 plan called this out of scope; the sase-h7 bead note proves otherwise, so it was epic work. Golden regenerated (only that one file changed; confirmed the diff is exactly the ', enum' text).

GATE. 'just check-full': every lint gate green, 1 failed / 27555 passed / 10 skipped -- identical to the clean-master baseline I measured before touching anything. The single failure is tests/test_content_layout.py::test_project_home_and_chezmoi_named_paths_are_canonical (schema_version 2 vs 1), caused by active epic sase-hb, not this one. 'just test-visual': 561 passed / 1 skipped / 1 failed, down from 2 failed on clean master; the remaining failure is test_agents_slow_tool_calls_fold_levels, which I confirmed pre-exists on a clean tree.

FOLLOW-UP OUTCOMES (every PROPOSED FOLLOW-UP collected from the children, plus the plan's own out-of-scope list):
- test_content_layout schema_version drift -> DISCOVERED ISSUE note on active epic sase-hb, whose phase sase-hb.1 bumped CONTENT_LAYOUT_SCHEMA_VERSION to 2 in sase-core 682d48f. No task created, per the active-epic rule.
- ACE commits-pane xdist flake -> +1 on task sase-ct (now +29) and a DISCOVERED ISSUE note on active epic sase-h8, which is chartered to retire that class. While verifying I found a second, sharper member: the visual lane's test_agents_slow_tool_calls_fold_levels fails 3 of 3 full 'just test-visual' runs and passes in isolation -- deterministic under parallel, so the cheapest reproducer in the class so far. Both beads carry that correction. No task created.
- sase commit's before-commit hook closing a phase bead mid-flight (reported by both h7.3 and h7.13.5, on a sase-core commit and a plans-sidecar commit) -> new task sase-hc (medium, ready).
- sase-telegram's 3 remaining test_custom_gates.py failures (bead_snooze registry gap; stale keyboards from closed phases h7.2/h7.11) -> new task sase-hd (small, ready).
- Single-phase workspace materializes a plan file but not its PARENT chain, so 'sase plan links validate' fails and 'repair' does not fix it -> new task sase-he (medium, ready).
- The frontmatter PNG golden, which the plan told the land agent to file rather than fix -> DECLINED as a follow-up and fixed here instead, because the sase-h7 bead note establishes phase sase-h7.3 as its cause.
- 'A land phase cannot close its parent epic' (hit again by h7.13.5) -> already filed and triaged as sase-gf, closed canceled 2026-08-06. Not refiled.

[2026-08-08T04:47:24Z · sase-h7.13.land] Publication check by commit finalizer: verification and integration recorded in the prior close note (all 5 phases closed and cross-checked against source/commits; only 3 non-epic commits since epic start, all already integrated; two epic-caused gaps fixed: submitted secrets now redacted in response.json option_results and the legacy shared input key, plus the stale frontmatter_panel_raw_diagnostics PNG golden caused by phase sase-h7.3).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.13.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.13.land/README.md) | [sase-h7.13](sase-h7.13.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ed50d45`](https://github.com/sase-org/sase/commit/ed50d45ee67018f5a77bef87b8cabf6bbed1af9b) | fix(gate): keep submitted secrets out of response.json too | [sase-h7.13](sase-h7.13.md) | 2026-08-08 01:00:03 EDT |
| sase--plans | [`sase--plans@5701a7d`](https://github.com/sase-org/sase--plans/commit/5701a7d64bb470e9d625e4ae1cfbcd71c26487c2) | docs(plan): mark the gate-input landing plan done | [sase-h7.13](sase-h7.13.md) | 2026-08-08 01:01:31 EDT |
