# Bead: sase-xy.4.1 — Resolve dead ends once off the event loop

[Bead Pages](../README.md) / [sase-xy.4](sase-xy.4.md) / sase-xy.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xy.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xy.land.md) · **Assignee:** `sase-xy.4.1` · **Size:** medium
**Created:** 2026-09-07 12:10:22 EDT · **Closed:** 2026-09-07 13:01:25 EDT
**Plan:** [202609/pager\_link\_landing\_corrections.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_link_landing_corrections.md)

## Description

one-pass-dead-ends: return the file-path search diagnostics needed by the pager from the same background resolution attempt, remove the synchronous/repeated toast search, and enforce the git output bound while preserving timeout and resolver-injection behavior.

## Notes

[2026-09-07T17:01:25Z · sase-xy.4.1] One background resolve_link now returns the target plus file-path dead-end diagnostics; the pager apply path toasts that stored copy (including on a repeated dangling press) without Path/Git/search I/O. Missing two-component paths run _git_ls_files once per unique anchor from press through toast. Git capture accepts output at the byte limit, rejects overflow without a partial candidate list, and kills/reaps timeout and overflow children while keeping GIT_TERMINAL_PROMPT=0. resolve_ref stays the convenience API; ACE link-index still short-circuits then falls back to resolve_link. Focused pager/ACE tests passed; just check passed (161 scoped files). Also updated the machine help metavar test so the committed attention subcommand is listed.

## Dependencies

- **Blocks:** [sase-xy.4.2](sase-xy.4.2.md) ◐ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xy.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.4.1/README.md) | [sase-xy.4.1](sase-xy.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5144564`](https://github.com/sase-org/sase/commit/51445642c37303762ef7bb51be7c49c680c19ee4) | feat(pager): resolve dead ends in one background pass | [sase-xy.4.1](sase-xy.4.1.md) | 2026-09-07 13:03:05 EDT |
