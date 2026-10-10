# Bead: sase-1j6.9 — Remove the beta flag, document, and replay the incident end to end

[Bead Pages](../README.md) / [sase-1j6](README.md) / sase-1j6.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.47.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.47.linker.w0.md) · **Assignee:** `sase-1j6.9` · **Size:** small
**Created:** 2026-10-09 15:02:08 EDT · **Closed:** 2026-10-09 22:10:55 EDT
**Plan:** [202610/update\_skew\_agent\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/update_skew_agent_auto_restart.md)

## Description

land: delete the agent_auto_restart flag's Off branches and close its bead, write the user-facing doc, add the end-to-end incident replay acceptance test, and record the deferred follow-ups.

## Notes

[2026-10-10T01:04:55Z · sase-1j6.9] PROPOSED FOLLOW-UP: Add a decisions-web record for update-skew auto-restart (at most once per lineage, pre-provider only, signature-witness-probe gated, out of process; reopen when release pinning lands) — skipped per epic decision_record=no

[2026-10-10T01:05:04Z · sase-1j6.9] PROPOSED FOLLOW-UP: P1 — CI import-recording test forbidding post-provider first imports; turn preload_post_gate_modules into a test-enforced invariant

[2026-10-10T01:05:09Z · sase-1j6.9] PROPOSED FOLLOW-UP: P2 — release-pinning epic with immutable per-process releases so Tier 1-2 skew becomes impossible

[2026-10-10T01:05:14Z · sase-1j6.9] PROPOSED FOLLOW-UP: post-provider resume-in-place mode (this epic only notifies for post-provider deaths)

[2026-10-10T01:05:19Z · sase-1j6.9] PROPOSED FOLLOW-UP: sunset the llm_provider.retry.sase entry into agent auto-restart

[2026-10-10T01:05:23Z · sase-1j6.9] PROPOSED FOLLOW-UP: %auto parity for manual ,x and sase agent restart

[2026-10-10T02:10:47Z · sase-1j6.9--2] PROPOSED FOLLOW-UP: full check has 13 pre-existing failures that reproduce identically with this phase stashed (completion snapshot/drift/mutex-groups, agents help sort, wire trailing-field, config schema, query-profile vocab, marker audits x2, tui import budget, pypi lock path, file-hook bob digest, timezone guard) — land agent to triage

[2026-10-10T02:10:55Z · sase-1j6.9--2] Beta flag removed (Off branches deleted, registry/schema/facade updated), docs/agent_auto_restart.md written plus axe.md/notifications.md updates, incident-replay acceptance test added; verified 18 auto-restart tests pass and symvision lint clean; full check 13 failures reproduce identically on stashed base tree (pre-existing, recorded as follow-up)

## Dependencies

- **Depends on:** [sase-1j6.1](sase-1j6.1.md) ✓ · ⧖ 2026-10-09
- **Depends on:** [sase-1j6.6](sase-1j6.6.md) ✓ · ⧖ 2026-10-09
- **Depends on:** [sase-1j6.7](sase-1j6.7.md) ✓ · ⧖ 2026-10-09
- **Depends on:** [sase-1j6.8](sase-1j6.8.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.9.md) | [sase-1j6.9](sase-1j6.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`05bab36`](https://github.com/sase-org/sase/commit/05bab368afe5275c26ac2e3be12d89dab32ffeef) | feat(auto-restart): remove beta flag, document, and replay incident end to end | [sase-1j6.9](sase-1j6.9.md) | 2026-10-09 22:12:40 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.9--2][1] | Need phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.9.md

<!-- sase:referenced-by:end -->
