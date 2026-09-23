# Bead: sase-16z.9.1 — Fix sase-16z landing defects in sase

[Bead Pages](../README.md) / [sase-16z.9](sase-16z.9.md) / sase-16z.9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16z.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16z.land.md) · **Assignee:** `sase-16z.9.1` · **Size:** medium
**Created:** 2026-09-23 16:32:20 EDT · **Closed:** 2026-09-23 17:09:06 EDT
**Plan:** [202609/usage\_collection\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_collection_landing_fixes.md)

## Description

landing-fixes: resolve the three epic-introduced symvision failures (reuse resolve_provider_cli_command in refresh readiness; privatize the capability-cache dir/invalidate helpers), make executable_fingerprint resolve bare commands through PATH so agy/grok cache entries hit, classify rate limits on JSON-line transport failures, stop 429 matching decimals, remove the stale real-CLI chop test, keep the inline crash path from overwriting finished providers, keep a failed Models-panel reservation read from ending tracking early, and fix stale comments, a test name, and the axe.md opt-out key.

## Notes

[2026-09-23T21:05:30Z · sase-16z.9.1] PROPOSED FOLLOW-UP: symvision still reports unused-public mark_all_message in src/sase/ace/tui/modals/plugins_browser_agent_clis_actions.py at verify time; per plan it belongs to epic sase-171 (already recorded there as a DISCOVERED ISSUE), so just check stays red until sase-171 lands it — not fixed here

[2026-09-23T21:09:06Z · sase-16z.9.1] All 9 landing fixes verified: symvision clean for _probe_meta.py and _capability_cache.py (only remaining failure is sase-171 mark_all_message, recorded as PROPOSED FOLLOW-UP); 228 tests pass across strategy/cache/refresh/runner/codex/grok/muse/agy probes/transport/admission/eligibility/claude/modal/chop suites; ruff/mypy/fmt and all other check gates green

## Dependencies

- **Blocks:** [sase-16z.9.3](sase-16z.9.3.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.9.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.9.1/README.md) | [sase-16z.9.1](sase-16z.9.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4b9da7a`](https://github.com/sase-org/sase/commit/4b9da7a334065f6fb1bb138056890c407a9c5f1e) | fix(sase-16z.9.1): land nine review fixes for usage probes and models panel | [sase-16z.9.1](sase-16z.9.1.md) | 2026-09-23 17:11:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16z.9.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.9.1/README.md

<!-- sase:referenced-by:end -->
