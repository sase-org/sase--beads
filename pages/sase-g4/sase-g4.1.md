# Bead: sase-g4.1 — A header-block validity rule in the Rust plan validator

[Bead Pages](../README.md) / [sase-g4](README.md) / sase-g4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ty](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ty/README.md) · **Assignee:** `sase-g4.1` · **Size:** medium
**Created:** 2026-08-06 09:05:22 EDT · **Closed:** 2026-08-06 09:22:49 EDT
**Plan:** [202608/plan\_header\_validation.md](https://github.com/sase-org/sase--plans/blob/main/202608/plan_header_validation.md)

## Description

core-diagnostic: teach `plan_validate` in sase-core to emit an error diagnostic when the document's leading plan-header block does not parse, carrying the parser's reason and the offending bullet's line, without touching the plan-header block wire schema; then land it and let release-plz publish the wheel.

## Dependencies

- **Blocks:** [sase-g4.3](sase-g4.3.md) ◐ · ⧖ 2026-08-06
- **Blocks:** [sase-g4.5](sase-g4.5.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-g4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-g4.1/README.md) | [sase-g4.1](sase-g4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@508d5d9`](https://github.com/sase-org/sase-core/commit/508d5d99f4ba81ef405a2421662fef6ad9d4a9e1) | feat(plan): reject a malformed plan header block during validation | [sase-g4.1](sase-g4.1.md) | 2026-08-06 09:23:14 EDT |
