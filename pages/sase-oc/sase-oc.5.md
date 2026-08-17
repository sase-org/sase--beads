# Bead: sase-oc.5 — Value-kind provider catalog

[Bead Pages](../README.md) / [sase-oc](README.md) / sase-oc.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04p](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04p.md) · **Assignee:** `sase-oc.5` · **Size:** medium
**Created:** 2026-08-17 08:54:25 EDT · **Closed:** 2026-08-17 12:49:14 EDT
**Plan:** [202608/cli\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/cli_completion.md)

## Description

kinds: fill out the remaining value-kind providers behind the existing seam, routing each through sase_core_rs or an equally cheap catalog and rendering project display names rather than ProjectSpec keys.

## Notes

[2026-08-17T16:48:43Z · sase-oc.5] Shipped remaining value-kind providers behind the existing candidates seam: repo, workspace, flag, plugin, plan, patch, memory, xprompt, skill, proc, monitor, artifact, tag, plus agent (cached rust artifact index) and model (five builtin size aliases). Each kind is reachable from NAME_TABLE or PATH_OVERRIDES; spec snapshot regenerated (76 slots gained live kinds). Providers stay off sase.ace / sase.main.parser / rich / textual by using rust bindings and in-process registries instead of sase.sdd, sase.bead, sase.workspace_provider, sase.xprompt.model_completion, or sase agent list. Isolated-subprocess latency for every shipped kind stayed under the existing 150ms contract budget (best-of-2 typically 120-230ms including interpreter start). path/dir remain shell-native with no provider. just check is red only on the pre-existing live flag bead sase-om (completion_refresh_on_update) with no registry definition, already tracked on sase-oc; fmt/ruff/mypy/symvision/toobig/validate/test-scoped (1415 passed) were green.

[2026-08-17T16:48:59Z · sase-oc.5] PROPOSED FOLLOW-UP: linked/sidecar/external repo completion — sase.repo_inventory cannot be imported on the candidates fast path because its module-level sase.sdd.store import loads sase.sdd.__init__ and then sase.ace/rich; make that import lazy (or add a rust inventory binding) so repo completion can offer more than primary project display names and checkout basenames.

[2026-08-17T16:49:14Z · sase-oc.5] Verified remaining value-kind providers (repo, workspace, flag, plugin, plan, patch, memory, xprompt, skill, proc, monitor, artifact, tag, agent, model) behind the candidates seam: each is reachable from kinds.py, uses sase_core_rs or an in-process catalog, renders project display names, stays off sase.ace/parser/rich/textual, and holds the import-set plus 150ms isolated-subprocess budget. Regenerated cli_spec.json (76 slots gained live kinds). path/dir still shell-native. No leftover --epic-symbol entries for sase-oc.5.

[2026-08-17T16:50:47Z · sase-oc.5] Verified remaining value-kind providers (repo, workspace, flag, plugin, plan, patch, memory, xprompt, skill, proc, monitor, artifact, tag, agent, model) behind the candidates seam: each is reachable from kinds.py, uses sase_core_rs or an in-process catalog, renders project display names, stays off sase.ace/parser/rich/textual, and holds the import-set plus 150ms isolated-subprocess budget. Regenerated cli_spec.json (76 slots gained live kinds). path/dir still shell-native. No leftover --epic-symbol entries for sase-oc.5.

## Dependencies

- **Depends on:** [sase-oc.4](sase-oc.4.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-oc.6](sase-oc.6.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-oc.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-oc.5/README.md) | [sase-oc.5](sase-oc.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`aca2b7a`](https://github.com/sase-org/sase/commit/aca2b7ac6a4a577bdca921c9add5ea5214a15112) | feat(completion): add remaining value-kind providers | [sase-oc.5](sase-oc.5.md) | 2026-08-17 12:51:24 EDT |
