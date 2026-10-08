# Bead: sase-1hi.1 — sase-core decisions grammar, resolver, quote matcher, and Decision Sheet

[Bead Pages](../README.md) / [sase-1hi](README.md) / sase-1hi.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.5n.md) · **Assignee:** `sase-1hi.1` · **Size:** large
**Created:** 2026-10-07 18:48:23 EDT · **Closed:** 2026-10-07 22:33:25 EDT
**Plan:** [202610/plan\_decisions.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions.md)

## Description

core: in the linked sase-core repo, add the `decisions:` grammar and diagnostics (including the system-written `answer`/`decided_by`/`decided_via` fields, a new Archived validation mode, branch callouts, and the reserved `phases[].when`), the additive validated-plan wire, the frozen payload definition record, the default/clamp resolver, the human-quote matcher, the Decision Sheet with its summary sentence and implementer prompt block, a definitions digest, and pyo3 bindings with tests.

## Notes

[2026-10-08T00:33:58Z · sase-1hi.1.1.2] resolve phase API (sase-1hi.1.1.2): plan_decisions_payload(validated plan object, host_facts {id: {requested_verified, provenance: asked|not_asked|quote_not_found|inherited, resolved: [{selector, kind: note|web|strand, scope: project|home, path, type: core|reference|web|strand, exists, strands?}]}}) -> [definitions {id, kind, ask, why?, choices, default (authored), effective_default, memory?, requested?, provenance?, requested_verified, resolved}]; memory authored-true + unverified clamps effective to false, missing facts fail closed to not_asked; plan_decisions_digest(definitions) -> 64-hex SHA-256 over canonical JSON; plan_decisions_resolve(definitions, submitted object, caller human|agent|auto) -> {values, rows[{id, value, source: default|submitted|clamped, changed}], errors[{id, code, message, allowed, default?}]}; agent true-on-unverified-memory refused with memory_decision_requires_human; auto ignores valid overrides (source default|clamped) but keeps unknown-id/invalid errors; errors non-empty => values {}; omitted vs explicit defaults agree on values

[2026-10-08T01:49:50Z · sase-1hi.1.1.4] Sheet phase API shapes for the gate phase: plan_decision_sheet(definitions, values: {id: canonical}, review_revision) -> {count, memory_count (#memory rows), changed_count (incl. memory), review_revision, rows[{id, kind, ask, why?, choices, default=effective_default, value, changed, memory?{selectors, resolved, provenance, quote=requested}}]}; plan_decision_summary(sheet, verdict: coder + commit|coder|commit|epic launch, form: short|full) -> full "-> verdict · id=k[ ●] · … · 🧠 notes|no memory edits" (memory only in clause), short "defaults|1 change|N changes[ · 🧠]"; plan_decisions_prompt_block(sheet, decided_by: reviewer|auto|agent, decided_via?: tui|telegram|mobile|cli (absent iff auto), audience: tale_coder|epic_phase|epic_land, inherited?: {sheet, epic_title}) -> header + per-row Implement/ignore or memory grant/skip lines + inherited lines + closing; auto-off memory rows append /sase_new_task (coder) or PROPOSED FOLLOW-UP: (phase/land). Evidence: 19 core sheet tests + 7 py binding tests incl. seven-binding tale+epic/Archived integration pass; sase-core gate red only on pre-existing editor directive matrix failure (repros on clean HEAD, noted as follow-up on sase-1hi.1.1.4).

[2026-10-08T02:33:47Z · sase-1hi.1.1.land] CORE LANDING COMBINED EVIDENCE (sase-1hi.1.1 repairs): warning-only asks preserve full wire (tale/epic x Authoring/Launch/Archived, payload/digest/sheet + Python round-trip; errors still fail); Archived completeness on any stamp incl decided_via-only with absent/empty/partial controls; Unicode byte-safe memory paths with public-validator tests; fence char+length tracking with CRLF/before-after coverage; sheet provenance/kind/shape/selector/count validation for local+inherited and unrequested-only auto follow-ups (asked/inherited quiet) across tale_coder/epic_phase/epic_land plus binding ValueError round-trips. Stable shapes: PlanDecisionWire {id,kind toggle|choice,ask,why?,choices[{key,label}],default bool|key,memory?{selectors},requested?,answer?}; definitions carry authored default + effective_default (unverified memory true->false), provenance asked|not_asked|quote_not_found|inherited, resolved [{selector,kind note|web|strand,scope project|home,path,type core|reference|web|strand,exists,strands?}]; digest 64-hex canonical; resolver caller human|agent|auto with memory_decision_requires_human and clamped/default/submitted sources; sheet {count,memory_count,changed_count,review_revision,rows}; summary verdicts coder + commit|coder|commit|epic launch forms short|full toggles yes|no; prompt audiences tale_coder|epic_phase|epic_land surfaces tui|telegram|mobile|cli. Verification: sase_core decisions 87 pass, sase_core_py plans 12 pass, parity 2 pass, fmt clean; full check only pre-existing for_epic matrix failure reproduced on clean base (on sase-1h7). Legacy parity v3 intact; seven bindings registered. Integration: core HEAD 9ea87c11 only non-epic change (no decisions callers); outer gate owns Python consumers + revision pin. Leave sase-1hi and plan:202610/plan_decisions.md open for waiting land agent.

## Dependencies

- **Blocks:** [sase-1hi.3](sase-1hi.3.md) ✓ · ⧖ 2026-10-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.1.md) | [sase-1hi.1](sase-1hi.1.md) | 0 |
