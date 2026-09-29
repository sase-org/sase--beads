# Bead: sase-1ck.4.1.3 — Text rendering, list/path, and beta docs

[Bead Pages](../README.md) / [sase-1ck.4.1](sase-1ck.4.1.md) / sase-1ck.4.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ck.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.4.md) · **Assignee:** `sase-1ck.4.1.3` · **Size:** medium
**Created:** 2026-09-29 12:24:50 EDT · **Closed:** 2026-09-29 14:52:46 EDT
**Plan:** [202609/note\_cli.md](https://github.com/sase-org/sase--plans/blob/main/202609/note_cli.md)

## Description

read_surface: render text chips, the attachments block, history, list, and path, and document the beta commands.

## Notes

[2026-09-29T18:51:58Z · sase-1ck.4.1.3] PROPOSED FOLLOW-UP: patch-stitch terminology audit fails on the clean base tree too (sase-core fixture note_attachment/at_bearing_notes.jsonl ChangeSpec lines) — needs a sase-core-side or audit-baseline fix, out of scope for read_surface; siblings sase-1ck.4.1.1 and sase-1ck.4.1.2 saw it byte-identically

[2026-09-29T18:52:11Z · sase-1ck.4.1.3] PROPOSED FOLLOW-UP: symvision reports stale --epic-symbol entries for closed bead sase-1cj.8 in the Justfile (this phase touches no Justfile lines) — needs the owning epic to clean up; sibling sase-1ck.4.1.2 saw the sase-1cj.7 variant identically

[2026-09-29T18:52:22Z · sase-1ck.4.1.3] PROPOSED FOLLOW-UP: 22 test_cli_work_* failures + 2 errors (launch-family: cleanup_confirm, collisions, epic_checkpoint, epic_lifecycle, launch_cleanup_sessions, epic_summary) reproduce identically on the clean base tree in this sandbox — environmental launch-infra issue, needs a launch-infra owner; sibling sase-1ck.4.1.2 saw the same 22+2

[2026-09-29T18:52:46Z · sase-1ck.4.1.3] read_surface landed: plain-text chip formatter (prose @attachment: tokens render as [name], control/bidi-stripped, never from_ansi), note label gains 📎 N, ATTACHMENTS block (name · mime · dims · size · sha256:12 plus cached view path, ✕ unavailable offline with exit 0), compact list/search 📎N suffix from stored manifests, public JSON gains availability plus local_path when cached (store codec untouched, no bytes or escapes), history full joins tokens to current manifests with (not on the current bead) fallback and renders wired payloads directly, sase bead attachment list (-j/--json) and path with bare-to-list delegation and no flag check, beta docs in docs/beads.md (Attachments section with mental model, grammar table, shipped commands, local-only storage, viewing rules) and docs/cli.md (attach, attachment list/path, -S on note-bearing verbs). Verified: 7 new read_surface tests plus 106 attach/note/history/help/read neighbors green; just fix clean; ruff, mypy, fmt, keep-sorted, flags, pyscripts, waits, changelog, and validate gates green; scoped lane 5532 passed with only pre-existing clean-tree failures (terminology audit on sase-core fixture, symvision stale sase-1cj.8 symbols, 22 work-launch failures + 2 errors — all filed as PROPOSED FOLLOW-UP, Justfile untouched); epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1ck.4.1.1](sase-1ck.4.1.1.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1ck.4.1.2](sase-1ck.4.1.2.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ck.4.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.4.1.3/README.md) | [sase-1ck.4.1.3](sase-1ck.4.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c2aec59`](https://github.com/sase-org/sase/commit/c2aec595c83802163e3c6c504f99d2bdbf8985f8) | feat(bead): render attachment text surface with list/path commands and beta docs | [sase-1ck.4.1.3](sase-1ck.4.1.3.md) | 2026-09-29 14:55:10 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ck.4.1.3][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.4.1.3/README.md

<!-- sase:referenced-by:end -->
