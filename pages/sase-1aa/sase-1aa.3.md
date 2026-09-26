# Bead: sase-1aa.3 — Validate shipped size-alias policy from the manifest

[Bead Pages](../README.md) / [sase-1aa](README.md) / sase-1aa.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1t](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1t.md) · **Assignee:** `sase-1aa.3` · **Size:** medium
**Created:** 2026-09-25 22:26:20 EDT · **Closed:** 2026-09-26 06:35:44 EDT
**Plan:** [202609/model\_catalog\_maintenance.md](https://github.com/sase-org/sase--plans/blob/main/202609/model_catalog_maintenance.md)

## Description

model_policy: enforce catalog membership, effort support and descent, provider redundancy, and deliberate selector shape with actionable diagnostics.

## Notes

[2026-09-26T10:35:44Z · sase-1aa.3] Validator src/sase/llm_provider/model_policy.py enforces catalog membership, effort support/descent with supersedes continuation, and 2-provider redundancy with alias/member/Fix diagnostics; grok supersedes link added to models.yml; 13 new policy tests pass plus 71 related (manifest, alias defaults, ladder, advisories) and 79 broader incl. renderer provider-import-free; symvision/ruff/mypy clean; sase-1aa.3 epic-symbols cleared, new validator symbols re-keyed to sase-1aa.4 for docs-phase consumption

## Dependencies

- **Depends on:** [sase-1aa.2](sase-1aa.2.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-1aa.4](sase-1aa.4.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aa.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aa.3/README.md) | [sase-1aa.3](sase-1aa.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e2b4625`](https://github.com/sase-org/sase/commit/e2b462548c2becdf846ed2773450c4542b56de04) | feat(llm-provider): add executable model policy over models.yml | [sase-1aa.3](sase-1aa.3.md) | 2026-09-26 06:38:07 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19p.4.land][1] | Need follow-up bead status | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-19p.4.land/README.md

<!-- sase:referenced-by:end -->
