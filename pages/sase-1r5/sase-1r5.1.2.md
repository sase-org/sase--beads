# Bead: sase-1r5.1.2 — sase pin bump and shared credential-confirmation retry policy

[Bead Pages](../README.md) / [sase-1r5.1](sase-1r5.1.md) / sase-1r5.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1r5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r5.md) · **Assignee:** `sase-1r5.1.2` · **Size:** medium
**Created:** 2026-11-04 06:54:53 EST · **Closed:** 2026-11-04 08:30:34 EST
**Plan:** [202611/github\_publickey\_retry.md](https://github.com/sase-org/sase--plans/blob/main/202611/github_publickey_retry.md)

## Description

credential-retry-policy: move sase's sase-core CI pin past the classifier change and add the Python wire constant. Add a shared, deadline-aware credential-retry tracker with launch and background budgets, an env kill switch, a per-host exhaustion memo, and a conservative local-SSH-credential precheck that fails fast when no credential exists.

## Notes

[2026-11-04T13:30:34Z · sase-1r5.1.2--1] Verified the sase-core pin and rebuilt binding; sase tool run check passed (exit 0, including the scoped test lane). Re-keyed CredentialRetry and CredentialRetryBudget to open phase sase-1r5.1.3; epic-symbol audit reports none for this phase.

## Dependencies

- **Depends on:** [sase-1r5.1.1](sase-1r5.1.1.md) ✓ · ⧖ 2026-11-04
- **Blocks:** [sase-1r5.1.3](sase-1r5.1.3.md) ◐ · ⧖ 2026-11-04
- **Blocks:** [sase-1r5.1.4](sase-1r5.1.4.md) ✓ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r5.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r5.1.2.md) | [sase-1r5.1.2](sase-1r5.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d008039`](https://github.com/sase-org/sase/commit/d0080395118c2c239433c3bef1c0b0e26a4a5c51) | feat(retryability): add credential confirmation retry policy | [sase-1r5.1.2](sase-1r5.1.2.md) | 2026-11-04 08:32:04 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1r5.1.2--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r5.1.2.md

<!-- sase:referenced-by:end -->
