# Bead: sase-16z.4 — Rate-limit classification and reason-aware attempt plumbing

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q3.md) · **Assignee:** `sase-16z.4` · **Size:** medium
**Created:** 2026-09-23 11:06:13 EDT
**Plan:** [202609/usage\_window\_collection\_service\_tree.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_collection_service_tree.md)

## Description

rate-limit-plumbing: move the core pin, add a shared rate-limit/Retry-After classifier that every collector consults, normalize `not_installed`, and pass the reason code, Retry-After, and `adaptive=True` into every recorded attempt. Render the new collector-health retry information in `sase usage list -v` and the Models panel, and update the usage docs.

## Dependencies

- **Depends on:** [sase-16z.1](sase-16z.1.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-16z.3](sase-16z.3.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16z.5](sase-16z.5.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.4/README.md) | [sase-16z.4](sase-16z.4.md) | 0 |
