# Bead: sase-4n.1 — Phase 1: Command Group Migration and Skill Contract

[Bead Pages](../README.md) / [sase-4n](README.md) / sase-4n.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-4n.1`
**Created:** 2026-06-13 13:58:26 UTC
**Plan:** [202606/plan\_command\_subcommands.md](https://github.com/sase-org/sase--plans/blob/main/202606/plan_command_subcommands.md)

## Notes

Phase 1 complete. Converted 'sase plan' into a command group with sorted approve/list/propose children; bare 'sase plan' now parses as list through the existing default-list parser behavior. Moved proposal behavior to 'sase plan propose <plan_file>' via a dispatcher and dedicated proposal handler while preserving archive/marker/pulse/runner-termination behavior. Updated the /sase_plan source template to use 'sase plan propose sase_plan_<name>.md', regenerated/applied live skills, and added parser, handler, help, and skill-source regression tests. Verified focused pytest, live Codex/Claude/Gemini/Qwen skill text, git diff --check, and full 'just check' with inherited SASE/Codex workspace env vars sanitized.

## Dependencies

- **Blocks:** [sase-4n.2](sase-4n.2.md) ✓
