# Bead: sase-ru.5 — Audit commit-finalizer shared-clone exemptions

[Bead Pages](../README.md) / [sase-ru](README.md) / sase-ru.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09i.md) · **Assignee:** `sase-ru.5` · **Size:** medium
**Created:** 2026-08-21 10:44:28 EDT · **Closed:** 2026-08-21 11:31:14 EDT
**Plan:** [202608/open\_feature\_flag\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/open_feature_flag_closeout.md)

## Description

shared_clone_audit: establish attributable shared-clone race evidence after the separately owned finalizer work lands and determine whether commit_finalizer_shared_clone_exempt is safe to retire.

## Notes

[2026-08-21T15:30:15Z · sase-ru.5] PROPOSED FOLLOW-UP: Wire discarded_dirty_work_evidence into builtin@commit — pluggable_finalizers On currently never calls the shared-clone classifier, so production with that beta emits no exemption events.

[2026-08-21T15:30:32Z · sase-ru.5] PROPOSED FOLLOW-UP: Decide whether On-path published classification requires dirty-blob survival — unattributed sdd/external HEAD-advance is still published even when the dirty blob is not in the new HEAD (existing sync-rebase tests).

[2026-08-21T15:30:49Z · sase-ru.5] PROPOSED FOLLOW-UP: Tree-level just check is red from out-of-scope work — live flag bead sase-rc has no artifact_links definition; symvision private-import errors in finalizers/commit_finalizer; toobig on src/sase/finalizers/declaration.py (1038 lines); test-scoped escalated on core-identity-changed and reported unrelated ConfigHubPane/LSP/completion/fakey failures.

[2026-08-21T15:31:14Z · sase-ru.5] Added path-free shared-clone classification events/counter; existing logs could not attribute exemptions. Controlled git races (sdd+external foreign_agent/already-published/pending-publication) preserved the dirty blob and classified race/published; main/sibling, unattributed owned-repo commits, genuine resets, and flag-off external foreign-agent stayed fail-closed. Event IDs recorded on sase-qi. Focused tests 66 passed; did not retire the flag.

## Dependencies

- **Blocks:** [sase-ru.10](sase-ru.10.md) ◐ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ru.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ru.5/README.md) | [sase-ru.5](sase-ru.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f4fde13`](https://github.com/sase-org/sase/commit/f4fde13df67b8c7df4cafc00839eab669799de30) | feat(llm\_provider): emit attributable shared-clone classification events | [sase-ru.5](sase-ru.5.md) | 2026-08-21 11:34:14 EDT |
| sase--plans | [`sase--plans@3975633`](https://github.com/sase-org/sase--plans/commit/3975633814f39766b2b01e91d063169f25b530a9) | chore(sdd): record sase-ru.5 read of the flag closeout plan | [sase-ru.5](sase-ru.5.md) | 2026-08-21 11:38:41 EDT |
