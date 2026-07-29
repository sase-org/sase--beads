# Bead: sase-aq.4 — Per-invocation key qualification at swarm expansion

[Bead Pages](../README.md) / [sase-aq](README.md) / sase-aq.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-aq.4` · **Size:** medium
**Created:** 2026-07-29 13:07:37 UTC · **Closed:** 2026-07-29 14:19:04 UTC
**Plan:** [202607/agent\_name\_key\_markers.md](https://github.com/sase-org/sase--plans/blob/main/202607/agent_name_key_markers.md)

## Description

qualify: rewrite unqualified `{@<id>}` markers to `{@<xprompt>.<stamp>.<id>!}` while expanding an xprompt swarm so each invocation gets its own key space, leaving `!` markers untouched.

## Notes

[2026-07-29T14:19:04Z · sase-aq.4] Implemented per-invocation keyed-marker qualification with timestamp-plus-counter namespaces, independent counter threading, protected fenced/disabled regions, nested-swarm handling, and launcher regression coverage. Verified 49 focused tests and the full suite (23523 passed, 7 skipped); formatting, ruff, mypy, pyscripts, symvision, toobig, diff checks, and committed-plan validation passed. just check reached SASE validation and stopped only on unrelated pre-existing provider-skill drift and missing axe_chop_reports plan links.

[2026-07-29T14:21:37Z · sase-aq.4] Verified 49 focused tests and the full suite (23,523 passed, 7 skipped); formatting, lint stages, and committed-plan validation passed. just check stopped only on unrelated existing provider-skill drift and missing axe_chop_reports plan links.

## Dependencies

- **Depends on:** [sase-aq.3](sase-aq.3.md) ✓
- **Blocks:** [sase-aq.5](sase-aq.5.md) ✓
- **Blocks:** [sase-aq.6](sase-aq.6.md) ✓
