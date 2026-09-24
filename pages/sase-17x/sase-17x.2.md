# Bead: sase-17x.2 — Command Line spec contract

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qs](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qs.md) · **Assignee:** `sase-17x.2` · **Size:** medium
**Created:** 2026-09-24 11:29:19 EDT · **Closed:** 2026-09-24 11:49:46 EDT
**Plan:** [202609/command\_line\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_panel.md)

## Description

spec-contract: extend the completion spec with required/metavar/default/value_hint and per-command run policy, writes and confirms data. Add `sase completion spec -d/--descriptions` and an identity-keyed on-disk spec cache that is built in a subprocess.

## Notes

[2026-09-24T15:49:46Z · sase-17x.2] spec-contract done: model/build carry required/metavar/default/value_hint + run_policy/writes/stdin; new run_policy.py (verified all table paths vs live parser) and command_line_spec.py (subprocess identity-keyed cache); completion spec -d flag; snapshot regenerated; 12 new spec-contract tests + 33 existing completion tests pass; ruff/mypy clean; just check blocked only by pre-existing symvision _failure_count flags in untouched files

## Dependencies

- **Blocks:** [sase-17x.3](sase-17x.3.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.5](sase-17x.5.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.2/README.md) | [sase-17x.2](sase-17x.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`db4266e`](https://github.com/sase-org/sase/commit/db4266e1cd1c853bfe3a176a053ef2aa0c80dbde) | feat(completion): Command Line spec contract (sase-17x.2) | [sase-17x.2](sase-17x.2.md) | 2026-09-24 11:51:25 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.2/README.md

<!-- sase:referenced-by:end -->
