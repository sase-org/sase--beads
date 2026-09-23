# Bead: sase-16z.1 — sase-core: reason-aware attempt recording and rate-limit policy

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q3.md) · **Assignee:** `sase-16z.1` · **Size:** medium
**Created:** 2026-09-23 11:06:10 EDT · **Closed:** 2026-09-23 11:40:28 EDT
**Plan:** [202609/usage\_window\_collection\_service\_tree.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_collection_service_tree.md)

## Description

core-attempt-policy: in the linked sase-core repo, add the `rate_limited` reason code, an optional observation `retry_after_seconds`, reason-aware backoff classes behind an opt-in `adaptive` attempt flag (Retry-After clamping, rate-limit escalation, parking, 1 h drift park, 60 s explicit cooldown), collector-health `retry_at`/`last_failure_reason`, and pruning of superseded-generation schedule rows. Legacy requests must behave exactly as they do today.

## Notes

[2026-09-23T15:40:28Z · sase-16z.1] core-attempt-policy done in linked sase-core: rate_limited reason, observation retry_after (clamped 86400), adaptive attempt fields, schedule streak/park/reason fields, pure refresh_failure_policy (transient/auth/rate-limit-clamp-900-21600/escalation-cap-7200/park-6h/drift-1h), health retry_at+last_failure_reason, gen pruning on write, legacy path byte-identical (5s cooldown, unclamped). Verified: sase tool run check gate succeeded; 118 provider_usage + 7 binding tests green. NOTE FOR LAND AGENT: per phase versioning rule this needs a breaking-change commit marker (feat!: or BREAKING CHANGE footer) since old cores drop new-field rows; I did not commit.

## Dependencies

- **Blocks:** [sase-16z.2](sase-16z.2.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16z.4](sase-16z.4.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.1/README.md) | [sase-16z.1](sase-16z.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@44dbc91`](https://github.com/sase-org/sase-core/commit/44dbc91b909c060a5ba5c53329f4891d0204d057) | feat!: reason-aware adaptive refresh-attempt policy for provider usage | [sase-16z.1](sase-16z.1.md) | 2026-09-23 11:42:05 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16z.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.1/README.md

<!-- sase:referenced-by:end -->
