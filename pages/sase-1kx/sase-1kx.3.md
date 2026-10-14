# Bead: sase-1kx.3 — A tested release watcher that always reports and can close its bead

[Bead Pages](../README.md) / [sase-1kx](README.md) / sase-1kx.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10b](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10b.md) · **Assignee:** `sase-1kx.3` · **Size:** medium
**Created:** 2026-10-14 07:18:03 EDT · **Closed:** 2026-10-14 08:19:43 EDT
**Plan:** [202610/v0\_18\_0\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_release.md)

## Description

release-watch-tool: add tools/release_watch, a stdlib-only, unit-tested poller. It waits on PyPI, the release PR, Full CI, Master Gate, Publish, and sase-core-rs; dispatches Full CI or Publish only by fixed rules; fails fast on unparseable reads; and on every exit path writes a verdict and can close a bead.

## Notes

[2026-10-14T12:17:29Z · sase-1kx.3] PROPOSED FOLLOW-UP: sase-xo — this phase full check failed tests/agents_sync/test_commit_publication_bounded_drain.py::test_blocked_render_is_bounded_and_leaves_the_request_queued at 30.56s versus its <5s bound; the exact test passed on clean HEAD in 0.80s call time, so the recurrence is load-sensitive and remains with the existing open flake task.

[2026-10-14T12:19:43Z · sase-1kx.3] Implemented the stdlib-only release watcher, dispatch rules, release proof, verdict writing, signal handling, bead close retries, documentation, and 26 unit tests. 
┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix                      │
└───────────────────────────────────────────────────────┘

---------- Formatting Python with ruff... ----------
12285 files left unchanged

---------- Fixing Python with ruff... ----------
All checks passed!

---------- Rendering generated docs... ----------

---------- Formatting Markdown with prettier... ----------
AGENTS.md 119ms (unchanged)
CLAUDE.md 70ms (unchanged)
CONTRIBUTING.md 9ms (unchanged)
demos/README.md 43ms (unchanged)
demos/tapes/AGENTS.md 3ms (unchanged)
demos/tapes/CLAUDE.md 3ms (unchanged)
demos/tapes/GEMINI.md 2ms (unchanged)
demos/tapes/OPENCODE.md 3ms (unchanged)
demos/tapes/QWEN.md 2ms (unchanged)
docs/ace.md 2288ms (unchanged)
docs/acknowledgements.md 16ms (unchanged)
docs/agent_auto_restart.md 35ms (unchanged)
docs/agent_images.md 109ms (unchanged)
docs/agent_providers.md 71ms (unchanged)
docs/agent_sessions.md 110ms (unchanged)
docs/agents_sidecar.md 57ms (unchanged)
docs/architecture.md 47ms (unchanged)
docs/artifact_links.md 35ms (unchanged)
docs/artifact_references.md 44ms (unchanged)
docs/artifacts_pane_contract.md 35ms (unchanged)
docs/artifacts_pane_visual_grammar.md 46ms (unchanged)
docs/axe.md 311ms (unchanged)
docs/beads.md 536ms (unchanged)
docs/blog/index.md 4ms (unchanged)
docs/blog/posts/axe-background-daemon.md 23ms (unchanged)
docs/blog/posts/beads-and-sdd.md 36ms (unchanged)
docs/blog/posts/changespecs-in-practice.md 36ms (unchanged)
docs/blog/posts/commit-workflows-plugins.md 23ms (unchanged)
docs/blog/posts/hello-sase-your-first-15-minutes.md 32ms (unchanged)
docs/blog/posts/macros-in-depth.md 27ms (unchanged)
docs/blog/posts/prompt-widget-and-nvim.md 37ms (unchanged)
docs/blog/posts/structured-agentic-software-engineering.md 52ms (unchanged)
docs/blog/posts/telegram-mobile-agents.md 32ms (unchanged)
docs/blog/posts/whats-next-memory-mobile-web.md 16ms (unchanged)
docs/blog/posts/why-coding-agents-need-orchestration.md 81ms (unchanged)
docs/change_spec.md 36ms (unchanged)
docs/cli.md 232ms (unchanged)
docs/commit_workflows.md 126ms (unchanged)
docs/completion.md 42ms (unchanged)
docs/configuration.md 1779ms (unchanged)
docs/content_layout.md 14ms (unchanged)
docs/development.md 181ms (unchanged)
docs/editor.md 69ms (unchanged)
docs/fakey.md 18ms (unchanged)
docs/getting_started.md 66ms (unchanged)
docs/goals.md 12ms (unchanged)
docs/images/blog/one_prompt_provider_clis.prompt.md 8ms (unchanged)
docs/images/blog/prompt_burrito.prompt.md 6ms (unchanged)
docs/images/blog/window_farm_vs_control_tower.prompt.md 7ms (unchanged)
docs/images/commit-workflow-infographic.critique.md 25ms (unchanged)
docs/images/commit-workflow-infographic.prompt.md 14ms (unchanged)
docs/images/infographic-style-brief.md 18ms (unchanged)
docs/images/macro-resolution-infographic.critique.md 8ms (unchanged)
docs/images/macro-resolution-infographic.prompt.md 12ms (unchanged)
docs/images/rust-backend-boundary-infographic.critique.md 34ms (unchanged)
docs/images/rust-backend-boundary-infographic.prompt.md 5ms (unchanged)
docs/images/sase_overview.critique.md 8ms (unchanged)
docs/images/sase_overview.prompt.md 7ms (unchanged)
docs/images/sase_tui_tabs_infographic.critique.md 33ms (unchanged)
docs/images/sase_tui_tabs_infographic.prompt.md 6ms (unchanged)
docs/images/sase-rust-core-integration.critique.md 30ms (unchanged)
docs/images/sase-rust-core-integration.prompt.md 4ms (unchanged)
docs/images/sase-telegram-integration.critique.md 26ms (unchanged)
docs/images/sase-telegram-integration.prompt.md 11ms (unchanged)
docs/images/workflow-execution-infographic.critique.md 45ms (unchanged)
docs/images/workflow-execution-infographic.prompt.md 11ms (unchanged)
docs/images/zorg-zettel-vision-infographic.critique.md 37ms (unchanged)
docs/index.md 5ms (unchanged)
docs/init.md 102ms (unchanged)
docs/instruction_bundles.md 32ms (unchanged)
docs/instruction_inventory.md 8ms (unchanged)
docs/integrations.md 48ms (unchanged)
docs/llms.md 469ms (unchanged)
docs/macros.md 579ms (unchanged)
docs/memory_history.md 58ms (unchanged)
docs/memory.md 76ms (unchanged)
docs/mentors.md 46ms (unchanged)
docs/mobile_gateway.md 89ms (unchanged)
docs/mobile_mvp_runbook.md 58ms (unchanged)
docs/monitors.md 150ms (unchanged)
docs/notifications.md 335ms (unchanged)
docs/pager.md 65ms (unchanged)
docs/perf_runbook.md 224ms (unchanged)
docs/plugins.md 153ms (unchanged)
docs/project_spec.md 48ms (unchanged)
docs/prompt.md 48ms (unchanged)
docs/query_language.md 29ms (unchanged)
docs/remote_dispatch.md 42ms (unchanged)
docs/rust_backend.md 164ms (unchanged)
docs/sdd_storage.md 53ms (unchanged)
docs/sdd.md 128ms (unchanged)
docs/sudo.md 41ms (unchanged)
docs/telemetry.md 36ms (unchanged)
docs/tool.md 94ms (unchanged)
docs/troubleshooting/agent-revival.md 9ms (unchanged)
docs/troubleshooting/runner-slots.md 35ms (unchanged)
docs/vcs.md 101ms (unchanged)
docs/workflow_spec.md 114ms (unchanged)
docs/workspace.md 92ms (unchanged)
GEMINI.md 43ms (unchanged)
INSTALL.md 30ms (unchanged)
OPENCODE.md 44ms (unchanged)
QWEN.md 58ms (unchanged)
README.md 31ms (unchanged)
sase/memory/cli_rules.md 8ms (unchanged)
sase/memory/decisions.md 32ms (unchanged)
sase/memory/decisions/adapters-normalize-harnesses.md 6ms (unchanged)
sase/memory/decisions/agents-sync-publish-only.md 12ms (unchanged)
sase/memory/decisions/check-full-is-explicit.md 6ms (unchanged)
sase/memory/decisions/ci-two-speed-split.md 6ms (unchanged)
sase/memory/decisions/corpus-before-mechanism.md 5ms (unchanged)
sase/memory/decisions/explicit-handoff-fails-closed.md 5ms (unchanged)
sase/memory/decisions/gates-never-block.md 10ms (unchanged)
sase/memory/decisions/global-install-is-human-only.md 8ms (unchanged)
sase/memory/decisions/goal-ledger.md 7ms (unchanged)
sase/memory/decisions/goals-host-binds.md 5ms (unchanged)
sase/memory/decisions/guarded-recipes.md 7ms (unchanged)
sase/memory/decisions/helpers-return-roots-declare.md 7ms (unchanged)
sase/memory/decisions/hold-pull-fail-open.md 10ms (unchanged)
sase/memory/decisions/host-owned-completion.md 9ms (unchanged)
sase/memory/decisions/machine-link-writes-off-primary.md 6ms (unchanged)
sase/memory/decisions/memory-links-are-authored.md 6ms (unchanged)
sase/memory/decisions/memory-webs.md 7ms (unchanged)
sase/memory/decisions/plugin-commands.md 6ms (unchanged)
sase/memory/decisions/project-labels-never-keys.md 5ms (unchanged)
sase/memory/decisions/receipts-prove-before-they-skip.md 5ms (unchanged)
sase/memory/decisions/record-before-admit.md 8ms (unchanged)
sase/memory/decisions/rust-core-required.md 5ms (unchanged)
sase/memory/decisions/single-turn-agents.md 6ms (unchanged)
sase/memory/decisions/size-alias-effort-ladder.md 9ms (unchanged)
sase/memory/decisions/triage-annotates-does-not-change-exit-codes.md 7ms (unchanged)
sase/memory/decisions/two-speed-verification.md 7ms (unchanged)
sase/memory/decisions/v1-import-retired.md 10ms (unchanged)
sase/memory/decisions/webs-render-in-their-own-section.md 11ms (unchanged)
sase/memory/dispatch.md 12ms (unchanged)
sase/memory/generated_skills.md 13ms (unchanged)
sase/memory/glossary.md 8ms (unchanged)
sase/memory/glossary/agent-clan.md 3ms (unchanged)
sase/memory/glossary/agent-data-card-block.md 2ms (unchanged)
sase/memory/glossary/agent-data-card.md 3ms (unchanged)
sase/memory/glossary/agent-data-deck.md 4ms (unchanged)
sase/memory/glossary/agent-hood.md 2ms (unchanged)
sase/memory/glossary/agent-instruction-file.md 3ms (unchanged)
sase/memory/glossary/agent-neighbor.md 2ms (unchanged)
sase/memory/glossary/agent-node.md 2ms (unchanged)
sase/memory/glossary/agent-relation-jump-target.md 5ms (unchanged)
sase/memory/glossary/agent-tab.md 3ms (unchanged)
sase/memory/glossary/agent-tribe.md 2ms (unchanged)
sase/memory/glossary/agent-turn.md 2ms (unchanged)
sase/memory/glossary/artifact-markdown-file.md 3ms (unchanged)
sase/memory/glossary/artifact-reference.md 3ms (unchanged)
sase/memory/glossary/artifact.md 2ms (unchanged)
sase/memory/glossary/chop.md 3ms (unchanged)
sase/memory/glossary/core-memory.md 3ms (unchanged)
sase/memory/glossary/current-project.md 4ms (unchanged)
sase/memory/glossary/deck-panel.md 4ms (unchanged)
sase/memory/glossary/failure-signature.md 2ms (unchanged)
sase/memory/glossary/feature-flag.md 2ms (unchanged)
sase/memory/glossary/flag-bead.md 3ms (unchanged)
sase/memory/glossary/gate-turn.md 3ms (unchanged)
sase/memory/glossary/goal.md 3ms (unchanged)
sase/memory/glossary/llm-calls.md 2ms (unchanged)
sase/memory/glossary/lumberjack.md 2ms (unchanged)
sase/memory/glossary/machine-tab.md 2ms (unchanged)
sase/memory/glossary/macro-invocation.md 3ms (unchanged)
sase/memory/glossary/macro-memory.md 2ms (unchanged)
sase/memory/glossary/macro-part.md 1ms (unchanged)
sase/memory/glossary/macro-swarm.md 2ms (unchanged)
sase/memory/glossary/macro-workflow.md 2ms (unchanged)
sase/memory/glossary/macro.md 1ms (unchanged)
sase/memory/glossary/memory-strand.md 1ms (unchanged)
sase/memory/glossary/memory-web.md 2ms (unchanged)
sase/memory/glossary/named-proc.md 2ms (unchanged)
sase/memory/glossary/nav-item.md 3ms (unchanged)
sase/memory/glossary/nav-section.md 3ms (unchanged)
sase/memory/glossary/node-panel.md 2ms (unchanged)
sase/memory/glossary/oneshot-service-proc.md 2ms (unchanged)
sase/memory/glossary/patch.md 2ms (unchanged)
sase/memory/glossary/proc.md 3ms (unchanged)
sase/memory/glossary/p

… and 5615 more characters

## Dependencies

- **Blocks:** [sase-1kx.4](sase-1kx.4.md) ◐ · ⧖ 2026-10-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kx.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kx.3/README.md) | [sase-1kx.3](sase-1kx.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7710ce5`](https://github.com/sase-org/sase/commit/7710ce5ffa9dbb389e2d8ff4de59130c5ad12e79) | feat(release): add stdlib release watcher | [sase-1kx.3](sase-1kx.3.md) | 2026-10-14 08:21:09 EDT |
