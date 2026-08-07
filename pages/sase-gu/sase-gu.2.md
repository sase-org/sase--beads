# Bead: sase-gu.2 — Write and migrate every enabled project to the new shape

[Bead Pages](../README.md) / [sase-gu](README.md) / sase-gu.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.um](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.um/README.md) · **Assignee:** `sase-gu.2` · **Size:** medium
**Created:** 2026-08-07 09:34:31 EDT · **Closed:** 2026-08-07 10:26:49 EDT
**Plan:** [202608/split\_sidecar\_config.md](https://github.com/sase-org/sase--plans/blob/main/202608/split_sidecar_config.md)

## Description

migrate_configs: make sase repo init emit the two-bucket mapping, update the operator-facing guidance strings and docs examples, and migrate the sase, actstat, and bob-cli project configs to the new shape.

## Notes

[2026-08-07T14:37:05Z · sase-gu.2] sase repo init now writes the role-keyed repos.sidecar mapping (builtin: plans/beads/agents, custom: research), refuses a legacy-list config with a migration error, and the agents consent prompt + docs/configuration.md + docs/init.md describe the two buckets. Migrated sase/sase.yml here and committed actstat (f63e496) and bob-cli (8bbef6e) in their own checkouts. Verified: just check-full green (all lint gates + full suite); workspace-venv sase doctor reports config.repos OK and 4 init planners current; sase repo list shows the same four sidecar rows in the same order for sase, actstat, and bob-cli; sase init memory --check reports nothing to regenerate, so AGENTS.md and its shims are unchanged; ~/.config/sase/sase.yml still has no repos.sidecar block (its only 'sidecars' key is an unrelated file_hooks entry).

## Dependencies

- **Depends on:** [sase-gu.1](sase-gu.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-gu.3](sase-gu.3.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gu.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gu.2/README.md) | [sase-gu.2](sase-gu.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f77bc98`](https://github.com/sase-org/sase/commit/f77bc9891e801c5003896aff76bbe471668f4c67) | feat(repos): write and document repos.sidecar as the builtin/custom mapping | [sase-gu.2](sase-gu.2.md) | 2026-08-07 10:33:42 EDT |
