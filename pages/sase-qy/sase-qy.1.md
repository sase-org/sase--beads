# Bead: sase-qy.1 — Shared persistent query-bar chrome

[Bead Pages](../README.md) / [sase-qy](README.md) / sase-qy.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07r](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07r.md) · **Assignee:** `sase-qy.1` · **Size:** medium
**Created:** 2026-08-19 10:02:23 EDT · **Closed:** 2026-08-19 11:02:47 EDT
**Plan:** [202608/artifacts\_persistent\_query\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_persistent_query_bar.md)

## Description

chrome: give FilterBar a real idle presentation -- a profile-driven, syntax-highlighted closed display with an empty-query placeholder, accent-driven border/sigil/completion colors, and click-to-edit -- and adopt it on the two bars that are already persistent.

## Notes

[2026-08-19T15:02:47Z · sase-qy.1] Verified: 75 targeted tests pass (highlighting, profile_highlighting, filter_bar persistent widget tests, commit/patch filter bar + pane click-routing); mypy clean on src (3502 files); ruff check + format clean on all touched files; epic-symbols empty. Pre-existing failures in tests/ace/tui/widgets/ (agent_model_section, summary_fold_*, etc.) traced to a ProviderDisableStateError environment issue that reproduces identically on clean master (stash-verified) -- unrelated to this phase's scope.

## Dependencies

- **Blocks:** [sase-qy.2](sase-qy.2.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qy.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qy.1/README.md) | [sase-qy.1](sase-qy.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c9cb183`](https://github.com/sase-org/sase/commit/c9cb183c46055f6cd853b08490e38f647467f65e) | feat(ace): give FilterBar shared idle chrome and adopt it on Commit/Patch bars | [sase-qy.1](sase-qy.1.md) | 2026-08-19 11:33:13 EDT |
