# Bead: sase-1r5.1 — Retry transient GitHub SSH publickey denials on git network operations

[Bead Pages](../README.md) / [sase-1r5](README.md) / sase-1r5.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1r5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r5.md) · **Assignee:** `sase-1r5.1.land`
**Created:** 2026-11-04 06:54:52 EST
**Plan:** [202611/github\_publickey\_retry.md](https://github.com/sase-org/sase--plans/blob/main/202611/github_publickey_retry.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/github_publickey_retry.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/github_publickey_retry.md

<!-- sase:links:end -->

## Description

A GitHub-side burst of `Permission denied (publickey)` rejections of valid SSH keys no longer aborts agent launches or background git jobs. Launch-blocking and background git network operations retry such denials within a bounded, deadline-aware budget. Genuine credential failures still surface promptly as permanent authentication errors that keep the original stderr: deploy-key refusals, a host with no local SSH credential at all, and a denial that outlasts the budget.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r5.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r5.1.land/README.md) | [sase-1r5.1](sase-1r5.1.md) | 0 |
