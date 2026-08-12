# Bead: sase-k3.2 — Two module-level import defects

[Bead Pages](../README.md) / [sase-k3](README.md) / sase-k3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yo/README.md) · **Assignee:** `sase-k3.2` · **Size:** xsmall
**Created:** 2026-08-12 11:36:57 EDT · **Closed:** 2026-08-12 12:14:22 EDT
**Plan:** [202608/ace\_startup\_critical\_path.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_startup_critical_path.md)

## Description

imports: move the `sase.axe.state` import in toast_log out of module scope, drop the module-level `unittest.mock` import from the Patch loader in favor of a sys.modules-guarded check, and add a subprocess import-graph guard test.

## Notes

[2026-08-12T16:14:22Z · sase-k3.2] Verified the two import-defect fixes already present in the workspace: toast_log.py moved the sase.axe.state import into read_recent_toasts() (out of module scope); patch/_loading.py replaced isinstance(x, Mock) with a sys.modules-guarded _is_mock() helper, dropping the module-level unittest.mock import. Added tests/ace/tui/test_lazy_imports.py::test_toast_log_import_stays_off_axe and test_patch_loading_import_stays_off_unittest_mock as subprocess import-graph guards confirming sase.axe and unittest.mock never load via these import paths. just install and just check both passed clean (all lint gates + scoped test suite, which escalated to the full suite per core-identity-changed and still passed).

## Dependencies

- **Blocks:** [sase-k3.6](sase-k3.6.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k3.2/README.md) | [sase-k3.2](sase-k3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e4391c3`](https://github.com/sase-org/sase/commit/e4391c373df946f87fe6f48b37338a0d3f7f25c7) | fix(ace,logs): move axe.state import into function scope, guard Mock isinstance checks via sys.modules | [sase-k3.2](sase-k3.2.md) | 2026-08-12 12:15:12 EDT |
