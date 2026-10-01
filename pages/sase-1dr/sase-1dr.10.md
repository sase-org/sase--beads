# Bead: sase-1dr.10 — Cross-file memory changes feed

[Bead Pages](../README.md) / [sase-1dr](README.md) / sase-1dr.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3o.md) · **Assignee:** `sase-1dr.10` · **Size:** medium
**Created:** 2026-09-30 19:09:35 EDT · **Closed:** 2026-10-01 09:51:51 EDT
**Plan:** [202609/memory\_history.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history.md)

## Description

changes-feed: running `sase memory history` with no selector opens a pager feed. It has one section per day. Each changeset lists its authored subjects as labels that open subject@version in the diff view. Generated consequences fold under their cause, regen-only changesets collapse into an expandable count, and home changes interleave with a ⌂ tag. `r` resyncs the feed. Add visual goldens.

## Notes

[2026-10-01T13:50:50Z · sase-1dr.10--1] PROPOSED FOLLOW-UP: just check base failures reproduce on clean tree (12 FAILED incl test_memory_log_json_id, test_memory_help, test_show_images, kind_coverage, config_schema_repositories, contract_manifest, force_reuse rejection x2, partial_launch_cleanup, artifact_directory_audit, axe_runner_started_at home_mode, tui app_import_budget; plus symvision KNOWN owner_ref/StarterResolution/HandoffSubmitResult and import ERROR test_agent_header_panel) - unrelated files untouched by this phase

[2026-10-01T13:51:13Z · sase-1dr.10--1] PROPOSED FOLLOW-UP: full-suite force_reuse consume/registry fanout+wipe+parse failures are order-dependent flaky (pass in isolation with and without phase changes)

[2026-10-01T13:51:51Z · sase-1dr.10--1] changes-feed done: feed_document builder with day sections, versioned subject labels to diff view, folded consequences, regen-only expandable count, home ⌂ tag, r resync, CLI no-selector pager honoring -s/-S/-a/-l/-p, PNG goldens. Verified: 17 phase tests pass (feed_document+feed_fold+history_png); just fmt clean; epic-symbols clean; just check full failures are base (12 reproduce on clean tree, 4 flaky pass isolated, symvision/import in untouched files) recorded as follow-ups

## Dependencies

- **Blocks:** [sase-1dr.11](sase-1dr.11.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1dr.8](sase-1dr.8.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.10.md) | [sase-1dr.10](sase-1dr.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`429d657`](https://github.com/sase-org/sase/commit/429d6577de09805c95c5cd7509e0ecb4691ba8c7) | feat(sase-1dr.10): cross-file memory changes feed with day sections, folded consequences and PNG goldens | [sase-1dr.10](sase-1dr.10.md) | 2026-10-01 09:55:04 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dr.10--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.10.md

<!-- sase:referenced-by:end -->
