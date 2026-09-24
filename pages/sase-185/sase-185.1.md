# Bead: sase-185.1 — Pending launch lifecycle and detached relaunch waits

[Bead Pages](../README.md) / [sase-185](README.md) / sase-185.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0r6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0r6.md) · **Assignee:** `sase-185.1` · **Size:** medium
**Created:** 2026-09-24 15:03:17 EDT
**Plan:** [202609/detached\_prompt\_submit.md](https://github.com/sase-org/sase--plans/blob/main/202609/detached_prompt_submit.md)

## Description

pending-launch: add the PendingLaunch record, restore helper, pending proc row, `,X` cancel of not-yet-submitted launches, and quit-time stash; unmount the bar ahead of the relaunch-cleanup/pending-kill holds; move the synchronous post-unmount tail (MRU write, bulk Patch resolution) off the UI thread.

## Dependencies

- **Blocks:** [sase-185.2](sase-185.2.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-185.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-185.1/README.md) | [sase-185.1](sase-185.1.md) | 0 |
