# Bead: sase-n8.1 — Record the alias resolution trail and its origin at launch

[Bead Pages](../README.md) / [sase-n8](README.md) / sase-n8.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03t](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03t.md) · **Assignee:** `sase-n8.1` · **Size:** large
**Created:** 2026-08-16 11:30:45 EDT
**Plan:** [202608/launch\_control\_alias\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/launch_control_alias_history.md)

## Description

provenance: make alias resolution return the ordered trail of alias hops it traversed, give LaunchSelection that trail plus the origin of the request (directive vs no-directive default vs no alias), and persist `model_alias_trail` and `model_alias_origin` into agent_meta.json and prompt-step markers at every launch, reconcile, re-exec, and follow-up write site.

## Notes

[2026-08-16T15:52:12Z · sase-n8.1] Contract note for phases core/adapter: the epic pins "model_alias_trail[0] == model_alias". That holds for every alias reference SASE generates (format_model_directive_value always emits @<name>, and _directive_extract only sets directives.model_alias when the @ prefix was present). It does NOT hold for a hand-typed "%model:large" — a known alias written without @ — where directives.model_alias is None but resolution really did traverse @large. The provenance phase records the truthful trail there rather than dropping a real hop; downstream projection/query/adapter key off the trail and alias_position, never off model_alias, so this only makes history more complete. No action needed unless a later phase asserts that invariant literally.

## Dependencies

- **Blocks:** [sase-n8.9](sase-n8.9.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n8.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n8.1.md) | [sase-n8.1](sase-n8.1.md) | 0 |
