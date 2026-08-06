# Bead: sase-gg.1 — Keep the core extension parent and submodule in sync across sys.modules patches

[Bead Pages](../README.md) / [sase-gg](README.md) / sase-gg.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.u6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.u6/README.md) · **Assignee:** `sase-gg.1` · **Size:** medium
**Created:** 2026-08-06 12:26:19 EDT
**Plan:** [202608/ci\_green\_restore.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_green_restore.md)

## Description

modguard: give the six test modules that swap or evict sys.modules['sase_core_rs'] a shared helper that moves the compiled submodule with its parent package, and pin the re-import invariant with a regression test.

## Dependencies

- **Blocks:** [sase-gg.5](sase-gg.5.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gg.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gg.1/README.md) | [sase-gg.1](sase-gg.1.md) | 0 |
