# Bead: sase-p3.15.1 — Make \`\_setup-required-plugins\` install what the project declares, verified

[Bead Pages](../README.md) / [sase-p3.15](sase-p3.15.md) / sase-p3.15.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-p3.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p3.land.md) · **Assignee:** `sase-p3.15.1` · **Size:** medium
**Created:** 2026-08-18 04:37:37 EDT · **Closed:** 2026-08-18 05:42:35 EDT
**Plan:** [202608/required\_plugin\_install\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202608/required_plugin_install_repair.md)

## Description

install-repair: rewrite `_setup-required-plugins` to honor each `plugins.required` PEP 508 spec, resolve an unpublished sase-org plugin from its public git repo, verify the distribution imports after install, and fail with an actionable message instead of a raw uv resolution error.

## Notes

[2026-08-18T09:42:35Z · sase-p3.15.1] Rewrote _setup-required-plugins as tools/setup_required_plugins: drives the install loop from plugins.required (honors PEP 508 specifiers so a stale sase-github 0.2.4 upgrades to the declared >=0.2.5), resolves linked-checkout -> PyPI -> sase-org git fallback in order, verifies each plugin actually imports post-install, and fails with an actionable message instead of a raw uv error. Pinned sase-github>=0.2.5 in sase/sase.yml and regenerated sase/task_types.json (adds github, agent_creatable: false, generated notes unaffected as predicted). Verified: doctor plugins.required and sase validate clean with no 'Skipping invalid file hook' noise; version-mismatch repair confirmed (0.2.4->0.2.5 in one pass, no no-op); moved-aside and dangling-.pth linked-checkout scenarios both simulated and repaired; just check green with the linked sase-github checkout both present and moved aside. Added tests/test_setup_required_plugins_tool.py (pytest.mark.contract, tools/ script not in the import graph) and re-curated tests/contract_manifest.txt budget 43->44 with measured 27.8s serial cost, still inside the 30s budget. Full just check (34 tests in test_plugins_required.py + test_setup_required_plugins_tool.py, plus whole-suite escalation, 33059 tests) is green, exit 0.

## Dependencies

- **Blocks:** [sase-p3.15.3](sase-p3.15.3.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.15.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.15.1/README.md) | [sase-p3.15.1](sase-p3.15.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eed1d9a`](https://github.com/sase-org/sase/commit/eed1d9a67d269295a69ef893cd895f4739b93d9e) | fix(plugins): install what plugins.required actually declares | [sase-p3.15.1](sase-p3.15.1.md) | 2026-08-18 05:43:49 EDT |
