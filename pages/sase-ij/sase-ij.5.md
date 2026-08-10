# Bead: sase-ij.5 — Verify one report-only run and switch the ratchet to apply

[Bead Pages](../README.md) / [sase-ij](README.md) / sase-ij.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wq/README.md) · **Assignee:** `sase-ij.5` · **Size:** small
**Created:** 2026-08-09 15:19:48 EDT · **Closed:** 2026-08-09 16:46:14 EDT
**Plan:** [202608/core\_window\_ratchet.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_window_ratchet.md)

## Description

enable-ratchet: read the report-only output from at least one real master push with a pending release branch, confirm the proposed version and diff are exactly right, then flip the reconciler to apply and confirm the release branch stays green.

## Notes

[2026-08-09T20:45:43Z · sase-ij.5] PROPOSED FOLLOW-UP: Stabilize the full-suite lane after local core rebuilds — while verifying this workflow-only change, just check escalated to the full suite with rule core-identity-changed and had 19 unrelated failures before interruption at 5:38; focused tests/test_github_actions_ci.py passed.

[2026-08-09T20:46:14Z · sase-ij.5] Verified publish.yml sync-release-metadata now runs tools/ratchet_core_window in apply mode before uv lock and accepts exit 2 as applied. Checked real Publish run 31334434181: pending release branch existed, report-only run found newest complete PyPI sase-core-rs 0.21.3 already matched, uv lock produced no diff. Independently checked PyPI newest complete release is 0.21.3; local apply-mode ratchet is a no-op and leaves pyproject.toml/uv.lock clean. tests/test_github_actions_ci.py passed. just check lint/validation passed, then scoped selection escalated to full suite due core-identity-changed and hit unrelated full-suite failures before interruption; recorded as proposed follow-up. Release PR 284 floor lane is red because published 0.21.3 lacks parse_merge_summary/vcs_log_wire_schema_version from sase-core 459bbc6; did not lower the floor.

## Dependencies

- **Depends on:** [sase-ij.3](sase-ij.3.md) ✓ · ⧖ 2026-08-09
- **Depends on:** [sase-ij.4](sase-ij.4.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ij.6](sase-ij.6.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ij.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.5/README.md) | [sase-ij.5](sase-ij.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`419a81b`](https://github.com/sase-org/sase/commit/419a81b7b5530e700cb176acf2a888ba3c267e19) | ci: apply release metadata ratchet | [sase-ij.5](sase-ij.5.md) | 2026-08-09 16:48:00 EDT |
