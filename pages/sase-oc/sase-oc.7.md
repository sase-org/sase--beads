# Bead: sase-oc.7 — Install, verification, doctor, and refresh

[Bead Pages](../README.md) / [sase-oc](README.md) / sase-oc.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04p](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04p.md) · **Assignee:** `sase-oc.7` · **Size:** medium
**Created:** 2026-08-17 08:54:26 EDT · **Closed:** 2026-08-17 12:22:33 EDT
**Plan:** [202608/cli\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/cli_completion.md)

## Description

install: add `sase completion install` that picks a directory compinit actually scans, zcompiles, verifies registration, and stamps the install, plus the doctor check and the flagged `sase update` refresh hook.

## Notes

[2026-08-17T16:22:18Z · sase-oc.7] PROPOSED FOLLOW-UP: sase validate init memory --check is red on chezmoi home AGENTS.md/CLAUDE.md/GEMINI.md/QWEN.md/OPENCODE.md and memory README drift (+1/−2). This phase did not edit repo memory files; just check lint and the escalated full pytest suite were green without refreshing those home shims.

[2026-08-17T16:22:33Z · sase-oc.7] sase completion install detects the shell, picks a scanned or conventional dir, writes atomically, zcompiles zsh, probes _comps[sase], and stamps ~/.sase/completion/stamp/<shell>.json. list shows path/.zwc/stamp/status. doctor completion.install (advisory) + completion.registration (deep). sase update refresh is behind beta flag completion_refresh_on_update (bead sase-om, default off); failures never fail the update. Regenerated cli_spec.json (adds install; also bead epic-symbols). Verified: 32205 passed / 13 skipped after test-scoped escalated (src-data-asset); real-zsh zcompile+_comps[sase]; both flag states; just check lint/symvision/mypy green. sase validate init memory --check failed on pre-existing chezmoi home shim drift only.

[2026-08-17T16:24:12Z · sase-oc.7] just check lint gates green; scoped suite escalated on schema change and full suite passed (32205 passed, 13 skipped); real-zsh install wrote .zwc and resolved _comps[sase]; update refresh is flag-gated and never fails sase update

## Dependencies

- **Depends on:** [sase-oc.3](sase-oc.3.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-oc.8](sase-oc.8.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-oc.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-oc.7/README.md) | [sase-oc.7](sase-oc.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3e9be9c`](https://github.com/sase-org/sase/commit/3e9be9ce44876f800bc21cc1b86e787c6be58132) | feat(completion): install scripts, doctor checks, and update refresh | [sase-oc.7](sase-oc.7.md) | 2026-08-17 12:26:21 EDT |
