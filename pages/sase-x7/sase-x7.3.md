# Bead: sase-x7.3 — Migrate configuration, prompts, editor integration, and automation

[Bead Pages](../README.md) / [sase-x7](README.md) / sase-x7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gk.md) · **Assignee:** `sase-x7.3` · **Size:** large
**Created:** 2026-09-05 18:55:29 EDT · **Closed:** 2026-09-06 17:04:01 EDT
**Plan:** [202609/canonical\_only\_fleet\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_only_fleet_cutover.md)

## Description

canonical-producers: Plan and update chezmoi sources, project and home prompts, generated skills and memory guidance, Neovim producers, scripts, and plugin callers to emit canonical forms already supported by the bridge runtime; deploy from landed sources on all three machines.

## Notes

[2026-09-06T12:17:51Z · sase-x7.2.1.5.land] DISCOVERED ISSUE (proposed by sase-x7.2.1.5.2 note #2): mac sase completion list reports /home/bryan Linux targets missing although the real mac-native files exist. G3 evidence shows the live completion stamps are chezmoi-owned, and current linked chezmoi source confirms home/dot_sase/completion/stamp/{bash,fish,zsh}.json hard-code /home/bryan targets. canonical-producers already owns updating chezmoi sources and deploying them on all three hosts; make these stamp targets home/platform-aware and verify sase completion list on mac. Routed here rather than creating a standalone task.

[2026-09-06T12:18:28Z · sase-x7.2.1.5.land] DISCOVERED ISSUE (proposed by sase-x7.2.1.5.2 note #2): mac sase completion list reports /home/bryan Linux targets missing although the real mac-native files exist. G3 evidence shows the live completion stamps are chezmoi-owned, and current linked chezmoi source confirms home/dot_sase/completion/stamp/{bash,fish,zsh}.json hard-code /home/bryan targets. canonical-producers already owns updating chezmoi sources and deploying them on all three hosts; make these stamp targets home/platform-aware and verify sase completion list on mac. Routed here rather than creating a standalone task.

[2026-09-06T21:05:26Z · sase-x7.3.1.land--2] LAND HANDOFF VERIFIED: child epic sase-x7.3.1 and all five phases are closed normally. The close command also completed this delegated parent phase with resolution done and reason delegated work landed; no force was used. Rechecked this phase description and both duplicate Mac stamp notes: landed canonical host/chezmoi/plugin/Neovim sources are deployed on athena, mac and apollo; portable ~/ ownership targets and Mac completion discovery were verified, Mac memory reconciled, generated legacy skill copies pruned, and canonical config behavior preserved. Audited fleet receipts file:explicit:f937c92641c01044fef763f8 and file:explicit:da42a703ffc6fda7becf6d62 plus child close note retain the source/revision evidence. Canonical_producers plan frontmatter is now status: done. Fresh full pytest passed 38,840 tests; full-check CPU-budget failure is corroborated on sase-xc and five historical flake nodes remain with sase-vt/sase-x6/sase-j7, explicitly qualified in the child close note. No producer gap remains. Both epic-symbol queries were empty. Containing epic sase-x7 remains open for its own land agent.

[2026-09-06T21:06:27Z · sase-x7.3.1.land--2] Verified completion through canonical producer child epic sase-x7.3.1; detailed verification is recorded on this phase and post-close symvision passed.

## Dependencies

- **Depends on:** [sase-x7.1](sase-x7.1.md) ✓ · ⧖ 2026-09-05
- **Depends on:** [sase-x7.2](sase-x7.2.md) ✓ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.4](sase-x7.4.md) ✓ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.6](sase-x7.6.md) ✓ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.3.md) | [sase-x7.3](sase-x7.3.md) | 0 |
