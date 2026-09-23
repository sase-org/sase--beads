# Bead: sase-16z.4 — Rate-limit classification and reason-aware attempt plumbing

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q3.md) · **Assignee:** `sase-16z.4` · **Size:** medium
**Created:** 2026-09-23 11:06:13 EDT · **Closed:** 2026-09-23 13:58:55 EDT
**Plan:** [202609/usage\_window\_collection\_service\_tree.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_collection_service_tree.md)

## Description

rate-limit-plumbing: move the core pin, add a shared rate-limit/Retry-After classifier that every collector consults, normalize `not_installed`, and pass the reason code, Retry-After, and `adaptive=True` into every recorded attempt. Render the new collector-health retry information in `sase usage list -v` and the Models panel, and update the usage docs.

## Notes

[2026-09-23T17:58:16Z · sase-16z.4] PROPOSED FOLLOW-UP: just check symvision gate flags pre-existing unused-public ClanSummaryDigest in ace tribe clan summaries (untouched by this phase; fails at HEAD too)

[2026-09-23T17:58:55Z · sase-16z.4] Core pin ratcheted to cfe1902a (bindings gate passes; attempt binding verified reason_code/adaptive/Retry-After clamp). Added detect_rate_limit classifier consulted first by all five collectors (incl. agy stderr/non-JSON), normalized not_installed to unsupported for muse/agy/grok, plumbed reason+Retry-After+adaptive=True through runner attempts, rendered retry info in usage list -v plain+rich and Models detail, updated llms.md and configuration.md docs. Verified: full test files for strategy/presentation/models-rendering/claude/agy/codex/grok/muse probes/refresh-runner/refresh/store/probe all green; just check green except pre-existing symvision ClanSummaryDigest flag (untouched file, noted as follow-up).

## Dependencies

- **Depends on:** [sase-16z.1](sase-16z.1.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-16z.3](sase-16z.3.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16z.5](sase-16z.5.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.4/README.md) | [sase-16z.4](sase-16z.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ed8172f`](https://github.com/sase-org/sase/commit/ed8172fdabebbc60bbe29df9473ea899129de4a7) | feat(llm-provider): rate-limit classification and reason-aware attempt plumbing | [sase-16z.4](sase-16z.4.md) | 2026-09-23 14:00:36 EDT |
