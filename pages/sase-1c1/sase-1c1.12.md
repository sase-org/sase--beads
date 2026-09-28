# Bead: sase-1c1.12 — Make the visual-test lane green without bulk acceptance

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.12

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.12` · **Size:** medium
**Created:** 2026-09-28 07:09:39 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

visual-lane: reproduce just test-visual at HEAD after the TUI phases land, fix the semantic timeouts (the Config Center flags SUNSET wait, the narrow top-bar startup), and rebaseline only goldens whose drift traces to a deliberate UI commit.

## Dependencies

- **Blocks:** [sase-1c1.13](sase-1c1.13.md) ◐ · ⧖ 2026-09-28
- **Depends on:** [sase-1c1.5](sase-1c1.5.md) ✓ · ⧖ 2026-09-28
- **Depends on:** [sase-1c1.6](sase-1c1.6.md) ✓ · ⧖ 2026-09-28
- **Depends on:** [sase-1c1.7](sase-1c1.7.md) ◐ · ⧖ 2026-09-28
- **Depends on:** [sase-1c1.8](sase-1c1.8.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1c1.12/README.md) | [sase-1c1.12](sase-1c1.12.md) | 0 |
