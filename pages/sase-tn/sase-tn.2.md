# Bead: sase-tn.2 — Neutralize the builtin refusal copy and retire the sase re-enable override

[Bead Pages](../README.md) / [sase-tn](README.md) / sase-tn.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0dk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0dk.md) · **Assignee:** `sase-tn.2` · **Size:** small
**Created:** 2026-08-25 12:36:22 EDT · **Closed:** 2026-08-25 12:59:43 EDT
**Plan:** [202608/feature\_task\_type\_default.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_task_type_default.md)

## Description

sase-cleanup: in the sase repo, rewrite the `create_refusal` copy in `_feature_spec()` so it stops asserting that feature beads belong only to SASE, delete the now-dead `use: builtin@feature` override from `sase/sase.yml`, extend the builtin copy test, and regenerate `sase/task_types.json`. Gated on `global-default` because that regeneration reads the live machine-global config layer.

## Notes

[2026-08-25T16:59:43Z · sase-tn.2] Updated feature refusal copy, removed the redundant SASE project feature override, regenerated sase/task_types.json, and verified with pytest tests/task_types/test_builtin.py, git diff --check, sase bead task-type list -a, just check, and sase bead epic-symbols sase-tn.2.

## Dependencies

- **Depends on:** [sase-tn.1](sase-tn.1.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tn.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tn.2/README.md) | [sase-tn.2](sase-tn.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5ca05f6`](https://github.com/sase-org/sase/commit/5ca05f6a57a6b4513559e04c62d08c80b3ca7f6b) | feat(task-types): neutralize feature refusal copy | [sase-tn.2](sase-tn.2.md) | 2026-08-25 13:01:05 EDT |
