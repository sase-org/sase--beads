# Bead: sase-h8.7 — Fix the non-ACE store, tooling, and subprocess family

[Bead Pages](../README.md) / [sase-h8](README.md) / sase-h8.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v5/README.md) · **Assignee:** `sase-h8.7` · **Size:** medium
**Created:** 2026-08-07 18:05:53 EDT
**Plan:** [202608/parallel\_suite\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/parallel_suite_flake_class.md)

## Description

tooling: fix the triaged non-ACE nodes — bead-store clusters, selection and run_pytest tooling tests, the coverage-context cache, and the subprocess/pipe races — while leaving the bead-mutation lock timeout tracked separately under sase-e2 alone.

## Notes

[2026-08-08T01:50:24Z · sase-h8.3] TRIAGE (from sase-h8.3): the phase-triage table is research:202608/parallel_suite_flake_triage.md, committed to the research sidecar. It measures family membership at master 47b9f0017 and corrects the epic plan in several places, including the family your phase owns. Read it before starting; see also the sase-h8.3 bead notes.

## Dependencies

- **Depends on:** [sase-h8.2](sase-h8.2.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h8.3](sase-h8.3.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h8.8](sase-h8.8.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.7/README.md) | [sase-h8.7](sase-h8.7.md) | 0 |
