# Bead: sase-tn.2 — Neutralize the builtin refusal copy and retire the sase re-enable override

[Bead Pages](../README.md) / [sase-tn](README.md) / sase-tn.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0dk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0dk.md) · **Assignee:** `sase-tn.2` · **Size:** small
**Created:** 2026-08-25 12:36:22 EDT
**Plan:** [202608/feature\_task\_type\_default.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_task_type_default.md)

## Description

sase-cleanup: in the sase repo, rewrite the `create_refusal` copy in `_feature_spec()` so it stops asserting that feature beads belong only to SASE, delete the now-dead `use: builtin@feature` override from `sase/sase.yml`, extend the builtin copy test, and regenerate `sase/task_types.json`. Gated on `global-default` because that regeneration reads the live machine-global config layer.

## Dependencies

- **Depends on:** [sase-tn.1](sase-tn.1.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tn.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tn.2/README.md) | [sase-tn.2](sase-tn.2.md) | 0 |
