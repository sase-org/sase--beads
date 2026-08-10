# Bead: sase-il.7 — Finish core-owned tale size semantics and land sase-il

[Bead Pages](../README.md) / [sase-il](README.md) / sase-il.7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-il.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.land/README.md) · **Assignee:** `sase-il.7.land`
**Created:** 2026-08-10 10:54:06 EDT
**Plan:** [202608/finish\_tale\_size\_semantics.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_tale_size_semantics.md)

## Description

sase-core owns the full tale-size contract the sase-il design specified — tales accept only xsmall/small/medium, launch mode normalizes legacy tales instead of failing, and the size field descriptions point at sase/memory/sase_sizes.md instead of restating it — so the generated size note is genuinely the single source of size truth, and epic sase-il can then be closed out.

## Notes

[2026-08-10T16:25:48Z · wv.f4] DISCOVERED ISSUE: Independent reproduction while implementing the approved smarter_model_alias plan on 2026-08-10. [setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
✓ fmt (python)
✓ fmt (markdown)
✓ lint (keep-sorted)
✓ lint (ruff)
✓ lint (mypy)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (toobig)
✓ SASE validation
✗ committed plans
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.24.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.23.0,<0.24.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python -m sase.scripts.validate_committed_plans
202608/ace_app_boot_amortization.md:7: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/ace_patch_terminology.md:7: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/agents_reload_cost.md:7: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/clear_ace_tui_test_surface.md:7: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/complete_python_patch_storage.md:7: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/core_ref_contract.md:7: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/event_driven_tui_waits.md:9: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/gate_inputs_ace.md:9: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/gate_inputs_ace_1.md:10: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/gate_inputs_core.md:8: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/gate_inputs_remote.md:8: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/gate_inputs_telegram.md:9: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/patch_stitch_compatibility_audit.md:8: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/patch_tui_config_surface.md:7: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/patch_workflow_contracts.md:7: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/python_patch_storage.md:7: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/python_ref_registry.md:7: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/python_ref_registry_1.md:8: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/python_ref_registry_2.md:7: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/rust_prebuild_cache.md:8: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
202608/workflows_cli_terminology.md:8: error [tale-size-invalid] tale `size` must be `xsmall`, `small`, or `medium`, found `large`; a tale is work one follow-up agent implements directly, and `large` or `xlarge` work belongs in an epic plan
Committed plan validation failed: 3570 files (202 strict, 3368 legacy), 21 errors, 0 warnings.
error: recipe `validate-committed-plans` failed on line 735 with exit code 1 passed fmt, markdown fmt, keep-sorted, ruff, mypy, pyscripts, test-waits, changelog, patch/stitch terminology, symvision, toobig, and SASE validation, then failed the committed-plan validation gate with 21 tale-size-invalid errors. Representative errors: 202608/ace_app_boot_amortization.md:7, 202608/ace_patch_terminology.md:7, and 202608/python_ref_registry.md:7 each declare tier: tale with size: large, which the current validator rejects because tales must be xsmall/small/medium. This matches this epic's remaining tale-size contract/migration work and is unrelated to the model-alias changes.

[2026-08-10T16:59:23Z · wv.f4] DISCOVERED ISSUE: Independent reproduction during smarter_model_alias verification on 2026-08-10. In addition to the committed-plan tale-size gate, just test and a serial isolation rerun fail tests/test_axe_run_agent_exec_plan_followup_model_selection.py::TestPlanFollowupModelSelection::test_coder_followup_uses_tale_size_worker_alias for large and xlarge. Both cases now produce a prompt starting with %model:@medium_worker instead of %model:@large_worker or %model:@xlarge_worker, matching this epic tale-size normalization/contract migration surface and unrelated to model-alias graph changes.

[2026-08-10T17:12:55Z · toobig-2b.split_file.src.sase.workflows.commit.commit_hooks.0] DISCOVERED ISSUE: Independent reproduction during commit-hooks module-split verification on 2026-08-10. Full just check and a serial isolation rerun both fail tests/test_axe_run_agent_exec_plan_followup_model_selection.py::TestPlanFollowupModelSelection::test_coder_followup_uses_tale_size_worker_alias for large and xlarge: each emits %model:@medium_worker instead of @large_worker/@xlarge_worker. This matches the active tale-size normalization epic and the prior wv.f4 report; the commit-hook refactor does not touch plan follow-up model selection.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-il.7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.7.land/README.md) | [sase-il.7](sase-il.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7691738`](https://github.com/sase-org/sase/commit/769173869556de3c3677510703c0180ad019dee2) | docs: document the tale size contract and show its launch normalization | [sase-il.7](sase-il.7.md) | 2026-08-10 13:55:58 EDT |
