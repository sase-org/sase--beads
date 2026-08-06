# Bead: sase-g4.4 — An actionable failure at the archive boundary

[Bead Pages](../README.md) / [sase-g4](README.md) / sase-g4.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ty](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ty/README.md) · **Assignee:** `sase-g4.4` · **Size:** small
**Created:** 2026-08-06 09:06:18 EDT
**Plan:** [202608/plan\_header\_validation.md](https://github.com/sase-org/sase--plans/blob/main/202608/plan_header_validation.md)

## Description

archive-guard: `archive_plan_file` projects header sections before it validates, so a malformed document escapes as a bare `validation: ...` ValueError with no path, line, or remedy; make the boundary refuse a malformed source before it mutates anything and fail with the diagnostic envelope.

## Dependencies

- **Depends on:** [sase-g4.3](sase-g4.3.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-g4.5](sase-g4.5.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-g4.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-g4.4/README.md) | [sase-g4.4](sase-g4.4.md) | 0 |
