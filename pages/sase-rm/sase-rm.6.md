# Bead: sase-rm.6 — Repair documentation, build guards, deleted imports, and plugin-isolated tests

[Bead Pages](../README.md) / [sase-rm](README.md) / sase-rm.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08u.md) · **Assignee:** `sase-rm.6` · **Size:** medium
**Created:** 2026-08-20 14:47:53 EDT · **Closed:** 2026-08-21 05:25:43 EDT
**Plan:** [202608/task\_backlog\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_closeout.md)

## Description

guardrail_cleanup: close the confirmed documentation gaps and make build, scoped collection, and doctor tests independent of stale recipe lines, deleted modules, and ambient plugins.

## Notes

[2026-08-20T19:11:18Z · sase-rm.6] CLOSE-READY sase-m3: docs/getting_started.md no longer calls muse/grok "explicit-only". Step 3 now states they are never auto-detected (PATH autodetection) and separately that Grok is also reached through shipped @xsmall/@small/@medium pools and as the last @xlarge candidate. docs/xprompt.md %model comments got the same split while editing that file for sase-pf. Verified by tests/test_docs_getting_started_providers.py (whitespace-collapsed "never auto-detected", "alias-pool routing", pool names, and no "explicit-only").

[2026-08-20T19:11:40Z · sase-rm.6] CLOSE-READY sase-pf: docs/xprompt.md bundled-skills table now includes sase_monitor and sase_new_task in alphabetical order. Purposes match the skill-source first sentences (monitor: run a long command without blocking your turn; new_task: use before creating/filing/proposing a task bead). Drift pin: tests/main/test_init_skills_sources.py::test_docs_xprompt_bundled_skills_table_matches_packaged_sources asserts the table names equal src/sase/xprompts/skills/*.md (excluding SKILL.frame.template.md).

[2026-08-20T19:11:58Z · sase-rm.6] CLOSE-READY sase-rb: Justfile _refresh-sase-core-checkout is now one shell, so SASE_ALLOW_STALE_CORE=1 exit 0 actually skips tools/refresh_linked_checkout. rust-install and rust-dev-install skip the refresh helper in the same shell when the flag is set; they still run maturin so a bisect can build from the stale checkout. Recipe-level proof: test_refresh_sase_core_checkout_skips_fetch_when_stale_core_is_allowed (spy venv python is not invoked), the complementary fetch-when-unset test, one-shell structural tests for all three recipes, and dry-run tests that maturin remains on rust-install/rust-dev-install.

[2026-08-20T19:12:16Z · sase-rm.6] CLOSE-READY sase-qb: every tests/ import of deleted sase.ace.tui.proc_queue now uses sase.ace.tui.proc_observer.ObservedProc (aliased as ProcInfo). The only remaining ProcQueue is the test helper tests/ace/tui/_compat_proc_queue.py used by test_agent_cleanup_procs.py. tests/ace/tui/conftest.py no longer installs a sys.modules shim. Verified: ModuleNotFoundError for sase.ace.tui.proc_queue; AST scan finds no test Import/ImportFrom of it; tests/_agent_cleanup_proc_helpers.py and tests/_plan_approval_tui_helpers.py import without tests/ace/tui/conftest.py; pytest --collect-only tests/test_agent_dismiss_persistence.py -p no:randomly exits 0.

[2026-08-20T19:12:33Z · sase-rm.6] CLOSE-READY sase-ql: tests/doctor/test_checks_config_repos.py owns a deterministic empty ArtifactProviderRegistry via autouse monkeypatch of sase.artifact_providers.get_artifact_provider_registry plus cache reset. The two OK tests run with SASE_DISABLE_PLUGINS unset and set to 1. A dedicated test proves a declared disabled_env still surfaces WARN. Sibling audit: test_only_config_repos_doctor_check_reads_artifact_provider_registry asserts src/sase/doctor/*.py mentions get_artifact_provider_registry only in checks_config_repos.py (external_mirror and other direct-check tests do not read live entry points). File passed 19/19 with and without SASE_DISABLE_PLUGINS=1.

[2026-08-20T19:12:50Z · sase-rm.6] PROPOSED FOLLOW-UP: remaining overloaded "explicit-only" Muse/Grok wording — sase-m3 said muse_documentation_wording already fixed README.md, INSTALL.md, docs/llms.md, docs/agent_providers.md, docs/xprompt.md, and the hello-sase / structured-agentic-software-engineering blog posts, but those files still use the label (except getting_started.md and the xprompt %model comments fixed here). Same split: never auto-detected vs alias-pool routing; do not change autodetection or model-alias defaults.

[2026-08-20T19:13:08Z · sase-rm.6] PROPOSED FOLLOW-UP: rust-install/rust-dev-install missing-dir and missing-python `exit 0` guards are still split across @-prefixed just lines, so a successful skip does not stop later recipe commands (same just-subshell mechanism as sase-rb, different guards).

[2026-08-20T19:22:37Z · sase-rm.6--1] Re-keyed stale Justfile --epic-symbol SnippetsPane/SnippetsPaneHost/SnippetsPaneSessionState from closed sase-ri.4 to still-open later phase sase-ri.5. just check-full failed at lint (symvision) because sase-ri.4 closed while those unused-until-cutover public symbols still had no non-test consumer; sase-rm.6 itself has no leftovers. just _lint-symvision now passes.

[2026-08-20T19:36:57Z · sase-rm.6--2] PROPOSED FOLLOW-UP: home memory README clobber across workspaces — just check-full failed at init memory --check because ~/.local/share/chezmoi/home/sase/memory/README.md lost the generated sase_artifacts.md sentence (template change from master a1da80ddb). Chezmoi HEAD 7cb3300d already had the new text; working tree had been reverted, likely by an older-checkout sase memory init. Regenerated via sase memory init --no-commit from this workspace; check now passes. Durable fix: pin generated home README to the running tree or stop older inits from rewriting it.

[2026-08-20T20:22:31Z · sase-rm.6--3] just check-full (monitor 06fhrd6fmev0) failed solely on known flake sase-qp: tests/test_suite_gate_reclaim.py::test_fresh_heartbeat_is_not_reclaimed DID NOT RAISE UsageError under the full parallel lane (35337 passed, 13 skipped). Serial 3/3 passed; this phase does not touch suite-gate reclaim. Corroborated with sase bead +1 sase-qp. sase-qp is assigned to later phase sase-rm.11 (heartbeat clocks). Re-running just check-full; will not close until that lane is green.

[2026-08-21T09:20:22Z · sase-rm.6] PROPOSED FOLLOW-UP: just check blocked by closed flag bead sase-rk — tools/check_feature_flags reports admin_center_config_hub still has a surviving definition after sase-rk closed; this is outside guardrail_cleanup but currently makes the shared feature-flag gate red.

[2026-08-21T09:21:30Z · sase-rm.6] PROPOSED FOLLOW-UP: shared lint gates still red outside guardrail_cleanup — just _lint-symvision reports removable SnippetsPaneSessionState/SnippetsPaneHost/SnippetsPane pragmas in snippets_panel.py, and just _lint-toobig reports src/sase/finalizers/declaration.py at 1038 lines.

[2026-08-21T09:25:10Z · sase-rm.6] PROPOSED FOLLOW-UP: selection-health has a new reproducible-flake record outside guardrail_cleanup — just selection-health --fail-on-new-flake reports tests/ace/tui/widgets/test_directive_completion_candidates.py::test_id_parenthesized_completion_advertises_identity_keywords exceeds tests/reproducible_flake_baseline.txt and needs a filed/fixed node before landing.

[2026-08-21T09:25:43Z · sase-rm.6] Verified guardrail_cleanup implementation: docs/getting_started.md separates Muse/Grok PATH autodetect from Grok alias-pool routing, docs/xprompt.md has source-matched bundled skill rows for sase_final, sase_monitor, and sase_new_task plus split Muse/Grok model comments, and docs drift tests passed. Justfile stale-core refresh is one-shell and rust-install/rust-dev-install skip refresh when SASE_ALLOW_STALE_CORE=1; focused Justfile tests passed. Deleted proc_queue imports in tests now use ObservedProc or tests/ace/tui/_compat_proc_queue.py; deleted-module AST/import guard, direct helper imports, collect-only for tests/test_agent_dismiss_persistence.py, and tests/ace/tui/test_agent_cleanup_procs.py passed. Doctor config repo tests use an isolated empty artifact-provider registry and pass 19/19 with SASE_DISABLE_PLUGINS unset and set. just fmt passed; git diff --check passed; sase bead epic-symbols sase-rm.6 reported no entries. just check was attempted after install and passed fmt/keep-sorted/ruff/mypy, then stopped at unrelated closed flag bead sase-rk admin_center_config_hub; additional unrelated blockers and selection-health flake were recorded as PROPOSED FOLLOW-UP notes.

[2026-08-21T09:27:04Z · sase-rm.6] Verified epic-symbols clear; prior focused docs, Justfile, proc import, doctor isolation tests, git diff --check, and install/format completed; just check reached unrelated shared-tree blockers recorded as PROPOSED FOLLOW-UP notes.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rm.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rm.6/README.md) | [sase-rm.6](sase-rm.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b76f53b`](https://github.com/sase-org/sase/commit/b76f53b998e3f208d339253a9ca7538469cb987a) | fix: repair guardrails for provider docs and proc imports | [sase-rm.6](sase-rm.6.md) | 2026-08-21 05:28:24 EDT |
