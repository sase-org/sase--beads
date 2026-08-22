# Bead: sase-s3.4 — Prefer the latest authoritative family plan everywhere

[Bead Pages](../README.md) / [sase-s3](README.md) / sase-s3.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0av](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0av.md) · **Assignee:** `sase-s3.4` · **Size:** small
**Created:** 2026-08-22 13:57:34 UTC · **Closed:** 2026-08-22 14:35:50 UTC
**Plan:** [202608/0ak\_failure\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202608/0ak_failure_recovery.md)

## Description

family_plan_preview_provenance: make replacement plans win in ACE and editor previews while invalidating caches from bounded in-memory member state.

## Notes

[2026-08-22T14:35:26Z · sase-s3.4] PROPOSED FOLLOW-UP: just check full-suite escalation fails outside family-preview patch — setup fast-forwarded linked core, test-scoped escalated on core-identity-changed, and the governed full lane failed in plan gate/completion parity/contract-manifest tests while focused family preview/editor tests passed.

[2026-08-22T14:35:50Z · sase-s3.4] Implemented newest-concrete-family-member plan precedence for ACE/editor previews, cache invalidation via member association tokens, and regressions. Verified: uv run pytest tests/ace/tui/models/test_agent_family_preview_cache.py tests/test_editor_helper_family_catalog.py passed; ruff format --check passed; sase bead epic-symbols sase-s3.4 reported no entries. just check rebuilt linked core, escalated to governed full suite on core-identity-changed, and failed in unrelated plan gate/completion parity/contract manifest tests; recorded PROPOSED FOLLOW-UP on this bead.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s3.4/README.md) | [sase-s3.4](sase-s3.4.md) | 0 |
