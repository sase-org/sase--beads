# Bead: sase-gw — sase init skills --check fails on unresolvable drift whenever skill sources are uncommitted

[Bead Pages](../README.md) / sase-gw

**Status:** ✓ closed · **Resolution:** done · **Type:** ◆ task · **+1 reports:** +2
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-gt.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gt.land/README.md) · **Assignee:** `sase-gw` · **Size:** small
**Created:** 2026-08-07 10:02:58 EDT · **Closed:** 2026-08-07 11:41:53 EDT

## Description

Proposed by phase bead sase-gt.2 (epic sase-gt) as a PROPOSED FOLLOW-UP; independently reproduced while landing sase-gt.

sase init skills refuses to deploy when src/sase/xprompts/skills/*.md have uncommitted changes (src/sase/main/_init_skills_source_integrity.py:45-64, escape hatch --allow-dirty at init_skills_handler.py:492-497). That refusal is correct — deploying from a dirty tree can revert other agents' skill work. The problem is the paired --check surface: it renders from the dirty sources and compares against the deployed chezmoi trees, so it reports drift that the agent is structurally forbidden from resolving.

Concrete reproduction from this epic: sase-gt.2 flipped MARKDOWN_PRINT_WIDTH to 100, which reflows every generated skill source. Its 'just check-full' run reported 86 chezmoi provider skill files needing redeploy, with no available action — the deploy could only happen after the commit landed, which is why the epic needed a separate phase (sase-gt.3) whose entire job was the post-land redeploy. The phase agent had to hand-classify a red validation stage as 'known and expected' in its notes.

This hits any change that touches skill sources, not just this epic. It is the same failure pattern previously called out in sase-bi: a validation stage that is red for reasons the agent did not cause and cannot fix is exactly what trains agents to ignore red checks. Prior art: sase-dr.5's note reached the same conclusion from the other direction ('run sase skill init --force from a clean canonical tree so init skills --check can pass without dirty development trees').

Scope: make 'init skills --check' detect that the skill sources are dirty and report the drift as deferred-until-land (a warning naming the required post-land 'sase init skills' run) instead of a hard validation failure. Leave the deploy-side refusal exactly as it is.

## Notes

[2026-08-07T15:41:53Z · sase-gw] Fixed: plan_init_skills() now treats skill-deploy drift as a deferred warning (naming the required post-land 'sase init skills' run) instead of a hard --check failure, gated on args.check so interactive/apply flows are unaffected and the deploy-side skill_source_integrity_error refusal is untouched. This covers both the dirty-tree case (sase-gt.2) and the clean-but-undeployed case (sase-gl), since deferral now applies regardless of the integrity-check reason. Added 3 tests in tests/main/test_init_skills_plan.py. Verified: just check and just check-full both pass, including 'SASE validation' (init skills --check), which was previously failing live in this workspace due to genuine unrelated sase_gate.md redeploy drift -- now correctly reported as a warning instead of failing the gate.

[2026-08-07T15:43:10Z · sase-gw] Deferred stale-skill-deploy drift under sase init skills --check to a warning instead of a hard failure; added 3 regression tests; just check and just check-full both pass.

## +1 Evidence

> **+1** by `sase-gl` · 2026-08-07 10:33:02 EDT
>
> Independently reproduced in sase_12 while landing sase-gl (flaky mtime tie-break fix, unrelated change). just check failed at SASE validation / init skills --check reporting 5 provider skill files out of sync for sase_gate (dot_gemini/dot_claude/dot_codex/dot_config/dot_qwen, each +12/-2). Root cause here: commit 7ca857a9a (feat(ace)!: always render a gate detail card and rename the HITL tab to Gates) changed src/sase/xprompts/skills/sase_gate.md and landed without the post-land chezmoi redeploy step this bead's scope covers. My working tree was clean of skill-source edits (only tests/_test_selection_contexts.py touched), so this is not the uncommitted-dirty-tree case sase-gt.2 hit -- it's the same check surface failing on a distinct trigger: a skill source that changed and merged to master but has not yet been redeployed via sase init skills. Confirms the check needs to treat this as deferred-until-land rather than a hard failure regardless of why the deployed copies are stale.

> **+1** by `sase-gu.land` · 2026-08-07 11:33:01 EDT
>
> Independently reproduced by the sase-gu land agent on a clean master tree at a56da1e6c (2026-08-07). `sase init skills --check` reports the same 5 sase_gate provider SKILL.md files under ~/.local/share/chezmoi/home (dot_gemini/dot_claude/dot_codex/dot_config/dot_qwen, each +12 -2) with no working-tree skill-source edits of my own — same deployed-copies-stale-after-land trigger sase-gl reported, still unresolved ~1h later. Proposed as a PROPOSED FOLLOW-UP by phase beads sase-gu.1 and sase-gu.3, whose `just check-full` / `sase validate` runs were red for this reason and had to be hand-classified as pre-existing. Worth noting the memory half of those proposals is NOT part of this bead: `sase init memory --check` also reported drift (project-local sase/memory/sase_beads.md +2 -3 and sase/memory/README.md +4 -4), but a plain `sase init memory` cleared it with zero tracked-file changes in either this repo or the chezmoi source, so only the skills surface is structurally unresolvable.

## Lineage

```mermaid
flowchart TD
    n0["sase-gw: sase init skills --check fails on unresolvable drift whenever skill sources are uncommitted [closed]"]
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gw](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gw/README.md) | [sase-gw](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`364bb6f`](https://github.com/sase-org/sase/commit/364bb6f9952eed38feb0e3b0ba6c0284538ae01b) | fix(init): defer unresolvable skill deploy drift under --check to a warning | [sase-gw](README.md) | 2026-08-07 11:44:12 EDT |
