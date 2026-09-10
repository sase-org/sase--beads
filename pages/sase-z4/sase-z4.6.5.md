# Bead: sase-z4.6.5 — Finish weighted-capacity acceptance

[Bead Pages](../README.md) / [sase-z4.6](sase-z4.6.md) / sase-z4.6.5

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-z4.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.land.md) · **Assignee:** `sase-z4.6.5.land`
**Created:** 2026-09-10 13:23:40 EDT
**Plan:** [202609/weighted\_capacity\_final\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_final_acceptance.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/weighted_capacity_final_acceptance.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_final_acceptance.md

<!-- sase:links:end -->

## Description

Weighted capacity uses authoritative durable lineage end to end, passes integrated lifecycle acceptance, and ships with verified published package floors.

## Notes

[2026-09-10T20:36:01Z · sase-z7.land] DISCOVERED ISSUE: stale agents-pane PNG goldens from the weighted capacity status strip are still unfixed and keep `just test-visual` red on clean master. Full evidence is on the root epic sase-z4 (note added 2026-09-10 by the sase-z7 land agent): 44 failed / 12 passed across a fixed 12-file agents-pane subset at HEAD 1ef9c092e, every diff confined to the status-strip row where the goldens still expect '[0/10 running' and the render now emits '0.0/10.0 [0 running'. Origin is sase-z4.4's commit 81064c144, which added _append_capacity_prefix without regenerating any goldens; sase-z4.6.3's cceed09a9 refreshed only 3 and added 2. Flagging it here because this is the active epic finishing weighted-capacity acceptance: whoever settles the final capacity-strip text should regenerate the corpus deliberately (inspecting the PNGs) in the same change, rather than leaving a bulk --sase-update-visual-snapshots for an unrelated agent.

[2026-09-10T21:37:39Z · sase-z4.6.5.land] LANDING AUDIT, epic NOT closed (sase-z4.6.5.land, 2026-09-10, at master HEAD 63a5dbef1).

VERIFIED COMPLETE (read the source, not just the notes):
- admission-authority (3260f6a42). Rust really is authoritative now. _serial_family_owner_key
  and _active_serial_claim are gone from the whole tree; the candidate travels as the Rust
  request's own `candidate` field (runner_slot_candidate_record / _admission.py) instead of
  being merged into records; _require_candidate_decision fails closed and raises on an
  "invalid" decision; _publish_claim_ownership writes queue_weight, queue_weight_explicit,
  and runner_claim_owner_key under the runner-slot lock BEFORE claim() exposes work; and
  capacity_only=True is live in _RUNNER_SLOT_SCAN_OPTIONS. runner_claim_owner_key propagates
  through gate_shell/member.py, monitor/member.py, run_agent_directive_metadata.py, and
  run_agent_helpers_artifacts.py. 398 lines of lineage regressions in
  tests/test_run_agent_runner_slot_lineage.py.
- integrated-acceptance items 1 and 3 (788c63e28), in tests/fakey/test_runner_slots_e2e.py:
  test_fractional_fakey_agents_fill_capacity_exactly_and_live_reload_allows_heavy,
  test_explicit_zero_runner_priority_and_weight_survive_real_parking, and
  test_installed_research_swarm_quarter_weights_fill_one_fakey_capacity_unit.
- published-floors item 1 (0444bac58). tools/validate_sase_core_rs behaviorally validates the
  weighted-capacity surface, with the phase's own clean-venv proof that real PyPI
  sase-core-rs==0.33.0 fails all three new contract checks.

VERIFIED INCOMPLETE:
- integrated-acceptance item 2 (weight-2 monitor/gate lifecycle) was NOT delivered. 788c63e28
  added exactly three tests and touched one file. The only monitor case in that suite is the
  pre-existing test_fakey_monitor_holds_capacity_across_handoff_and_followup, which the epic
  plan had already named as inadequate; its own comment still says it simulates the monitor
  shape with a bare live pid "instead of driving the full monitor subsystem", and it runs at
  default weight 1.0. Gate routes, cancellation, failed startup, timeout, and crash are
  uncovered.
- integrated-acceptance item 4 (one-snapshot runtime/CLI/TUI parity) was NOT delivered. No
  test compares runtime admission, `sase agent list -j`, the ACE capacity header, queue
  ranks/blockers/details, badges, and filtering/folding against one shared snapshot.
- published-floors items 2-5 are NOT done and are externally blocked; see the correction I
  added to sase-z4.6.5.3.

INTEGRATION DEFECT THIS EPIC CAUSED, still unfixed: sase-core-revision.txt pins
270e50168391d38a32083f12ebac5afda0a8247d, which predates the core commit carrying the
agent-scan runner_claim_owner_key wire field, the scanner lineage lookup, and
AGENT_ARTIFACT_INDEX_SCHEMA_VERSION 27. At the pinned revision runner_claim_owner_key exists
only in crates/sase_core/src/runner_capacity.rs and agent_scan/index.rs still declares 26,
while this repo's src/sase/core/agent_scan_wire_records.py now asserts 27 and consumes the
wire field. The pin was last moved by unrelated commit 1bfd9f0a1 seven minutes before
3260f6a42 landed; the phase agent rebuilt from its checkout locally, said so in its note, and
nothing durable followed. This is not cosmetic: CI's master gate and PR CI both build the core
wheel from this file and then run tools/check_sase_core_rs_bindings, and
`just ratchet-core-revision --report-only` independently agrees the pin should move. Left for
the child epic's core-pin phase so it gets a real cold-build proof rather than a blind bump.

REVIEWED COMMITS THAT LANDED DURING THIS EPIC (13 between 13:23 and 17:21, excluding this
epic's own three): 755ef4a7b, abdcb86d6, 140c8e42f, 93789035b, b8a4b9003, f5a3f5c99, f22339c18,
1bfd9f0a1, 1ef9c092e, 811700bc3, 16001bb36, 37b32cfde, 63a5dbef1. Only two interact with this
epic's feature, and both are already accounted for: 1ef9c092e (compact provider usage window
badges) shifted the same top-bar/status-strip region the capacity prefix renders into, which is
folded into the child epic's capacity-visual-corpus phase; and 1bfd9f0a1 is the commit that
left the core pin stale, above. The rest are artifact-link, TUI-split, pager, logs, and
agent-index work with no weighted-capacity surface.

PROPOSED FOLLOW-UP DISPOSITIONS (all five collected from child beads):
1. sase-z4.6.5.1 #1 (5 pooled-alias failures) and #3 (2 test_workflow_executor TestShouldHitl
   failures) -- CORROBORATED, not filed new. Both are the same defect as closed task sase-q4,
   which named the identical files and the identical root cause (model/provider resolution
   silently falls back to the launch-default model) and was closed 2026-08-20 as obsolete. The
   phase agents' 2026-09-10 stash-verified reproductions on clean origin/master are entirely
   after that close, so the +1 promoted sase-q4 back to READY.
2. sase-z4.6.5.1 #2 and sase-z4.6.5.2 #1 (feature-flag lint gate blocked by live flag bead
   sase-z0 with no registry definition for key link_events) -- ROUTED, not filed new. Already
   recorded as DISCOVERED ISSUE #1 on active epic sase-yy.8, which owns link-event cutover and
   created sase-z0 via sase-yy.4. I appended our two independent reproductions plus the detail
   the other reporter lacked: check_feature_flags rule 8 escalates from warning to error once
   the landing grace expires, and `just validate`'s static --static pass stays clean, so only
   the live-bead rule is red.
3. sase-z4.6.5.1 #3 (tests/sdd/test_artifact_link_derivation.py::test_a_second_pass_over_the_
   same_documents_is_idempotent, fails only under the full parallel lane, passes in isolation)
   -- FILED as task sase-ze (flake, large, ready). Filed node-specific rather than as a +1
   because sase-ct is a retired umbrella whose close reason forbids corroboration.
4. sase-z4.6.5.2 #2 (stale symvision epic symbols UsagePeekSnapshot,
   cached_usage_display_snapshot, cached_usage_indicator_projection whitelisted under closed
   bead sase-z7.3) -- DECLINED, already resolved. The Justfile's _lint-symvision recipe now
   carries no --epic-symbol arguments at all and `sase bead epic-symbols sase-z4.6.5` reports
   none, so sase-z7's landing cleaned this up. Nothing left to file.
5. sase-z4.6.5.3 (release-plz Cargo packaging blocker) -- DECLINED as a new bead, and I agree
   with that phase's reasoning. It is live on sase-xe.16.11.7.14.3; a duplicate would fragment
   ownership of one shared fix.
DISCOVERED SEPARATELY during this landing: `sase artifact link add` is silently failing on this
host (prints an error, exits 0, records nothing) because the hidden plans clone holds 4
stranded "persist link events" commits. Recorded on sase-yy.8; it cost sase-ze its two typed
related links, which I preserved as a note on that bead instead.

WHY THE EPIC STAYS OPEN: three of the parent plan's contract items are unmet (integrated-
acceptance 2 and 4, published-floors 2-5), the core pin is stale in a way that breaks a clean
provision, and `just test-visual` is still red on clean master from the capacity strip this
epic's feature owns. Proposing a child epic under sase-z4.6.5 with phases core-pin,
monitor-gate-acceptance, snapshot-parity, capacity-visual-corpus, and published-floors. This
landing resumes when that child lands. `sase bead epic-symbols sase-z4.6.5` is clean, so
nothing is blocking the eventual close but the work itself.

VERIFICATION LIMIT, stated plainly: I ran no test suite. The repo .venv resolves sase_core_rs
to an editable path with no compiled extension present, so every just gate on this host dies at
import with "sase_core_rs is not importable in this environment"; the cargo target directory is
empty, so restoring it is a cold Rust build. Every claim above is from reading source, git
history, bead records, sase-core's git state, PyPI, and GitHub Actions run logs -- not from a
green run. The child epic's core-pin phase is written to establish that build first.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.5.land.md) | [sase-z4.6.5](sase-z4.6.5.md) | 0 |
