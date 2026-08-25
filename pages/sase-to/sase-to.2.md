# Bead: sase-to.2 — bugyi-chops release readiness

[Bead Pages](../README.md) / [sase-to](README.md) / sase-to.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0dm](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0dm.md) · **Assignee:** `sase-to.2` · **Size:** small
**Created:** 2026-08-25 13:05:36 EDT · **Closed:** 2026-08-25 13:23:20 EDT
**Plan:** [202608/git\_fallback\_and\_bugyi\_chops\_release.md](https://github.com/sase-org/sase--plans/blob/main/202608/git_fallback_and_bugyi_chops_release.md)

## Description

chops_release_readiness: repair the red typed-launch integration tests, harden the trusted-publishing artifact handoff, and correct installation documentation without changing the unreleased 0.7.0 version.

## Notes

[2026-08-25T17:23:20Z · sase-to.2] Fixed the 3 red toobig_split tests (test_sase_planning_emits_one_summary_and_promotes_a_surviving_tail, test_sase_bridge_launches_eligible_file_after_admission, test_sase_bridge_promotes_next_basename_member_when_first_skips) by widening override_flags(typed_launch_units=True) scopes to cover all directive-parsing calls (plan_chop_proposals/extract_prompt_directives and the shared _assert_planned_prompts_use_medium_model helper), not just launch_chop_proposals. Verified against the dev sase SDK venv (built via just install + maturin) with SASE_FEATURE_FLAGS unset and an isolated SASE_HOME so the beta flag genuinely defaults off -- confirmed the unfixed test file fails 3/95 under that condition and the fixed file passes 95/95. Hardened publish.yml: canonical https://pypi.org/project/bugyi-chops/ environment URL, if-no-files-found: error on the dist/ upload, explicit packages-dir: dist/ on the pypi-publish action. Corrected README's -g claim to describe it as a built VCS snapshot/force install, not a dev install, and pointed to the existing Development and releases section. project.version stayed 0.7.0; ran just check (ruff format/check, mypy, full pytest w/ 92.75% coverage, build, twine check) green under the same flag-disabled setup; inspected wheel/sdist contents -- no .deps or test/build debris packaged.

## Dependencies

- **Blocks:** [sase-to.3](sase-to.3.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-to.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-to.2/README.md) | [sase-to.2](sase-to.2.md) | 0 |
