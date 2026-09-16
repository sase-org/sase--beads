# Bead: sase-11e.8.6.5.1 — Route every job tribe operation through contextual identity resolution

[Bead Pages](../README.md) / [sase-11e.8.6.5](sase-11e.8.6.5.md) / sase-11e.8.6.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11e.8.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11e.8.6.land.md) · **Assignee:** `sase-11e.8.6.5.1` · **Size:** medium
**Created:** 2026-09-16 09:55:18 EDT · **Closed:** 2026-09-16 11:57:59 EDT
**Plan:** [202609/routine\_job\_identity\_diagnostic\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/routine_job_identity_diagnostic_completion.md)

## Description

tribe_context: unify assignment, query, wait/fork, completion, and display resolution without changing stored identities.

## Notes

[2026-09-16T15:57:59Z · sase-11e.8.6.5.1] tribe_context: routed every job-tribe operation that mutates or targets identity
through the existing Rust contextual resolver (agent_tribe.rs's
resolve_agent_tribe_identity, already exposed via core/agent_tribe.py's
layers=/stored_tribes=/current_tribe= kwargs from a prior phase) instead of the
plain, context-free canonicalize_public_tribe_name/parse_tribe_reference calls
the landing audit found:

- Assignment: ace/agent_tribes.py's set_tribe/update_agent_tribe/
  update_agent_tribe_assignment now accept layers=; wired at the CLI
  (agents/cli_tribe.py, catches InvalidTribeError -> clean stderr + exit 2),
  the TUI persist-directive worker (_directive_persistence.py, off the
  render/event loop), and the %id(tribe=...) launch path
  (axe/run_agent_directives.py, wraps InvalidTribeError as RuntimeError). A
  same-layer/cross-layer ace.tribes.chop/job collision is now rejected with
  the resolver's source-aware diagnostic and the store is left unchanged
  (verified: rejected mutation does not touch tribes_by_identity or the
  written JSON file).
- Wait/fork: scripts/_agent_chat_from_name_tribe.py's resolve_tribe_fork_source
  now resolves the public @job spelling using the same all-projects index's
  stored tribes it already builds for tribe_candidate lookup, instead of the
  caller canonicalizing @job to chop before the index exists. A wait bound to
  an independent historical job identity is now followed by a fork that
  targets the same identity.
- Completion: ace/tui/_agent_completion_wait.py's _parse_tribe_target now
  passes stored_tribes derived from the already-loaded tribe_rows snapshot
  (zero extra I/O) so the live wait-binding display in the Agents tab
  resolves the same identity resolve_tribe_wait_binding binds against.
- Display: ace/tui/models/tribe_display.py's named_tribe_identity_colors now
  passes its own already-loaded tribe_names collection as stored_tribes
  context (zero extra I/O, safe on the render path) so an independently
  stored job identity keeps its own configured color instead of collapsing
  onto the built-in chop panel's color.
- Query filtering (agent_query/evaluator.py) was already context-aware from
  the prior phase; left unchanged and reverified.
- Syntactic-only tribe-reference recognition (chat/resume/fan-out reference
  checks, directive parsing, wait-target-shape validation) was left as cheap,
  context-free parse_tribe_reference calls per the plan's explicit allowance,
  since those sites only test "is this a tribe reference" and discard the
  resolved identity.

No Rust/PyO3 changes were needed: the resolver and its collision diagnostics
already existed and were already tested from the prior tribe_safety phase.
Added production-path Python tests: CLI and durable-store layer-collision
rejection with store-unchanged assertions, %id(tribe=job) launch-time
collision rejection, wait-then-fork identity consistency for an independent
stored job tribe, TUI completion tribe-binding resolution for an independent
stored job tribe, and TUI display color resolution for an independent stored
job tribe.

Verified: `just check` (fmt, ruff, mypy, feature-flags, pyscripts, test-waits,
changelog, patch/stitch terminology, symvision, toobig, SASE validation, and
the diff-scoped test lane covering 843/3917 files) exits 0 on SASE HEAD
b9c28f25e880df7436c03cc00a767c248560073a against sase-core linked checkout
f822ebd5839cca0b41627d3c0294203aafa4401d (auto-refreshed and rebuilt by
`just check` itself from the audit's 2d7fa287 baseline; sase-core-revision.txt
stays pinned at 51c7c38d, unchanged -- the published-floor gap is explicitly
the acceptance phase's concern per the plan, not touched here). Also ran the
full ~3700-test sweep of every test file mentioning "tribe" and the dedicated
agent-query suite (tokenizer/pushdown/canonicalization/parser/evaluator):
all green. No config collision, reserved-tribe, clan-aggregation, wait-order,
glyph/color/grouping/collapse, or .chop.-agent-name behavior changed.

sase bead epic-symbols sase-11e.8.6.5.1 has no --epic-symbol entries (checked
both before starting and immediately before this close). No PROPOSED
FOLLOW-UP: work found was already in-scope for this phase or already owned by
a named sibling phase/bead.

## Dependencies

- **Blocks:** [sase-11e.8.6.5.3](sase-11e.8.6.5.3.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11e.8.6.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11e.8.6.5.1/README.md) | [sase-11e.8.6.5.1](sase-11e.8.6.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9759e5a`](https://github.com/sase-org/sase/commit/9759e5afe8c0d58906981d04e3381b153334e20f) | fix(agent-tribes): route job-tribe assignment, wait/fork, completion, and display through contextual identity resolution | [sase-11e.8.6.5.1](sase-11e.8.6.5.1.md) | 2026-09-16 12:00:06 EDT |
