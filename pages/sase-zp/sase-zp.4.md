# Bead: sase-zp.4 — Document and verify the complete capacity workflow

[Bead Pages](../README.md) / [sase-zp](README.md) / sase-zp.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0jl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0jl.md) · **Assignee:** `sase-zp.4` · **Size:** small
**Created:** 2026-09-11 13:40:30 EDT · **Closed:** 2026-09-11 19:27:41 EDT
**Plan:** [202609/bead\_work\_capacity.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_work_capacity.md)

## Description

capacity_docs_integration: synchronize CLI and directive documentation, reference memory and skill source, and verify the complete gate-to-admission path.

## Notes

[2026-09-11T23:27:41Z · sase-zp.4] Documented and verified the gate-to-admission capacity path. Updated docs/beads.md (-c/--capacity, -C/--cl-name, multi-target examples, epic Custom Approval Capacity control), docs/xprompt.md (capacity grammar, completion, examples, pre-admission vs global budget, runners= migration), plus audited active docs (ace, axe, cli, configuration, editor, troubleshooting/runner-slots). Rewrote sase/memory/xprompts.md in place and ran sase memory init. Updated src/sase/xprompts/skills/sase_agents_status.md source only (previewed sase skill init --diff; did not deploy from this dirty checkout). Added tests/test_capacity_gate_to_admission.py: epic gate capacity=1 through launch argv, bead-work rendering, xprompt expansion, Rust extraction, and weighted admission — phase and land capacity match, land weight remains 2.0, four 0.25 claims satisfy capacity 1, one weight-2 claim does not; omitted-capacity regression keeps no %queue(capacity=) line, land weight 2.0, and the global budget. Focused pytest 71 passed (new path + plan_gate_capacity + TestCapacityDirective + land-weight + wait directives). git diff --check clean. just fmt clean. just check: fmt/ruff/mypy/feature-flags passed; stopped on pre-existing symvision private imports tracked by ready task sase-zk. sase bead epic-symbols sase-zp.4: no leftovers.

## Dependencies

- **Depends on:** [sase-zp.3](sase-zp.3.md) ✓ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zp.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zp.4/README.md) | [sase-zp.4](sase-zp.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`14ddd4d`](https://github.com/sase-org/sase/commit/14ddd4d82787a79afaa70523bbdaab4d13f2f0d8) | docs(queue): document weighted capacity and verify gate-to-admission path | [sase-zp.4](sase-zp.4.md) | 2026-09-11 19:29:03 EDT |
