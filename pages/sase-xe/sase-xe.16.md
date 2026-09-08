# Bead: sase-xe.16 — Complete remote dispatch - target bootstrap, tailnet discovery, canonical machine init, and the live Apollo proof

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.16

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.land`
**Created:** 2026-09-08 10:21:31 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/remote_dispatch_completion.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md

<!-- sase:links:end -->

## Description

Finish the remote dispatch feature epic sase-xe shipped incompletely, ending with a live proof: a normally installed Apollo that Athena discovers over the tailnet, explicitly enrolls through `sase machine init` after a target-local `sase machine bootstrap`, and immediately manages - launching 1-3 remote agents with %dispatch:apollo and driving them from Athena's TUI. Also lands the acceptance-hardening remainder (provider isolation, offline fleet fixture, PNG snapshots, fleet benches) reconciled from the sase-xe landing's stashed child plan draft.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.land/README.md) | [sase-xe.16](sase-xe.16.md) | 0 |
