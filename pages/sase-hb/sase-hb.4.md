# Bead: sase-hb.4 — Enabled-project and chezmoi source migration

[Bead Pages](../README.md) / [sase-hb](README.md) / sase-hb.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vh/README.md) · **Assignee:** `sase-hb.4` · **Size:** small
**Created:** 2026-08-07 22:51:36 EDT · **Closed:** 2026-08-08 01:25:53 EDT
**Plan:** [202608/xprompt\_skill\_directories.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_skill_directories.md)

## Description

source-migrations: re-audit enabled projects and move every personal skill source and reference to the canonical layout.

## Notes

[2026-08-08T05:25:28Z · sase-hb.4] PROPOSED FOLLOW-UP: chezmoi apply will not remove the orphaned ~/sase/xprompts/bob_query.md after this source move (chezmoi has no .chezmoiremove entries in this repo yet), and migrating the config-only sase_gmail skill out of the athena-only sase_athena.yml into the host-agnostic home/sase/skills/sase_gmail.md widens its deployment from athena-only to every chezmoi-managed host (the canonical skill contract has no host-scoping mechanism, and the gog wrapper is already deployed to all hosts, so this looks intentional/safe, but Phase 5 should confirm both the orphan cleanup and the multi-host availability before/while applying chezmoi.

[2026-08-08T05:25:53Z · sase-hb.4] Re-audited enabled projects (actstat, bob-cli, sase) and chezmoi for skill: frontmatter/config declarations and legacy #<skill> xprompt-form references outside the canonical skills tree: actstat and bob-cli have zero skill sources (no sase/xprompts or sase/skills dirs at all, confirmed zero-result), and sase's own project-level sase/xprompts/ (sync.md, reads.md) has no skill declarations. In chezmoi, migrated home/sase/xprompts/bob_query.md -> home/sase/skills/bob_query.md via git mv (preserves history), and additionally discovered and migrated a config-based skill missed by the original inventory: sase_athena.yml's xprompts.sase_gmail (skill: true) block, which is now rejected by the Phase 2 config-skill-rejection code, into a new home/sase/skills/sase_gmail.md file with identical content/description, removing the stale config block. Verified via the actual sase.xprompt loader (.venv/bin/python + loader_skills._load_skills_from_dir against the chezmoi skills dir after just install) that both files load with zero load issues and produce the expected xprompt reference names skills/bob_query and skills/sase_gmail while keeping skill_name bob_query/sase_gmail unchanged, so #skills/bob_query and #skills/sase_gmail resolve while /bob_query and /sase_gmail are untouched. Confirmed no #bob_query/#sase_gmail (or any of the 16 bundled skill names) old-form references exist anywhere in chezmoi, actstat, bob-cli, or sase outside historical plan docs. Previewed the chezmoi effect with 'chezmoi diff --source' against the live home dir: only the 3 expected file changes appear (plus one pre-existing unrelated nvim-script diff). Kept this phase source-only per the plan: did not run sase skill init, did not apply chezmoi, and made no changes inside the sase repo itself (only chezmoi). Recorded a PROPOSED FOLLOW-UP for Phase 5 about orphan cleanup of the old xprompts/bob_query.md path and the athena-only -> all-hosts scope widening for sase_gmail.

[2026-08-08T05:26:37Z · sase-hb.4] Verified: chezmoi skill migration confirmed (bob_query.md moved, sase_gmail.md added, stale config block removed); re-close check for publish verification.

## Dependencies

- **Depends on:** [sase-hb.2](sase-hb.2.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-hb.5](sase-hb.5.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hb.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hb.4/README.md) | [sase-hb.4](sase-hb.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| chezmoi | [`chezmoi@bd2ffb2`](https://github.com/bbugyi200/dotfiles/commit/bd2ffb2a556c013de4a9870381014c96c3ef3ba8) | fix(sase): migrate personal skill sources to canonical skills/ layout | [sase-hb.4](sase-hb.4.md) | 2026-08-08 01:27:30 EDT |
