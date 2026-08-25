# Bead: sase-tn.1 — Drop the machine-global \`feature\` disable from chezmoi

[Bead Pages](../README.md) / [sase-tn](README.md) / sase-tn.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0dk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0dk.md) · **Assignee:** `sase-tn.1` · **Size:** small
**Created:** 2026-08-25 12:36:21 EDT · **Closed:** 2026-08-25 12:39:13 EDT
**Plan:** [202608/feature\_task\_type\_default.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_task_type_default.md)

## Description

global-default: delete the `bead.task_types` block from the chezmoi-managed `home/dot_config/sase/sase.yml` so no machine-global layer turns `agent_creatable` off for `builtin@feature`. This phase's commit runs chezmoi's own `after` hook, which redeploys `~/.config/sase/sase.yml` and makes the change live for every project on the machine.

## Notes

[2026-08-25T16:39:13Z · sase-tn.1] Deleted the bead.task_types block (lines 3-7) from chezmoi's home/dot_config/sase/sase.yml, removing the machine-global builtin@feature agent_creatable:false override. Verified: grep for builtin@feature in the chezmoi repo returns no matches, grep -c '^bead:' on the file returns 0, and the file still parses as valid YAML. No other lines touched. Left chezmoi/apply/update untouched per plan D3 — redeploy happens via chezmoi's own commit_hooks.after when this phase is committed. No epic-symbol leftovers (sase bead epic-symbols sase-tn.1 reported none).

## Dependencies

- **Blocks:** [sase-tn.2](sase-tn.2.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tn.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tn.1/README.md) | [sase-tn.1](sase-tn.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| chezmoi | [`chezmoi@18ef29d`](https://github.com/bbugyi200/dotfiles/commit/18ef29d0ec0bbc40f609745987da546446349088) | chore(config): drop machine-global feature task-type disable | [sase-tn.1](sase-tn.1.md) | 2026-08-25 12:39:53 EDT |
