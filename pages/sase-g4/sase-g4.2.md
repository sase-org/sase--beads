# Bead: sase-g4.2 — Report an invalid header block from \`sase plan links validate\`

[Bead Pages](../README.md) / [sase-g4](README.md) / sase-g4.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ty](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ty/README.md) · **Assignee:** `sase-g4.2` · **Size:** small
**Created:** 2026-08-06 09:05:39 EDT
**Plan:** [202608/plan\_header\_validation.md](https://github.com/sase-org/sase--plans/blob/main/202608/plan_header_validation.md)

## Description

links-parity: `_link_validation.py` silently skips a plan whose header disposition is INVALID while `plan_links_refresh` reports `header-invalid` for the same document; give the validator the same issue so the two commands agree on what a broken header block is.

## Dependencies

- **Blocks:** [sase-g4.5](sase-g4.5.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-g4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-g4.2/README.md) | [sase-g4.2](sase-g4.2.md) | 0 |
