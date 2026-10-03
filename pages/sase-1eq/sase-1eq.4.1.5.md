# Bead: sase-1eq.4.1.5 — Remaining strings, skill sources, and terminology guard

[Bead Pages](../README.md) / [sase-1eq.4.1](sase-1eq.4.1.md) / sase-1eq.4.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.4.md) · **Assignee:** `sase-1eq.4.1.5` · **Size:** medium
**Created:** 2026-10-03 06:00:04 EDT · **Closed:** 2026-10-03 11:31:25 EDT
**Plan:** [202610/macro\_syntax\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_syntax_cutover.md)

## Description

strings-guard: finish non-TUI strings and directive writers, update maintained skill sources and smoke/demo scripts, tighten the guard with classified exceptions, and record integration evidence for the assigned parent phase without closing any ancestor.

## Notes

[2026-10-03T15:30:18Z · sase-1eq.4.1.5] Guard exceptions recorded in tests/test_macro_terminology.py: sunset-policy readers/aliases (removed with flag); doctor retired-names table (permanent); flag definition/schema prose; dual-spelling directive readers; permanent durable readers (artifacts, MRU, save-state, prompt archive); pre-flip wire/transport owned by sase-1eq.10 (LSP envs, swarm/launch envs, snippet kinds, stats binding, content-layout wire, xprompt-proc family, continuation provenance kind); TUI-mirrored vocabulary owned by sase-1eq.5 (highlight roles, JinjaScope kind, save index kinds, keymaps, TUI prose, commit-type vocabulary); stable emitted keys; legacy-residue cleanup; external audit matcher. Skill sources and smoke/demo scripts carry zero exceptions.

[2026-10-03T15:30:39Z · sase-1eq.4.1.5] PROPOSED FOLLOW-UP: mypy EntryPoints.get attr-defined error at src/sase/doctor/checks_config_retired.py:322 — reproduces identically on clean base (verified via stash), from predecessor phase sase-1eq.4.1.4 commit 4f90695659; file untouched by strings-guard.

[2026-10-03T15:30:50Z · sase-1eq.4.1.5] PROPOSED FOLLOW-UP: symvision unused-public flags for PublicationPayloadFile, plan_publication_payload_batches, discover_macro_plugin_entry_points — reproduce identically on clean base (verified via stash); files untouched by strings-guard, likely owned by predecessor/discovery phases or a later consumer.

[2026-10-03T15:31:01Z · sase-1eq.4.1.5] PROPOSED FOLLOW-UP: test_load_launchable_prunes_provider_mismatched_prefix fails identically on clean base (verified via stash); matches the predecessor-noted MRU provider-mismatch pruning failure; path untouched by strings-guard.

[2026-10-03T15:31:25Z · sase-1eq.4.1.5] Writers emit %macros_enabled (disabled_regions, qa_prompt, followup_persistence, fork_by_chat/make_mentor_changes); readers accept both spellings incl. flag-off legacy test. 61-pair mechanical string sweep + skill sources (sase_run/project/chats/agents_status), smoke_check.sh, seed demo updated; skill dry-run clean, no deploy. Guard widened to strings/comments/resources with classified exceptions (808+9+15 pairs); negative control proved it fails on new stragglers. Verified: guard 7 passed, writer/reader/both-states suites green, live macro list/show CLI canonical, doctor retired-names check clean in both states, fmt/ruff/flags/pyscripts/waits/changelog/patch-stitch/keep-sorted/model-policy green. mypy, symvision, toobig, and one MRU-pruning test fail identically on clean base (recorded as PROPOSED FOLLOW-UPs).

## Dependencies

- **Depends on:** [sase-1eq.4.1.4](sase-1eq.4.1.4.md) ✓ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.4.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.4.1.5/README.md) | [sase-1eq.4.1.5](sase-1eq.4.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`29c1471`](https://github.com/sase-org/sase/commit/29c14710fb6c7aedf5db7641deb466511c8a34b8) | feat!: finish non-TUI macro strings, skill sources, and terminology guard | [sase-1eq.4.1.5](sase-1eq.4.1.5.md) | 2026-10-03 11:32:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.4.1.5][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.4.1.5/README.md

<!-- sase:referenced-by:end -->
