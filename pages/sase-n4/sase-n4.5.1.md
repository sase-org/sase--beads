# Bead: sase-n4.5.1 — Make first usage-limit disable atomic in sase-core

[Bead Pages](../README.md) / [sase-n4.5](sase-n4.5.md) / sase-n4.5.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-n4.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n4.land.md) · **Assignee:** `sase-n4.5.1` · **Size:** medium
**Created:** 2026-08-16 14:19:24 EDT
**Plan:** [202608/finish\_usage\_limit\_auto\_disable.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_usage_limit_auto_disable.md)

## Description

atomic-disable: add a Rust-core and Python-binding operation that atomically writes a provider disable only when no active record exists, returns whether this caller won the window, preserves the existing unconditional manual replacement APIs, and proves first-writer behavior under real contention.

## Dependencies

- **Blocks:** [sase-n4.5.2](sase-n4.5.2.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n4.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n4.5.1/README.md) | [sase-n4.5.1](sase-n4.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@dc87c8e`](https://github.com/sase-org/sase-core/commit/dc87c8e5faa250b1babc84764493e05233d5a0a8) | feat(provider\_disable): add atomic first-writer disable | [sase-n4.5.1](sase-n4.5.1.md) | 2026-08-16 15:15:23 EDT |
