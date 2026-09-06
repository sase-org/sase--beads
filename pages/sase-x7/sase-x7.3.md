# Bead: sase-x7.3 — Migrate configuration, prompts, editor integration, and automation

[Bead Pages](../README.md) / [sase-x7](README.md) / sase-x7.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gk.md) · **Assignee:** `sase-x7.3` · **Size:** large
**Created:** 2026-09-05 18:55:29 EDT
**Plan:** [202609/canonical\_only\_fleet\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_only_fleet_cutover.md)

## Description

canonical-producers: Plan and update chezmoi sources, project and home prompts, generated skills and memory guidance, Neovim producers, scripts, and plugin callers to emit canonical forms already supported by the bridge runtime; deploy from landed sources on all three machines.

## Notes

[2026-09-06T12:17:51Z · sase-x7.2.1.5.land] DISCOVERED ISSUE (proposed by sase-x7.2.1.5.2 note #2): mac sase completion list reports /home/bryan Linux targets missing although the real mac-native files exist. G3 evidence shows the live completion stamps are chezmoi-owned, and current linked chezmoi source confirms home/dot_sase/completion/stamp/{bash,fish,zsh}.json hard-code /home/bryan targets. canonical-producers already owns updating chezmoi sources and deploying them on all three hosts; make these stamp targets home/platform-aware and verify sase completion list on mac. Routed here rather than creating a standalone task.

[2026-09-06T12:18:28Z · sase-x7.2.1.5.land] DISCOVERED ISSUE (proposed by sase-x7.2.1.5.2 note #2): mac sase completion list reports /home/bryan Linux targets missing although the real mac-native files exist. G3 evidence shows the live completion stamps are chezmoi-owned, and current linked chezmoi source confirms home/dot_sase/completion/stamp/{bash,fish,zsh}.json hard-code /home/bryan targets. canonical-producers already owns updating chezmoi sources and deploying them on all three hosts; make these stamp targets home/platform-aware and verify sase completion list on mac. Routed here rather than creating a standalone task.

## Dependencies

- **Depends on:** [sase-x7.1](sase-x7.1.md) ✓ · ⧖ 2026-09-05
- **Depends on:** [sase-x7.2](sase-x7.2.md) ✓ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.4](sase-x7.4.md) ◐ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.6](sase-x7.6.md) ◐ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.3.md) | [sase-x7.3](sase-x7.3.md) | 0 |
