# Bead: sase-1cq.2 — Host moves a linked repo's revision pin when one declaration commits both repos

[Bead Pages](../README.md) / [sase-1cq](README.md) / sase-1cq.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u6.md) · **Assignee:** `sase-1cq.2` · **Size:** medium
**Created:** 2026-09-29 17:21:21 EDT · **Closed:** 2026-09-29 17:46:09 EDT
**Plan:** [202609/cross\_repo\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202609/cross_repo_landing.md)

## Description

pin_follow: add a repos.linked[].revision_pin config field, make the builtin commit finalizer commit pinned siblings first and write their pushed SHA into the primary's pin file before the primary commit, with tests and docs.

## Notes

[2026-09-29T21:45:50Z · sase-1cq.2] PROPOSED FOLLOW-UP: symvision flags 6 unused bead-attachment symbols (format_attachment_dims/size, handle_bead_attachment_list/path, note_label_attachment_suffix, total_attachment_count) identically on the clean base tree; just check stays red until the stranded-landing phase resolves them

[2026-09-29T21:46:09Z · sase-1cq.2] pin_follow done: revision_pin config field + sase-core pin set; finalizer commits pinned siblings first, writes pushed SHA to pin with ancestor/branch/equality guards, revision_pin evidence, bead_action only on primary; 32 new tests in tests/test_commit_revision_pin.py, 95 focused tests green, mypy/ruff/prettier clean on touched files, doctor OK, epic-symbols empty; symvision bead-attachment reds reproduce on clean base (recorded as follow-up)

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cq.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cq.2/README.md) | [sase-1cq.2](sase-1cq.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c257a3f`](https://github.com/sase-org/sase/commit/c257a3f22035e68e431826fc939af2895e3ff328) | feat(finalizer): add revision\_pin for linked repos with commit ordering and pin update | [sase-1cq.2](sase-1cq.2.md) | 2026-09-29 17:48:14 EDT |
