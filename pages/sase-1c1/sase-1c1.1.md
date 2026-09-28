# Bead: sase-1c1.1 — Fix macOS path canonicalization in sase-core

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.1` · **Size:** small
**Created:** 2026-09-28 07:09:23 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

core-macos: in the linked sase-core checkout, canonicalize the deepest existing ancestor in launch_scratch_liveness normalize_path, make the managed_tmp_roots test expect canonical storage, and add a symlink regression test that reproduces the macOS /var vs /private/var bug on Linux.

## Dependencies

- **Blocks:** [sase-1c1.2](sase-1c1.2.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1c1.1.md) | [sase-1c1.1](sase-1c1.1.md) | 0 |
