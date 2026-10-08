# Bead: sase-1hi.1 — sase-core decisions grammar, resolver, quote matcher, and Decision Sheet

[Bead Pages](../README.md) / [sase-1hi](README.md) / sase-1hi.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.5n.md) · **Assignee:** `sase-1hi.1` · **Size:** large
**Created:** 2026-10-07 18:48:23 EDT
**Plan:** [202610/plan\_decisions.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions.md)

## Description

core: in the linked sase-core repo, add the `decisions:` grammar and diagnostics (including the system-written `answer`/`decided_by`/`decided_via` fields, a new Archived validation mode, branch callouts, and the reserved `phases[].when`), the additive validated-plan wire, the frozen payload definition record, the default/clamp resolver, the human-quote matcher, the Decision Sheet with its summary sentence and implementer prompt block, a definitions digest, and pyo3 bindings with tests.

## Notes

[2026-10-08T00:33:58Z · sase-1hi.1.1.2] resolve phase API (sase-1hi.1.1.2): plan_decisions_payload(validated plan object, host_facts {id: {requested_verified, provenance: asked|not_asked|quote_not_found|inherited, resolved: [{selector, kind: note|web|strand, scope: project|home, path, type: core|reference|web|strand, exists, strands?}]}}) -> [definitions {id, kind, ask, why?, choices, default (authored), effective_default, memory?, requested?, provenance?, requested_verified, resolved}]; memory authored-true + unverified clamps effective to false, missing facts fail closed to not_asked; plan_decisions_digest(definitions) -> 64-hex SHA-256 over canonical JSON; plan_decisions_resolve(definitions, submitted object, caller human|agent|auto) -> {values, rows[{id, value, source: default|submitted|clamped, changed}], errors[{id, code, message, allowed, default?}]}; agent true-on-unverified-memory refused with memory_decision_requires_human; auto ignores valid overrides (source default|clamped) but keeps unknown-id/invalid errors; errors non-empty => values {}; omitted vs explicit defaults agree on values

## Dependencies

- **Blocks:** [sase-1hi.3](sase-1hi.3.md) ◐ · ⧖ 2026-10-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.1.md) | [sase-1hi.1](sase-1hi.1.md) | 0 |
