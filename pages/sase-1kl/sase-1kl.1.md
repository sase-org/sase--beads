# Bead: sase-1kl.1 — Fix the test-lane failures blocking Full CI and Master Gate

[Bead Pages](../README.md) / [sase-1kl](README.md) / sase-1kl.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.106](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.106.md) · **Assignee:** `sase-1kl.1` · **Size:** medium
**Created:** 2026-10-13 14:15:35 EDT · **Closed:** 2026-10-13 16:13:08 EDT
**Plan:** [202610/v0\_18\_0\_release\_unblock.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_release_unblock.md)

## Description

test-flakes: fix the New Project source/create debounce races and the sudo canary length false positive that redden today's Full CI test lanes, re-inventory newer red runs, and root-cause the recent Master Gate tip flakes where the cause is a test wait or fixture.

## Notes

[2026-10-13T20:01:45Z · sase-1kl.1] PROPOSED FOLLOW-UP: `just check` full-suite escalation fails tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget at 3519 modules vs 3513; isolated on clean base 432dd1f759 it fails identically at the same assertion and count. Existing task sase-1ic tracks the TUI import-deferral overage.

[2026-10-13T20:13:08Z · sase-1kl.1] Fixed the New Project filter/debouncer race with a stale-callback guard and deterministic semantic waits; stabilized create-flow probe ordering; made sudo canary matching strict for values/hashes and standalone length tokens, comparing only changed process-environment entries. 
┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix                      │
└───────────────────────────────────────────────────────┘

---------- Formatting Python with ruff... ----------
12238 files left unchanged

---------- Fixing Python with ruff... ----------
All checks passed!

---------- Rendering generated docs... ----------

---------- Formatting Markdown with prettier... ----------
AGENTS.md 110ms (unchanged)
CLAUDE.md 67ms (unchanged)
CONTRIBUTING.md 9ms (unchanged)
demos/README.md 40ms (unchanged)
demos/tapes/AGENTS.md 2ms (unchanged)
demos/tapes/CLAUDE.md 2ms (unchanged)
demos/tapes/GEMINI.md 1ms (unchanged)
demos/tapes/OPENCODE.md 2ms (unchanged)
demos/tapes/QWEN.md 2ms (unchanged)
docs/ace.md 2570ms (unchanged)
docs/acknowledgements.md 20ms (unchanged)
docs/agent_auto_restart.md 46ms (unchanged)
docs/agent_images.md 170ms (unchanged)
docs/agent_providers.md 104ms (unchanged)
docs/agent_sessions.md 175ms (unchanged)
docs/agents_sidecar.md 93ms (unchanged)
docs/architecture.md 57ms (unchanged)
docs/artifact_links.md 46ms (unchanged)
docs/artifact_references.md 61ms (unchanged)
docs/artifacts_pane_contract.md 51ms (unchanged)
docs/artifacts_pane_visual_grammar.md 70ms (unchanged)
docs/axe.md 431ms (unchanged)
docs/beads.md 494ms (unchanged)
docs/blog/index.md 4ms (unchanged)
docs/blog/posts/axe-background-daemon.md 30ms (unchanged)
docs/blog/posts/beads-and-sdd.md 28ms (unchanged)
docs/blog/posts/changespecs-in-practice.md 28ms (unchanged)
docs/blog/posts/commit-workflows-plugins.md 28ms (unchanged)
docs/blog/posts/hello-sase-your-first-15-minutes.md 31ms (unchanged)
docs/blog/posts/macros-in-depth.md 24ms (unchanged)
docs/blog/posts/prompt-widget-and-nvim.md 30ms (unchanged)
docs/blog/posts/structured-agentic-software-engineering.md 61ms (unchanged)
docs/blog/posts/telegram-mobile-agents.md 28ms (unchanged)
docs/blog/posts/whats-next-memory-mobile-web.md 17ms (unchanged)
docs/blog/posts/why-coding-agents-need-orchestration.md 82ms (unchanged)
docs/change_spec.md 37ms (unchanged)
docs/cli.md 250ms (unchanged)
docs/commit_workflows.md 130ms (unchanged)
docs/completion.md 46ms (unchanged)
docs/configuration.md 1940ms (unchanged)
docs/content_layout.md 22ms (unchanged)
docs/development.md 190ms (unchanged)
docs/editor.md 72ms (unchanged)
docs/fakey.md 19ms (unchanged)
docs/getting_started.md 79ms (unchanged)
docs/goals.md 9ms (unchanged)
docs/images/blog/one_prompt_provider_clis.prompt.md 6ms (unchanged)
docs/images/blog/prompt_burrito.prompt.md 5ms (unchanged)
docs/images/blog/window_farm_vs_control_tower.prompt.md 6ms (unchanged)
docs/images/commit-workflow-infographic.critique.md 22ms (unchanged)
docs/images/commit-workflow-infographic.prompt.md 10ms (unchanged)
docs/images/infographic-style-brief.md 16ms (unchanged)
docs/images/macro-resolution-infographic.critique.md 7ms (unchanged)
docs/images/macro-resolution-infographic.prompt.md 11ms (unchanged)
docs/images/rust-backend-boundary-infographic.critique.md 33ms (unchanged)
docs/images/rust-backend-boundary-infographic.prompt.md 5ms (unchanged)
docs/images/sase_overview.critique.md 6ms (unchanged)
docs/images/sase_overview.prompt.md 6ms (unchanged)
docs/images/sase_tui_tabs_infographic.critique.md 32ms (unchanged)
docs/images/sase_tui_tabs_infographic.prompt.md 5ms (unchanged)
docs/images/sase-rust-core-integration.critique.md 33ms (unchanged)
docs/images/sase-rust-core-integration.prompt.md 4ms (unchanged)
docs/images/sase-telegram-integration.critique.md 26ms (unchanged)
docs/images/sase-telegram-integration.prompt.md 10ms (unchanged)
docs/images/workflow-execution-infographic.critique.md 45ms (unchanged)
docs/images/workflow-execution-infographic.prompt.md 11ms (unchanged)
docs/images/zorg-zettel-vision-infographic.critique.md 40ms (unchanged)
docs/index.md 5ms (unchanged)
docs/init.md 108ms (unchanged)
docs/instruction_bundles.md 23ms (unchanged)
docs/instruction_inventory.md 8ms (unchanged)
docs/integrations.md 46ms (unchanged)
docs/llms.md 526ms (unchanged)
docs/macros.md 509ms (unchanged)
docs/memory_history.md 36ms (unchanged)
docs/memory.md 49ms (unchanged)
docs/mentors.md 27ms (unchanged)
docs/mobile_gateway.md 52ms (unchanged)
docs/mobile_mvp_runbook.md 34ms (unchanged)
docs/monitors.md 119ms (unchanged)
docs/notifications.md 304ms (unchanged)
docs/pager.md 46ms (unchanged)
docs/perf_runbook.md 185ms (unchanged)
docs/plugins.md 166ms (unchanged)
docs/project_spec.md 69ms (unchanged)
docs/prompt.md 56ms (unchanged)
docs/query_language.md 43ms (unchanged)
docs/remote_dispatch.md 58ms (unchanged)
docs/rust_backend.md 204ms (unchanged)
docs/sdd_storage.md 54ms (unchanged)
docs/sdd.md 123ms (unchanged)
docs/sudo.md 38ms (unchanged)
docs/telemetry.md 34ms (unchanged)
docs/tool.md 84ms (unchanged)
docs/troubleshooting/agent-revival.md 8ms (unchanged)
docs/troubleshooting/runner-slots.md 25ms (unchanged)
docs/vcs.md 88ms (unchanged)
docs/workflow_spec.md 100ms (unchanged)
docs/workspace.md 87ms (unchanged)
GEMINI.md 40ms (unchanged)
INSTALL.md 28ms (unchanged)
OPENCODE.md 47ms (unchanged)
QWEN.md 42ms (unchanged)
README.md 24ms (unchanged)
sase/memory/cli_rules.md 5ms (unchanged)
sase/memory/decisions.md 23ms (unchanged)
sase/memory/decisions/adapters-normalize-harnesses.md 5ms (unchanged)
sase/memory/decisions/agents-sync-publish-only.md 8ms (unchanged)
sase/memory/decisions/check-full-is-explicit.md 6ms (unchanged)
sase/memory/decisions/ci-two-speed-split.md 6ms (unchanged)
sase/memory/decisions/corpus-before-mechanism.md 5ms (unchanged)
sase/memory/decisions/explicit-handoff-fails-closed.md 5ms (unchanged)
sase/memory/decisions/gates-never-block.md 6ms (unchanged)
sase/memory/decisions/global-install-is-human-only.md 5ms (unchanged)
sase/memory/decisions/goal-ledger.md 6ms (unchanged)
sase/memory/decisions/goals-host-binds.md 5ms (unchanged)
sase/memory/decisions/guarded-recipes.md 6ms (unchanged)
sase/memory/decisions/helpers-return-roots-declare.md 6ms (unchanged)
sase/memory/decisions/hold-pull-fail-open.md 7ms (unchanged)
sase/memory/decisions/host-owned-completion.md 6ms (unchanged)
sase/memory/decisions/machine-link-writes-off-primary.md 4ms (unchanged)
sase/memory/decisions/memory-links-are-authored.md 5ms (unchanged)
sase/memory/decisions/memory-webs.md 6ms (unchanged)
sase/memory/decisions/plugin-commands.md 5ms (unchanged)
sase/memory/decisions/project-labels-never-keys.md 4ms (unchanged)
sase/memory/decisions/receipts-prove-before-they-skip.md 4ms (unchanged)
sase/memory/decisions/record-before-admit.md 7ms (unchanged)
sase/memory/decisions/rust-core-required.md 4ms (unchanged)
sase/memory/decisions/single-turn-agents.md 5ms (unchanged)
sase/memory/decisions/size-alias-effort-ladder.md 6ms (unchanged)
sase/memory/decisions/triage-annotates-does-not-change-exit-codes.md 4ms (unchanged)
sase/memory/decisions/two-speed-verification.md 5ms (unchanged)
sase/memory/decisions/v1-import-retired.md 7ms (unchanged)
sase/memory/decisions/webs-render-in-their-own-section.md 6ms (unchanged)
sase/memory/dispatch.md 7ms (unchanged)
sase/memory/generated_skills.md 8ms (unchanged)
sase/memory/glossary.md 5ms (unchanged)
sase/memory/glossary/agent-clan.md 2ms (unchanged)
sase/memory/glossary/agent-data-card-block.md 2ms (unchanged)
sase/memory/glossary/agent-data-card.md 2ms (unchanged)
sase/memory/glossary/agent-data-deck.md 2ms (unchanged)
sase/memory/glossary/agent-hood.md 2ms (unchanged)
sase/memory/glossary/agent-instruction-file.md 2ms (unchanged)
sase/memory/glossary/agent-neighbor.md 2ms (unchanged)
sase/memory/glossary/agent-node.md 1ms (unchanged)
sase/memory/glossary/agent-relation-jump-target.md 4ms (unchanged)
sase/memory/glossary/agent-tab.md 2ms (unchanged)
sase/memory/glossary/agent-tribe.md 2ms (unchanged)
sase/memory/glossary/agent-turn.md 1ms (unchanged)
sase/memory/glossary/artifact-markdown-file.md 2ms (unchanged)
sase/memory/glossary/artifact-reference.md 2ms (unchanged)
sase/memory/glossary/artifact.md 2ms (unchanged)
sase/memory/glossary/chop.md 2ms (unchanged)
sase/memory/glossary/core-memory.md 1ms (unchanged)
sase/memory/glossary/current-project.md 2ms (unchanged)
sase/memory/glossary/deck-panel.md 3ms (unchanged)
sase/memory/glossary/failure-signature.md 1ms (unchanged)
sase/memory/glossary/feature-flag.md 1ms (unchanged)
sase/memory/glossary/flag-bead.md 2ms (unchanged)
sase/memory/glossary/gate-turn.md 3ms (unchanged)
sase/memory/glossary/goal.md 3ms (unchanged)
sase/memory/glossary/llm-calls.md 2ms (unchanged)
sase/memory/glossary/lumberjack.md 2ms (unchanged)
sase/memory/glossary/machine-tab.md 2ms (unchanged)
sase/memory/glossary/macro-invocation.md 2ms (unchanged)
sase/memory/glossary/macro-memory.md 1ms (unchanged)
sase/memory/glossary/macro-part.md 1ms (unchanged)
sase/memory/glossary/macro-swarm.md 1ms (unchanged)
sase/memory/glossary/macro-workflow.md 2ms (unchanged)
sase/memory/glossary/macro.md 2ms (unchanged)
sase/memory/glossary/memory-strand.md 1ms (unchanged)
sase/memory/glossary/memory-web.md 2ms (unchanged)
sase/memory/glossary/named-proc.md 2ms (unchanged)
sase/memory/glossary/nav-item.md 3ms (unchanged)
sase/memory/glossary/nav-section.md 3ms (unchanged)
sase/memory/glossary/node-panel.md 2ms (unchanged)
sase/memory/glossary/oneshot-service-proc.md 2ms (unchanged)
sase/memory/glossary/patch.md 2ms

… and 6267 more characters

## Dependencies

- **Blocks:** [sase-1kl.4](sase-1kl.4.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kl.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kl.1/README.md) | [sase-1kl.1](sase-1kl.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8959b0e`](https://github.com/sase-org/sase/commit/8959b0e6fc6b048ee60f79731e676db994cb2ce7) | fix(tests): stabilize New Project flows and sudo checks | [sase-1kl.1](sase-1kl.1.md) | 2026-10-13 16:15:33 EDT |
