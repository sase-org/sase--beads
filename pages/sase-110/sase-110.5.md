# Bead: sase-110.5 — The /sase\_sudo generated skill and the raw-sudo PreToolUse guard

[Bead Pages](../README.md) / [sase-110](README.md) / sase-110.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0kl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0kl.md) · **Assignee:** `sase-110.5` · **Size:** medium
**Created:** 2026-09-14 11:33:17 EDT · **Closed:** 2026-09-14 13:26:50 EDT
**Plan:** [202609/agent\_sudo\_requests.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_sudo_requests.md)

## Description

skill-guard: author the generated /sase_sudo skill teaching the request contract, add the chezmoi-managed PreToolUse deny for raw sudo in agent Bash calls, and revise the 'SASE never uses sudo' user-facing copy.

## Notes

[2026-09-14T17:26:09Z · sase-110.5] PROPOSED FOLLOW-UP: Deploy generated /sase_sudo provider SKILL.md files from the landed SASE revision with sase skill init --force, then apply/update chezmoi - preview in this phase showed all seven provider targets missing, and generated-skills policy keeps deployment out of dirty unlanded source.

[2026-09-14T17:26:50Z · sase-110.5] Implemented /sase_sudo generated skill source, reviewed-sudo wording updates, and Claude raw-sudo PreToolUse guard in chezmoi; verified with primary just fmt, targeted pytest for skill/copy tests, sase skill init --diff -p claude preview, primary just check passing with full-suite escalation, chezmoi just fmt, bashunit guard tests, chezmoi just check, and epic-symbols empty.

## Dependencies

- **Depends on:** [sase-110.2](sase-110.2.md) ✓ · ⧖ 2026-09-14
- **Blocks:** [sase-110.7](sase-110.7.md) ◐ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-110.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-110.5/README.md) | [sase-110.5](sase-110.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`378f18b`](https://github.com/sase-org/sase/commit/378f18b2ef0ccb6b12a91408ddf9adb80fa8511e) | feat(skills): add reviewed sudo request guidance | [sase-110.5](sase-110.5.md) | 2026-09-14 13:28:46 EDT |
| chezmoi | [`chezmoi@ca9aa21`](https://github.com/bbugyi200/dotfiles/commit/ca9aa21d3ff2b558ecd8b422526c87cc2ff0b16a) | feat(claude): deny raw sudo in agent Bash hooks | [sase-110.5](sase-110.5.md) | 2026-09-14 13:31:24 EDT |
