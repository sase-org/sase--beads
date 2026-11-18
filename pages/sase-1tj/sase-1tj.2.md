# Bead: sase-1tj.2 — Flag writes the commit finalizer cannot see

[Bead Pages](../README.md) / [sase-1tj](README.md) / sase-1tj.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1dz](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1dz.md) · **Assignee:** `sase-1tj.2` · **Size:** medium
**Created:** 2026-11-18 11:26:28 EST · **Closed:** 2026-11-18 12:17:29 EST
**Plan:** [202611/research\_commit\_gap.md](https://github.com/sase-org/sase--plans/blob/main/202611/research_commit_gap.md)

## Description

unscanned-write-guard: add a shared detector for run writes and registered artifact sources that sit in checkouts the commit finalizer does not scan, and surface it in sase final context, sase artifact create, and the /sase_final and /sase_repo skills.

## Notes

[2026-11-18T17:17:29Z · sase-1tj.2] unscanned-write-guard done and verified: new commit_scan_roots helper plus find_unscanned_writes detector (tool-call writes, explicit-artifact sources, extra_paths; toplevel-equality vs scan roots; dirty check; open/open_and_move/relocate_or_discard fix with repo-relative path; fail-open); surfaced as advisory top-level unscanned_writes in sase final context (wire/requirements/obligations/digests unchanged), step 2 of /sase_final, repo-relative rule in /sase_repo, and warn-branch stderr warning in sase artifact create -p (exit unchanged; artifact still registers); parser help + generated artifact.md + finalizers.md docs updated. Verified: 13/13 new tests in tests/test_unscanned_writes_guard.py pass; 77 affected tests pass (finalizer channel context, final prepare/status, artifact handler, artifact create, dirty-repo dedupe/reserved-paths, followup inheritance); ruff/mypy/symvision/fmt clean; sase tool run check lint stages all green incl. symvision (run 1f27f18dcdc719886b71631fe5008b61; its test lane was still sweeping on an overloaded host at hand-off). No epic-symbol leftovers. Note: redeploy generated skills (sase skill init) from the landed tree after landing; not run from this workspace per generated_skills note.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tj.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tj.2/README.md) | [sase-1tj.2](sase-1tj.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`03a48ab`](https://github.com/sase-org/sase/commit/03a48ab7fc25f64baf244dfef1012a5cbcc42e02) | feat(finalizers): flag writes the commit finalizer cannot see | [sase-1tj.2](sase-1tj.2.md) | 2026-11-18 12:22:39 EST |
