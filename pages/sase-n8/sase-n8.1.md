# Bead: sase-n8.1 — Record the alias resolution trail and its origin at launch

[Bead Pages](../README.md) / [sase-n8](README.md) / sase-n8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03t](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03t.md) · **Assignee:** `sase-n8.1` · **Size:** large
**Created:** 2026-08-16 11:30:45 EDT · **Closed:** 2026-08-16 13:12:56 EDT
**Plan:** [202608/launch\_control\_alias\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/launch_control_alias_history.md)

## Description

provenance: make alias resolution return the ordered trail of alias hops it traversed, give LaunchSelection that trail plus the origin of the request (directive vs no-directive default vs no alias), and persist `model_alias_trail` and `model_alias_origin` into agent_meta.json and prompt-step markers at every launch, reconcile, re-exec, and follow-up write site.

## Notes

[2026-08-16T15:52:12Z · sase-n8.1] Contract note for phases core/adapter: the epic pins "model_alias_trail[0] == model_alias". That holds for every alias reference SASE generates (format_model_directive_value always emits @<name>, and _directive_extract only sets directives.model_alias when the @ prefix was present). It does NOT hold for a hand-typed "%model:large" — a known alias written without @ — where directives.model_alias is None but resolution really did traverse @large. The provenance phase records the truthful trail there rather than dropping a real hop; downstream projection/query/adapter key off the trail and alias_position, never off model_alias, so this only makes history more complete. No action needed unless a later phase asserts that invariant literally.

[2026-08-16T17:11:17Z · sase-n8.1] PROPOSED FOLLOW-UP: Preserve the hand-typed known-alias edge in downstream phases — %model:large can traverse @large while directives.model_alias remains None because the @ prefix was omitted. The provenance phase records the truthful trail anyway; core/adapter/query work should key off model_alias_trail and alias_position rather than asserting model_alias_trail[0] == model_alias literally.

[2026-08-16T17:12:56Z · sase-n8.1] Implemented alias-trail provenance for launch-side metadata. Resolution now returns alias_trail, default launch selection threads it through, LaunchSelection carries trail/origin, agent_meta and prompt-step marker writers persist both fields, re-exec preserves them without recomputing, and accepted-plan follow-up metadata writes/pops alias/trail/origin consistently. Added resolver/origin tests and extended metadata/follow-up/pooled-alias/fakey coverage. Verification: focused provenance suite passed (52 tests); targeted rerun of three full-suite failures passed; just install, just fmt, and just _lint-symvision passed; inline just check-full passed lint/validation and full non-visual pytest (31132 passed, 11 skipped) but failed only the known unrelated test-cost budget gate, corroborated on task sase-j0 with ref file:explicit:1ad8388625f2a55b59f0d503.

[2026-08-16T17:15:27Z · sase-n8.1] Implemented alias trail provenance across resolver, launch selection, metadata persistence, workflow markers, and accepted-plan follow-ups. Verified focused provenance tests passed, targeted regressions passed, and check-full passed lint/validation plus 31132 non-visual tests; only the known unrelated test-cost budget gate failed and was corroborated on sase-j0.

## Dependencies

- **Blocks:** [sase-n8.9](sase-n8.9.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n8.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n8.1.md) | [sase-n8.1](sase-n8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`96b48d0`](https://github.com/sase-org/sase/commit/96b48d0abbe9acec0f8037a08c388fc7c291edf8) | feat: record alias launch provenance | [sase-n8.1](sase-n8.1.md) | 2026-08-16 13:22:10 EDT |
