# Bead: sase-k2.1 — ProjectSpec description truncation and duplicate-block repair

[Bead Pages](../README.md) / [sase-k2](README.md) / sase-k2.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yn/README.md) · **Assignee:** `sase-k2.1` · **Size:** large
**Created:** 2026-08-12 11:28:34 EDT
**Plan:** [202608/external\_mirror\_refinement.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_mirror_refinement.md)

## Description

spec_repair: fix the two-blank-line record terminator that silently drops any Patch whose DESCRIPTION contains a blank run, in both the Python and Rust parsers plus the block writer, and add the raw-text de-duplication repair that reclaims the archives the external PR mirror has already corrupted.

## Dependencies

- **Blocks:** [sase-k2.5](sase-k2.5.md) ◐ · ⧖ 2026-08-12
- **Blocks:** [sase-k2.6](sase-k2.6.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k2.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-k2.1.md) | [sase-k2.1](sase-k2.1.md) | 0 |
