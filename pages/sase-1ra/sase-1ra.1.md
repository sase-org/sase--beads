# Bead: sase-1ra.1 — -p accepts a project's display name, alias, or key (sase-zo)

[Bead Pages](../README.md) / [sase-1ra](README.md) / sase-1ra.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.18d](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.18d.md) · **Assignee:** `sase-1ra.1` · **Size:** small
**Created:** 2026-11-04 17:59:12 EST · **Closed:** 2026-11-04 18:38:04 EST
**Plan:** [202611/next\_ten\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_ten_task_beads.md)

## Description

project_names: canonicalize -p/--project through the project registry in resolve_project_context, list candidates on ambiguity, and add display-name-differs-from-key regressions (sase-zo).

## Notes

[2026-11-04T23:25:44Z · sase-1ra.1] TASK RESOLVED: sase-zo — -p canonicalized through project registry in resolve_project_context (key/display/alias case-insensitive, ambiguity exits 2 with candidates, registered wins over stray); sase repo list -p sase now works via checkout code; regressions in tests/main/test_project_ref_canonicalization.py (7 passed); full just check handed to monitor run 7603580eb32df95ec89243cea3884f1d

[2026-11-04T23:37:56Z · sase-1ra.1] PROPOSED FOLLOW-UP: tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms fails on raw_xprompt.md strings in tests/agents_sync/test_deferred_prompt_archive/ (3 findings); reproduces identically on clean base tree, unrelated to this phase

[2026-11-04T23:38:04Z · sase-1ra.1] Verified: -p canonicalized through registry in resolve_project_context (key/display/alias, case-insensitive, ambiguity exits 2, registered wins over stray); sase repo list -p sase and -p SASE work; 7 new regression tests pass; 66 related tests pass; full scoped selection 1732 passed with 1 pre-existing macro-terminology failure confirmed identical on clean base tree (recorded as PROPOSED FOLLOW-UP); all 18 lint/validation stages of check run 7603580eb32df95ec89243cea3884f1d exit 0; epic-symbols empty

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ra.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ra.1.md) | [sase-1ra.1](sase-1ra.1.md) | 0 |
