# Bead: sase-ha — Meta Muse Code as a first-class SASE LLM provider

[Bead Pages](../README.md) / sase-ha

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ve](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ve/README.md) · **Assignee:** `sase-ha.land`
**Created:** 2026-08-07 20:45:30 EDT · **Closed:** 2026-08-08 10:00:55 EDT
**Plan:** [202608/muse\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/muse_provider.md)

## Description

SASE can run agents on Meta's Muse Code CLI as a native provider — selected by config, `%model:muse/...`, or `SASE_MUSE_PATH` — with reply, usage, and tool-call artifacts; correctly-rendered Muse-native skills; a data-sharing advisory that makes the Contributor model's training terms impossible to miss; and `sase agent-cli` install/update support that works for a channel-versioned, self-updating CLI.

## Notes

[2026-08-08T02:05:36Z · vf] Independent corroboration from an unrelated task (ACE saved-query 0-prefix feature), 2026-08-08: reproduced all three pre-existing failures already noted on sase-ha.3/sase-ha.6 as PROPOSED FOLLOW-UPs, via 'git stash' on the same commit (44fa7eee2). (1) tests/test_gate_cli_show.py (4 tests) + tests/gate_conformance/test_gate_conformance.py[cli|ace-legacy_shared_input] — GateError from src/sase/notification_gates/kind_validation/custom.py:52, legacy shared-input fixtures not migrated with a1cc172d3. (2) tests/doctor/test_checks_providers.py::test_setup_hint_points_script_installs_at_the_install_subcommand — muse setup_hint() auth string mismatch. (3) NEW signature not yet on this epic: tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_raw_diagnostics_png_snapshot fails 'just test-visual' with 415/1520532 changed pixels (0.027%); reproduces identically on a clean stash of the same commit, so unrelated to any sase-ha phase's diff — flagging for the land phase (sase-ha.7/sase-ha.8) to sweep alongside the other two.

[2026-08-08T14:00:55Z · sase-ha.land] VERIFIED (step 1). All 8 phases closed with resolution done. Read every child note and confirmed each against the source and the epic's 7 commits (47b9f0017, 44fa7eee2, 050c9477c, 85d12614e, 90b17d824, b9ac35d9e, 1d5a8a70f). cli_meta: LatestQuery + HTTPS JSON-endpoint latest oracle, InstallMethod.SCRIPT, VersionCompare.EXACT, env-carrying self-update — confirmed live, 'sase agent-cli list' shows Muse Code at 0.1.0-R708.1 with latest matching, which is exactly the PEP 440 silent-failure the plan existed to fix. provider: src/sase/llm_provider/muse.py (457 lines) with both tiers deliberately on muse-spark-1.2, all seven canonical efforts incl. max->ultra, --disable-sandbox by default with SASE_MUSE_SANDBOX=on, MUSE_NO_AUTO_UPDATE, no autodetect priority; _subprocess_muse.py (351) implementing the five documented parser rules. cli_install: src/sase/agent_clis/install.py read in full — HTTPS-only with redirect-downgrade recheck on the served URL, 1 MB cap, 0o600 temp file, SHA-256 shown before the run, shell-free 'bash <tmpfile>', post-install re-probe with a PATH note that explicitly does not edit rc files, cleanup() in a finally. artifacts: _tool_call_muse.py (375) and _muse_session_usage.py (157) read in full — usage summed from model_completed only, goal_usage_attribution ignored to avoid double counting, XDG_DATA_HOME honored, globbed date components, missing log degrades to zeroed usage plus a diagnostic. advisory: llm_model_advisories hook, registry.model_advisory_map/for/marker/color, and all four claimed render sites confirmed present (model_picker_rows.py, provider_styles.py, xprompt/model_completion.py, doctor/checks_providers_advisory.py); 'sase doctor -C llm.model_advisory -v' returns OK and silent for shipped defaults. polish: muse+meta Meta-blue styles in ace/tui/provider_styles.py, the badge in integrations/provider_badges.py, meta=#0064E0 in registry._PROVIDER_FAMILY_COLORS. docs: Muse sections and provider enumerations across llms.md, agent_providers.md, configuration.md, plugins.md, ace.md, xprompt.md, cli.md, getting_started.md, commit_workflows.md and default_config.yml. verify: phase 8 closed without a note; its transcript shows plan steps 1-5 verified live but step 6 left running — I finished it and recorded the detail on sase-ha.8.

VERIFIED (step 2 — integration). No commit after the epic's last (1d5a8a70f) touches src/sase/llm_provider/ or src/sase/agent_clis/, so nothing conflicts with or duplicates this epic. Checked the two breaking skills commits that landed after it (ab442ed24, c181d4c24 — skills must live in skills/, sources moved to src/sase/skills/, #<name> no longer resolves a skill): Muse integrates cleanly through the provider hooks, confirmed live with 'sase skill list' reporting 6 providers and muse present on all 18 sources with 0 missing targets, and docs/xprompt.md's skill-target table still carries the Muse Code row. Verified no Python module enumerates providers without muse. 'just check-full' at HEAD passes every lint gate and 27601 tests.

FOLLOW-UPS (step 3). Collected every PROPOSED FOLLOW-UP across the children; 12 entries reduced to 7 distinct issues. Filed as new tasks via /sase_new_task: sase-hg (large) project Muse session-lifetime subagents into ACE, from sase-ha.4 — an explicit non-goal in the plan, so new work not epic debt; sase-hh (small) decide whether SASE must disable or reconcile Muse's cron_* tools and per-session cron.db, from sase-ha.4. Corroborated rather than duplicated: +1 on sase-ct (now +31) carrying both parallel-lane flakes — sase-ha.3's test_launcher_qualifies_research_swarm_per_dispatch, and a new one I hit, test_agents_slow_tool_calls_fold_levels_png_snapshots, which failed 'just test-visual' with a 15s settle timeout and passed in isolation at 4.64s. Attached to an active epic rather than filed: DISCOVERED ISSUE on sase-hf for tests/test_content_layout.py::test_project_home_and_chezmoi_named_paths_are_canonical, the only failure in check-full — sase-hf.1 bumped CONTENT_LAYOUT_SCHEMA_VERSION to 3 in sase-core (cd52cb8, past the v0.20.0 release) while this repo still pins <0.21.0 and asserts 2, and the Justfile deliberately builds core from the linked checkout, so it fails in every workspace; unrelated to Muse. Declined, with reasons: the 6 gate failures reported by sase-ha.1/.2/.3/.7 (test_gate_cli_show x4, gate_conformance legacy_shared_input x2) are fixed at HEAD by 0a13ffed4/f2c6f1889/ed50d45ee and pass in check-full, so no task; test_setup_hint_points_script_installs_at_the_install_subcommand, reported by sase-ha.4 and sase-ha.6, was fixed inside this epic by b9ac35d9e and passes; the chezmoi 'research-highlights' file-hook globs->path_globs warning reported by sase-ha.3 no longer reproduces on any sase invocation; the frontmatter_panel_raw_diagnostics PNG pixel drift recorded on this epic's own note now passes clean; and sase-ha.2's note that 'muse exec' rejects --model without '--provider meta' is a design constraint for any future echo/preset smoke mode, not work — recorded here instead of as a bead. No sase-ha symvision --epic-symbol whitelist entries exist in src/ or tests/, so this close expires none.

[2026-08-08T14:03:11Z · sase-ha.land] Land verification: read all 8 child beads' notes and checked each claim against source and the epic's 7 commits (47b9f0017..1d5a8a70f). install.py verified HTTPS-only w/ redirect-downgrade recheck, 1MB cap, 0o600 temp, SHA-256 shown, shell-free bash, finally-cleanup; PEP 440 fix confirmed live via 'sase agent-cli list'. muse.py/_subprocess_muse.py/_muse_session_usage.py verified: 5 parser rules, max->ultra effort map, both-tiers-on-full-price, sum model_completed (no goal_usage_attribution double-count). All 4 advisory render sites present; 'sase doctor -C llm.model_advisory -v' OK+silent on shipped defaults. sase-ha.8 had closed with no note and left just check-full unreported; I ran it: all lint gates green (symvision, toobig, committed plans), 27601 passed / 10 skipped / 1 failed. Integration: no post-epic commit touches src/sase/llm_provider/ or src/sase/agent_clis/; the breaking skills commits (ab442ed24, c181d4c24) integrate cleanly -- 'sase skill list' shows 6 providers, muse on all 18 sources, 0 missing targets, docs/xprompt.md Muse Code row intact. The single check-full failure is not this epic's: test_content_layout.py::test_project_home_and_chezmoi_named_paths_are_canonical expects schema_version 2 but gets 3 because sase-hf.1 bumped CONTENT_LAYOUT_SCHEMA_VERSION in sase-core (cd52cb8) past v0.20.0 while this repo pins <0.21.0; recorded as DISCOVERED ISSUE on in-progress epic sase-hf. Follow-ups: 12 PROPOSED FOLLOW-UP entries reduced to 7 distinct issues -- filed sase-hg (large, project Muse subagents into ACE; explicit plan non-goal) and sase-hh (small, decide whether SASE disables or reconciles Muse cron_* tools); corroborated sase-ct (+1, now +31) with both parallel-lane flakes incl. test_agents_slow_tool_calls_fold_levels_png_snapshots timing out at 15s under the full visual run but passing in 4.64s alone. Declined with reasons: the 6 gate failures 4 phases reported all pass at HEAD; the doctor setup_hint failure was fixed inside the epic by b9ac35d9e; the chezmoi globs->path_globs warning no longer reproduces; the frontmatter_panel pixel drift passes clean; and 'muse exec --model' / '--provider meta' is a design constraint, not work. Post-close 'just symvision' was clean -- no sase-ha whitelist entries existed, so nothing expired and no dead code to remove.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-ha.1](sase-ha.1.md) | Channel-versioned agent-CLI detection and update | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-ha.2](sase-ha.2.md) | The Muse provider and its JSONL stream parser | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-ha.3](sase-ha.3.md) | sase agent-cli install | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-ha.4](sase-ha.4.md) | Usage, tool-call, and model-identity artifacts | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-ha.5](sase-ha.5.md) | Model advisories and the Contributor data-sharing guard | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-ha.6](sase-ha.6.md) | ACE styling and provider badges | ✓ closed | small | 2026-08-07 | 1 | 1 |
| [sase-ha.7](sase-ha.7.md) | Documentation sweep | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-ha.8](sase-ha.8.md) | Live end-to-end verification | ✓ closed | small | 2026-08-07 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-ha: Meta Muse Code as a first-class SASE LLM provider [closed]"]
    n1["sase-ha.1: Channel-versioned agent-CLI detection and update [closed]"]
    n2["sase-ha.2: The Muse provider and its JSONL stream parser [closed]"]
    n3["sase-ha.3: sase agent-cli install [closed]"]
    n4["sase-ha.4: Usage, tool-call, and model-identity artifacts [closed]"]
    n5["sase-ha.5: Model advisories and the Contributor data-sharing guard [closed]"]
    n6["sase-ha.6: ACE styling and provider badges [closed]"]
    n7["sase-ha.7: Documentation sweep [closed]"]
    n8["sase-ha.8: Live end-to-end verification [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n3
    n2 -.-> n4
    n2 -.-> n5
    n2 -.-> n6
    n3 -.-> n7
    n4 -.-> n7
    n5 -.-> n7
    n6 -.-> n7
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ha.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.1/README.md) | [sase-ha.1](sase-ha.1.md) | 1 |
| [bbugyi200.athena.sase-ha.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.2/README.md) | [sase-ha.2](sase-ha.2.md) | 1 |
| [bbugyi200.athena.sase-ha.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.3/README.md) | [sase-ha.3](sase-ha.3.md) | 1 |
| [bbugyi200.athena.sase-ha.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.4/README.md) | [sase-ha.4](sase-ha.4.md) | 1 |
| [bbugyi200.athena.sase-ha.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.5/README.md) | [sase-ha.5](sase-ha.5.md) | 1 |
| [bbugyi200.athena.sase-ha.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.6/README.md) | [sase-ha.6](sase-ha.6.md) | 1 |
| [bbugyi200.athena.sase-ha.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.7/README.md) | [sase-ha.7](sase-ha.7.md) | 1 |
| [bbugyi200.athena.sase-ha.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.8/README.md) | [sase-ha.8](sase-ha.8.md) | 0 |
| [bbugyi200.athena.sase-ha.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.land/README.md) | [sase-ha](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`47b9f00`](https://github.com/sase-org/sase/commit/47b9f0017075f3efd54f8d5098abf77dbd39a2a5) | feat(agent-clis): support channel-versioned agent CLIs | [sase-ha.1](sase-ha.1.md) | 2026-08-07 21:09:24 EDT |
| sase | [`44fa7ee`](https://github.com/sase-org/sase/commit/44fa7eee2445bc1b33742cd3ffef7f7a983110d0) | feat(llm-provider): add the Muse Code provider and its JSONL stream parser | [sase-ha.2](sase-ha.2.md) | 2026-08-07 21:23:25 EDT |
| sase | [`050c947`](https://github.com/sase-org/sase/commit/050c9477cea1e11b85df7d504b46a50db3bbdd67) | feat(llm-provider): parse Muse tool calls, usage, and model identity | [sase-ha.4](sase-ha.4.md) | 2026-08-07 21:44:51 EDT |
| sase | [`85d1261`](https://github.com/sase-org/sase/commit/85d12614e2ae2ab6acc5b4455bba095e91bdb297) | feat(agent-clis): add a confirmed, shell-free \`sase agent-cli install\` | [sase-ha.3](sase-ha.3.md) | 2026-08-07 21:56:50 EDT |
| sase | [`90b17d8`](https://github.com/sase-org/sase/commit/90b17d824596216df6f0cee97ec5a363f6cbd333) | feat(ace): give Muse a Meta-blue provider palette and badge | [sase-ha.6](sase-ha.6.md) | 2026-08-07 22:03:48 EDT |
| sase | [`b9ac35d`](https://github.com/sase-org/sase/commit/b9ac35d9e2e36a1f148670213b089295b69b297b) | feat(llm-provider): add model advisories and a data-sharing guard | [sase-ha.5](sase-ha.5.md) | 2026-08-07 22:04:04 EDT |
| sase | [`1d5a8a7`](https://github.com/sase-org/sase/commit/1d5a8a70ff84a981f54b1eda0d9384fe687c1f14) | docs(llms): document the Muse Code provider end to end | [sase-ha.7](sase-ha.7.md) | 2026-08-07 22:30:14 EDT |
| sase--plans | [`sase--plans@e476541`](https://github.com/sase-org/sase--plans/commit/e4765410c1099fe4c70a3cafd1bad6e842957554) | docs(plan): mark the Muse provider plan done | [sase-ha](README.md) | 2026-08-08 10:04:37 EDT |
