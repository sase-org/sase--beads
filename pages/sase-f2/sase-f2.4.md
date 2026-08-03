# Bead: sase-f2.4 — Launch-time provenance capture removal

[Bead Pages](../README.md) / [sase-f2](README.md) / sase-f2.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ej.land.w2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.land.w2/README.md) · **Assignee:** `sase-f2.4` · **Size:** small
**Created:** 2026-08-03 14:48:41 EDT
**Plan:** [202608/revert\_stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_stored_prompt_duality.md)

## Description

provenance: stop writing `xprompt_sources.json` at launch, reduce the source-collection and hosted-URL modules to exactly the definition-resolution surface `sase xprompt show` calls, and delete the record loading and link rewriting helpers that only the reverted stores used.

## Dependencies

- **Depends on:** [sase-f2.1](sase-f2.1.md) ◐
- **Depends on:** [sase-f2.2](sase-f2.2.md) ✓
- **Depends on:** [sase-f2.3](sase-f2.3.md) ◐
- **Blocks:** [sase-f2.5](sase-f2.5.md) ◐
