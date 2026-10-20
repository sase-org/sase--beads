# Bead: sase-1n6.5.1.2 — Supply verified published core artifacts to the CI setup action

[Bead Pages](../README.md) / [sase-1n6.5.1](sase-1n6.5.1.md) / sase-1n6.5.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1n6.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.md) · **Size:** medium
**Created:** 2026-10-19 20:21:18 EDT · **Closed:** 2026-10-19 22:34:49 EDT
**Plan:** [202610/published\_core\_qualification.md](https://github.com/sase-org/sase--plans/blob/main/202610/published_core_qualification.md)

## Description

published-core: extend build-core and setup-sase to use the manifest's hashed PyPI wheel and tag-built LSP while preserving default source builds.

## Notes

[2026-10-20T02:34:40Z · sase-1n6.5.1.2--2] Published-core contract: build-core.yml accepts ref/core-source(default source)/core-version/manifest-artifact(default candidate-build)/probe-core-version; published mode downloads the sealed manifest, runs release_candidate published-core, uploads the same sase-core-wheel shape plus probe-core-version.txt in probe mode, and exposes core-version/probe outputs; setup-sase accepts optional expected-core-version and refuses on installed-version mismatch; probe mode needs an older complete core and never rewrites candidate-manifest.json

[2026-10-20T02:34:49Z · sase-1n6.5.1.2--2] Verified: tests/test_release_candidate_published_core.py, tests/test_github_actions_build_core.py, tests/test_github_actions_setup_sase.py, tests/test_github_actions_ci_workflow.py, tests/test_github_actions_ci_master_gate.py, tests/test_contract_manifest.py; sase tool run check 4291056ffcced4e489f8892ad81459f3 exit 0 green (epic-symbols clean)

## Dependencies

- **Depends on:** [sase-1n6.5.1.1](sase-1n6.5.1.1.md) ✓ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.5.1.3](sase-1n6.5.1.3.md) ◐ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.5.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.1.2.md) | [sase-1n6.5.1.2](sase-1n6.5.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9edbacd`](https://github.com/sase-org/sase/commit/9edbacd4efbde6ed91c1e5da5c37d9918e9e6e81) | feat(ci): supply verified published core artifacts to setup-sase | [sase-1n6.5.1.2](sase-1n6.5.1.2.md) | 2026-10-19 22:36:02 EDT |
