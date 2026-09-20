# Bead: sase-133.5.4 — Prove production and live cross-machine parity

[Bead Pages](../README.md) / [sase-133.5](sase-133.5.md) / sase-133.5.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-133.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-133.land.md) · **Assignee:** `sase-133.5.4` · **Size:** medium
**Created:** 2026-09-19 08:06:13 EDT
**Plan:** [202609/remote\_parity\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_parity_landing_repairs.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:0fabc9428a2dc8170edcfb5a | attached via sase artifact create --bead |
| related | file:explicit:6881b918e8940383cbaa09e7 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

parity-acceptance: exercise the production path, validate ordered screenshot driving, deploy consistent builds, and save reviewed parity evidence from both hosts.

## Notes

[2026-09-20T13:47:43Z · sase-133.5.4] Partial, NOT closed. Done (uncommitted in workspace): (1) rendered-row parity oracle test_owner_and_catalog_render_equal_rows_and_nested_shell_counts (current + compact-index) in tests/ace/tui/test_owner_facts_oracle.py compares status, chips, stamp and nested-shell count between real owner loader and real catalog; passes. (2) tmux has no 'slash' key name (verified: -p slash types the letters); fixed docs/ace.md and parser_screenshot.py epilog to '-p / -w INSERT --type machine:apollo -w machine:apollo -p enter' plus help test; ordered driving verified locally and --host apollo (both show machine:apollo 0/0, remote_sase_version 0.17.1+957.g6087c0a8e). Focused tests pass. NOT done: live acceptance. sase machine status apollo still reports real skew (gateway 0.34.66 vs local core 0.34.67, fleet v4 vs v5); athena is an editable dev install, so deploying consistent builds on athena+apollo, restarting gateway/AXE, and capturing equal settled owner/viewer PNGs needs these changes landed and released first; just check-full and saved artifacts also not run. Screenshots at /tmp/local.png and /tmp/apollo.png are empty-filter captures, not parity evidence.

[2026-09-20T15:23:29Z · sase-133.5.4] Live acceptance NOT complete; bead intentionally left open. Consistent builds already deployed (verified 2026-09-20): athena and apollo both sase 0.17.1+957.g6087c0a8e + sase-core-rs 0.34.67, gateways/AXE restarted; sase machine status apollo -> gateway 0.34.67, fleet contract schema v5, capability v1, version_skew [] (no false skew). LIVE PRE-FIX CAPTURES (owner=apollo TUI, viewer=athena TUI filtered machine:apollo, both 120x40): owner file:explicit:0fabc9428a2dc8170edcfb5a, viewer file:explicit:6881b918e8940383cbaa09e7. They FAIL parity: viewer lacks every completed family made only of shells (sase-12y.2/.3/.land, sase-12o.land, sase-zr.7.1, .7.2, sase-zr.7.1.1*.land, ...), so family x N, [Dn] counts, shell chips, done rows and clan members differ; catalog served 31 of 84 owner named identities. ROOT CAUSES FOUND VIA REPLAY OF apollo REAL DATA: (1) sase-core fleet_presentation dropped every terminal concrete shell unless a non-member root record was in the window, but modern plan-chain families have NO root record (the --plan shell has agent_family_role root and no parent), so completed families vanished; the phase-1/2 fixtures always wrote a synthetic root record, hiding it. (2) a record holding only side files (continuation_stage_diagnostics.jsonl, no meta/done/running) was served as a permanent RUNNING/unknown row the owner loader never builds (20260919114347). FIXES (uncommitted here, for host finalizer): sase-core fleet_presentation.rs + fleet_catalog.rs add candidate fields family_anchor (concrete shell with no tracked parent presents its family inside the 7-day window; unanchored orphans stay excluded, so sase_gateway orphan test still passes) and lifecycle_evidence (marker-less records excluded); new Rust unit tests + gateway test root_less_completed_plan_chain_family_is_presented_through_its_plan_shell; core just check green (exit 0). Primary: owner_roster_fixture now writes the production shape (chain--plan root-role/no-parent + chain--mon + chain--1, plus a side-file-only dir), takes a pinned now, and uses a valid tribe name; roster oracle now compares signatures of rows projected through project_fleet_agents instead of a catalog-only nested heuristic; facts oracle covers chain shells; new fixed-clock visual test agents_fleet_production_families_120x40 built from the REAL assembled catalog of the fixture (pinned installation id, revisions normalised) with new golden, reviewed, determinism-verified; docs/remote_dispatch.md documents the window/anchor rule. POST-FIX REAL-DATA REPLAY on apollo (fixed extension loaded from /tmp, apollo install untouched): catalog serves 84 of 84 owner named identities (was 31), 0 extra; roster-oracle signatures on apollo home: visible nodes 11=11, panels @default 4=4 and epic 7=7, nested named shells equal; only remaining owner-only nested rows are 146 unnamed workflow step rows (not agents). Statuses now TESTED/EPIC CREATED/EPIC APPROVED present. Post-fix viewer render artifact: file:explicit:5ce90c912a66753c9dc58aa7. VERIFIED: oracle tests 33 pass; focused set 56 pass; test-scoped 43687 pass with only the 4 known baseline failures (import budget, 2x capacity_gate, lazy_tier2 reconcile); lint: ruff/keep-sorted/flags/pyscripts/waits/changelog/terminology/toobig green, mypy (20 errors in ace_tmux*.py) and symvision (28 unused, none in touched files) red at baseline exactly as in sase-133.5.2 note #3. just check-full NOT run (agent default is just check, which is red at baseline; no rendering source changed). REMAINING TO CLOSE THIS PHASE (needs steps outside an agent turn): land the primary + sase-core commits, let sase-core release (expected 0.34.68), run the normal update flow on athena and apollo, restart gateway/AXE, confirm sase machine status apollo has no skew, recapture both views with -p / -w INSERT --type machine:apollo -w machine:apollo -p enter at the same pane size (owner list is viewport-bounded: 19 agents at 120x40 vs 37 at 150x110, so sizes must match), compare identities, save PNGs as artifacts. Screenshot ordered driving verified earlier (local and --host apollo).

[2026-09-20T15:24:15Z · sase-133.5.4] PROPOSED FOLLOW-UP: three fleet PNG goldens drift on the pristine tree (agents_fleet_followed_partial_offline_120x40, agents_fleet_keyboard_focus_narrow_82x28, agents_fleet_remote_tribe_families_120x40) — confirmed by stashing all changes and running just test-visual on the fleet module; view mode file->none, mac.ci elapsed 73h->0s, a new @visual panel, and families rendering fold-expanded with a neighbors header; not approved or regenerated here because it needs a product decision on the fold default

[2026-09-20T15:24:44Z · sase-133.5.4] PROPOSED FOLLOW-UP: remote family x N and shell chips still differ from the owner because the catalog does not serve workflow step rows (owner 0s.f0 x7 vs viewer x2, WAITING marker >1 and the [agent] tag also differ on standalone rows) — decide whether to publish bounded step counts or document x N as shell-only; live apollo shows 146 unnamed step rows owner-only

[2026-09-20T15:25:12Z · sase-133.5.4] PROPOSED FOLLOW-UP: apollo real ~/.sase holds ~11 dead lane--gate artifacts (parent 20260812120000, dated 2026-09-14 to 2026-09-20, latest 09:31) that match a gateway/fixture test family — some test or tool appears to write fixture data into a real SASE home; find and isolate it

## Dependencies

- **Depends on:** [sase-133.5.2](sase-133.5.2.md) ✓ · ⧖ 2026-09-19
- **Depends on:** [sase-133.5.3](sase-133.5.3.md) ✓ · ⧖ 2026-09-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-133.5.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-133.5.4/README.md) | [sase-133.5.4](sase-133.5.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`52b0283`](https://github.com/sase-org/sase/commit/52b0283947e67c25ac4b155c2ba138e5575f38e1) | test(fleet): add rendered-row parity oracle and fix screenshot slash key examples | [sase-133.5.4](sase-133.5.4.md) | 2026-09-20 09:49:11 EDT |
| sase | [`e99bd48`](https://github.com/sase-org/sase/commit/e99bd48ac4f8bbff3c7bfea89df34dd16d847df0) | test(fleet): run the parity oracle on the production family shape and add a fixed-clock production-derived visual | [sase-133.5.4](sase-133.5.4.md) | 2026-09-20 11:27:07 EDT |
