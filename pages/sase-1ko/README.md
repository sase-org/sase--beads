# Bead: sase-1ko — E3 (instruction migration): Explicit instruction delivery cutover

[Bead Pages](../README.md) / sase-1ko

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.land`
**Created:** 2026-10-13 18:10:34 EDT · **Closed:** 2026-10-14 11:27:01 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/e3_explicit_delivery_cutover.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-1l2][2] | Found while reviewing the E3 explicit-delivery epic (note #15); export filtering matters before E4 publishes exports |
| related | file:explicit:294276aba63ff9003d936aaf | attached via sase artifact create --bead |
| related | file:explicit:777e0f69d8eed315766656b3 | attached via sase artifact create --bead |
| related | file:explicit:cbf7c8bf99bcd81ce4eba5d3 | attached via sase artifact create --bead |

_Plus 9 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1l2/README.md

<!-- sase:links:end -->

## Description

Every SASE root agent on Claude, Codex, Grok, and Muse (unless its trust spike fails) gets its memory-built instruction bundle exactly once through an explicit adapter channel, with SASE-owned native instruction files suppressed. Claude helpers get the helper bundle. Each provider switch has a per-provider sunset kill switch and an atomic per-invocation legacy fallback. A trustworthy scoreboard, `sase instructions show`, and a handoff-aware readout prove the result and support the soak.

## Notes

[2026-10-13T22:22:40Z · sase-1ko.1] Sanitized CLI probe evidence for the E3 provider spikes

🔒 E3\_SPIKE\_RESULTS.md

[2026-10-13T22:23:03Z · sase-1ko.1] E3 SPIKE RESULTS: Claude Code 2.1.296 — pass: exact-path `claudeMdExcludes` suppressed workspace and home root files; excluding only CLAUDE.md also prevented AGENTS.md fallback, so no `instructionFiles` override is needed. Nested linked-repo CLAUDE.md with `@AGENTS.md` and nested tools/AGENTS.md still loaded on read. 20 KB `--append-system-prompt-file` and `--append-subagent-system-prompt-file` each appeared in their respective snapshots; helper had no root marker, and `--resume` retained the root snapshot. `autoMemoryEnabled: false` and `CLAUDE_CODE_DISABLE_AUTO_MEMORY=1` both yielded snapshots without an auto-memory section; prefer the per-run setting. Codex CLI 0.162.1 — pass: on a managed fixture, `-c project_doc_max_bytes=0` suppressed project AGENTS.md while 20 KB `developer_instructions` remained; an unmanaged fixture retained its own AGENTS.md without the override. Allowlist-shadow `codex exec` succeeded and wrote rollout to real `~/.codex/sessions` without stale-path errors. No real-home state was linked; Codex created local SQLite files in the shadow during execution (including `memories_1.sqlite`), not symlinks. Multi-agent v2 fork child: unprobed. Muse Code 1.4.7 — pass without `--trust-workspace`: project AGENTS.md was skipped, user skills listed with activation on, and a completed model run successfully used shell and file-edit tools. Grok 1.0.52 — pass: `GROK_MEMORY=0` yielded `prompt_context.json` with `memory_v2_enabled: false` and `agents_md_files: []`; the `--max-turns 1` CLI then exited with “max turns reached,” after writing that evidence. Sanitized evidence attached as E3_SPIKE_RESULTS.md.

[2026-10-13T22:32:27Z · sase-1ko.1] E3 spike addendum: exact settings and Claude auto-memory fingerprint for channel-counting

🔒 E3\_SPIKE\_FINGERPRINTS.md

[2026-10-13T22:32:44Z · sase-1ko.1] E3 SPIKE RESULTS: addendum — Claude auto-memory fingerprint for channel-counting is the prompt_snapshot heading `# Memory` plus lead-in `You have a persistent file-based memory at` (path is per-project). Prefer per-run `--settings` `autoMemoryEnabled: false`; `CLAUDE_CODE_DISABLE_AUTO_MEMORY=1` also removes it. Do not use `"Memory" in snapshot`. Claude 2.1.296 (a–e) pass with exact-path `claudeMdExcludes` and no `instructionFiles` override. Codex 0.162.1 (a,b) pass; (c) unprobed. Muse 1.4.7 pass without `--trust-workspace` (create muse flag). Grok 1.0.52 pass with `GROK_MEMORY=0` (`memory_v2_enabled: false`). Details attached as E3_SPIKE_FINGERPRINTS.md.

[2026-10-14T02:06:13Z · sase-1ko.4] Pre-cutover readout baseline Sep 10-Oct 5: handoff-aware misses per provider and mode with memory reads. Totals match planning baseline; misses within tolerance except Grok/Muse explained in phase note.

🔒 e3\_readout\_baseline\_20260910\_20261005.json

[2026-10-14T02:06:22Z · sase-1ko.4] Pre-cutover readout baseline Oct 6-Oct 13: handoff-aware misses per provider and mode with memory reads. No explicit manifests yet; first_explicit empty, watch starts at first explicit render.

🔒 e3\_readout\_baseline\_20261006\_20261013.json

[2026-10-14T03:37:38Z · sase-1kj.8.1.land] DISCOVERED ISSUE: During artifact-link implementation verification, required ToolRun e3290324a8eee4f12f8877a8d66b4b99 failed tests/instructions/test_delivery_plan.py::test_render_failure_notifies_once. Reproduced standalone with .venv/bin/python -m pytest -n 0 tests/instructions/test_delivery_plan.py::test_render_failure_notifies_once (1 failed in 2.57s): the test monkeypatches sase.llm_provider._instruction_boundary.notify_instruction_fallback, but invoke_with_instructions imports that function from sase.llm_provider.instruction_delivery. Neither file is in the artifact-link diff. This falls directly within this epic's sase-1ko.5 delivery-plan fallback/test seam; update the test patch target or expose an intentional seam, then rerun the node and gate. No task bead created.

[2026-10-14T05:50:07Z · sase-1kj.8.1.land--3] DISCOVERED ISSUE: The required `sase tool run check` during the main stitch conflict repair failed at `lint (symvision)` in ToolRun 13807f8ad336e1fcca8c3dc83eca023d with seven NEW unused public symbols in unchanged instruction-delivery files: `claude_helper_sources` (coverage_sources.py), `contains_contract` and `count_contract_sources` (fingerprints.py), `human_rules_blocks` (grok.py), and `prompt_prefixes`, `prompt_texts`, `rules_texts` (muse.py). These paths are outside the artifact-link change. The gate stopped before validation and scoped tests; the three affected artifact-link test modules passed separately in ToolRun 42d28af5cee04160810f641d3a0d39d1 (70 passed). The symbols are in the completed Grok/Muse delivery area (sase-1ko.9); the acceptance phase sase-1ko.10 remains active. Review each against real non-test consumers and remove dead APIs or wire their intended consumer; do not restore epic-symbol exemptions for symbols the linter reports unused.

[2026-10-14T06:29:03Z · sase-1kj.land] DISCOVERED ISSUE: sase-1kj.land wrapped check c7410810d41e7e4b5841f34a6b7012cc failed two instruction tests outside the startup-starvation diff: tests/instructions/test_delivery_plan.py::test_declared_legacy_hookimpls_resolve_to_provider_legacy (assert 'explicit' == 'inherits_native') and tests/instructions/test_scoreboard_conformance.py::test_conformance_warns_for_duplicate_root_and_leaked_helper_markers (ImportError: cannot import name '_RunManifest' from sase.instructions.manifests). Neither file is in the sase-1kj landing-repair diff. just symvision also reports unused public symbols claude_helper_sources, contains_contract, count_contract_sources, human_rules_blocks, prompt_prefixes, prompt_texts, rules_texts in instructions/* (KNOWN in that ToolRun). Active sase-1ko.10 owns this cutover.

[2026-10-14T11:02:53Z · toobig-7y.verify.0] DISCOVERED ISSUE: Independent reproduction during the verify.py module-split check. ToolRun b85574024daa8fbac1f87328416ac24d failed tests/instructions/test_scoreboard_conformance.py::test_conformance_warns_for_duplicate_root_and_leaked_helper_markers with ImportError: cannot import name '_RunManifest' from sase.instructions.manifests. The test fails while importing its fixture type, before invoking the verification collector or report builder. This is the same acceptance-test failure already recorded in note #9; the current refactor did not touch manifests.py or this test file.

[2026-10-14T12:27:55Z · sase-1ko.10] E3 acceptance record: harness probes both flag states, helper probe, readout, parity, declared gaps, notes for E4

🔒 e3\_acceptance\_record.md

[2026-10-14T12:28:04Z · sase-1ko.10] Pre-cutover readout JSON 2026-10-06 through first Codex explicit 2026-10-14T10:35:06Z

🔒 e3\_readout\_pre\_20261006\_103506.json

[2026-10-14T12:28:12Z · sase-1ko.10] Post-cutover readout JSON from first Codex explicit 2026-10-14T10:35:06Z

🔒 e3\_readout\_post\_20261014\_103506.json

[2026-10-14T12:28:21Z · sase-1ko.10] Workspace-venv harness probe rows for Claude/Codex/Grok/Muse both flag states plus Claude helper

🔒 e3\_harness\_probe\_results.json

[2026-10-14T13:28:29Z · research.1a.cdx] DISCOVERED ISSUE: Independent cdx research at sase 508eb963a33d745eba229efc753d5082d58f134a reproduced incomplete Codex home fallback. With temporary HOME holding SASE ~/AGENTS.md, an empty .codex, and current_instruction_delivery() None, production codex_subprocess_env() links the home AGENTS only with the explicit flag off; flag on omits it despite no active bundle. _codex_home._create_shadow_codex_home keys suppression to the feature flag, while CodexProvider.invoke uses only the single-turn directive without an explicit root. This affects the no-artifacts and render-failure paths; restore home discovery from actual delivery status while keeping SQLite isolation. Separately, render -f mode=export,provider=codex excludes home.* but pkg.sase.repos still includes a home-only linked repo and home configuration metadata; public export must filter transitive home inputs before E4 publishing. Synthetic local probes used no provider/model calls or real-home mutations. Full evidence and decision analysis: file:explicit:8ccecece271b668ba9820e83 (research:202610/instruction_bundles_keep_delivery_preserve_readable_contract__cdx.md). No new task bead: this active migration epic owns the causal boundary.

[2026-10-14T14:05:01Z · sase-1ko.land] LAND TRIAGE (sase-1ko.land) of every child PROPOSED FOLLOW-UP and epic DISCOVERED ISSUE:
Created tasks: sase-1l0 (bug, small: Codex small tier codex-mini-latest HTTP 400; from sase-1ko.8 #3); sase-1l1 (memory, small: harvest the 3 leftover Claude auto-memory notes; from sase-1ko.7 #1/#15, required by foreign_memory); sase-1l2 (bug, medium: export-mode render lists home-only linked repos in pkg.sase.repos; from epic note #15 Finding B, E2 compiler 22ea0cf4db, not E3-caused); sase-1l3 (ci, large: ACE agent-session render/hint cluster; from sase-1ko.3 #1, .5 #1, .7 #10).
Corroborated (+1): sase-1hy (hint duplicates; .6 #1, .7 #7), sase-1ia (raw-prompt rendering; .7 #8/#10, .9), sase-1ki (header bottom pin; .5 #2), all reproduced on master 88acef6234.
Closed: sase-11s (codex phase skipped the planned close; allowlist shadow home verified live).
Declined as already resolved: notify-once patch target (epic #7, .7 #4, .9 #1; fixed in .7); _RunManifest import/private symbols and the 7 unused instruction symbols (epic #8-#10, .4 #1, .7 #9, .8 #4, .9 #2; just symvision clean on 88acef6234); duplicate Claude prompt_snapshot and numbered-heading/home-H1 observer misreads (.7 #3/#13, .8 #1-#2; fixed in .10); stale sase-1kj.7 epic-symbol (.2 #2; gone); sase-core clippy (.2 #1; already sase-1an); Codex shadow memories_1.sqlite (.1 #1; per-run local file in a disposable shadow that is rmtree'd, never linked); override_flags vs SASE_FEATURE_FLAGS (.10 #3; documented resolver prec

… and 2443 more characters

## Attachments

- 🔒 E3\_SPIKE\_RESULTS.md · text/markdown · 2.92383 KiB (private attachment)
- 🔒 E3\_SPIKE\_FINGERPRINTS.md · text/markdown · 4.25586 KiB (private attachment)
- 🔒 e3\_readout\_baseline\_20260910\_20261005.json · application/json · 4.40625 KiB (private attachment)
- 🔒 e3\_readout\_baseline\_20261006\_20261013.json · application/json · 7.26074 KiB (private attachment)
- 🔒 e3\_acceptance\_record.md · text/markdown · 9.52539 KiB (private attachment)
- 🔒 e3\_readout\_pre\_20261006\_103506.json · application/json · 7.70898 KiB (private attachment)
- 🔒 e3\_readout\_post\_20261014\_103506.json · application/json · 1.53711 KiB (private attachment)
- 🔒 e3\_harness\_probe\_results.json · application/json · 26.8691 KiB (private attachment)
- 🔒 e3\_acceptance\_addendum.md · text/markdown · 5.14453 KiB (private attachment)

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1ko.1](sase-1ko.1.md) | Provider channel and suppression spikes, with outcomes recorded on the epic | ✓ closed | small | 2026-10-13 | 1 | 0 |
| [sase-1ko.10](sase-1ko.10.md) | Live acceptance probes, decision record, docs, and acceptance record | ✓ closed | medium | 2026-10-13 | 1 | 1 |
| [sase-1ko.2](sase-1ko.2.md) | Instruction manifest wire v2 in sase-core (delivery slots and fallback), binding, adapter, pin move | ✓ closed | medium | 2026-10-13 | 1 | 2 |
| [sase-1ko.3](sase-1ko.3.md) | Scoreboard sees dismissed agents, and the new sase instructions show command | ✓ closed | medium | 2026-10-13 | 1 | 1 |
| [sase-1ko.4](sase-1ko.4.md) | Handoff-aware declaration and memory-read readout, with the pre-cutover baseline attached | ✓ closed | medium | 2026-10-13 | 1 | 1 |
| [sase-1ko.5](sase-1ko.5.md) | Delivery-plan hook, active delivery, atomic legacy fallback, and helper manifests at the boundary | ✓ closed | medium | 2026-10-13 | 1 | 1 |
| [sase-1ko.6](sase-1ko.6.md) | Channel-aware, occurrence-exact scoreboard counting and the conformance check | ✓ closed | medium | 2026-10-13 | 1 | 1 |
| [sase-1ko.7](sase-1ko.7.md) | Claude root bundle via system-prompt file, helper bundle, exact-path native exclusion | ✓ closed | medium | 2026-10-13 | 1 | 1 |
| [sase-1ko.8](sase-1ko.8.md) | Codex developer-instructions delivery, project-doc suppression, and shadow-home hygiene (folds sase-11s) | ✓ closed | medium | 2026-10-13 | 1 | 1 |
| [sase-1ko.9](sase-1ko.9.md) | Grok full-bundle rules and Muse prompt-prefix delivery | ✓ closed | medium | 2026-10-13 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1ko: E3 (instruction migration): Explicit instruction delivery cutover [closed]"]
    n1["sase-1ko.1: Provider channel and suppression spikes, with outcomes recorded on the epic [closed]"]
    n2["sase-1ko.10: Live acceptance probes, decision record, docs, and acceptance record [closed]"]
    n3["sase-1ko.2: Instruction manifest wire v2 in sase-core (delivery slots and fallback), binding, adapter, pin move [closed]"]
    n4["sase-1ko.3: Scoreboard sees dismissed agents, and the new sase instructions show command [closed]"]
    n5["sase-1ko.4: Handoff-aware declaration and memory-read readout, with the pre-cutover baseline attached [closed]"]
    n6["sase-1ko.5: Delivery-plan hook, active delivery, atomic legacy fallback, and helper manifests at the boundary [closed]"]
    n7["sase-1ko.6: Channel-aware, occurrence-exact scoreboard counting and the conformance check [closed]"]
    n8["sase-1ko.7: Claude root bundle via system-prompt file, helper bundle, exact-path native exclusion [closed]"]
    n9["sase-1ko.8: Codex developer-instructions delivery, project-doc suppression, and shadow-home hygiene (folds sase-11s) [closed]"]
    n10["sase-1ko.9: Grok full-bundle rules and Muse prompt-prefix delivery [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n1 -.-> n8
    n1 -.-> n9
    n1 -.-> n10
    n3 -.-> n6
    n4 -.-> n5
    n4 -.-> n7
    n5 -.-> n2
    n6 -.-> n7
    n6 -.-> n8
    n6 -.-> n9
    n6 -.-> n10
    n7 -.-> n8
    n7 -.-> n9
    n7 -.-> n10
    n8 -.-> n2
    n9 -.-> n2
    n10 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.1/README.md) | [sase-1ko.1](sase-1ko.1.md) | 0 |
| [bbugyi200.apollo.sase-1ko.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1ko.10.md) | [sase-1ko.10](sase-1ko.10.md) | 1 |
| [bbugyi200.apollo.sase-1ko.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.2/README.md) | [sase-1ko.2](sase-1ko.2.md) | 2 |
| [bbugyi200.apollo.sase-1ko.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.3/README.md) | [sase-1ko.3](sase-1ko.3.md) | 1 |
| [bbugyi200.apollo.sase-1ko.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1ko.4.md) | [sase-1ko.4](sase-1ko.4.md) | 1 |
| [bbugyi200.apollo.sase-1ko.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.5/README.md) | [sase-1ko.5](sase-1ko.5.md) | 1 |
| [bbugyi200.apollo.sase-1ko.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.6/README.md) | [sase-1ko.6](sase-1ko.6.md) | 1 |
| [bbugyi200.apollo.sase-1ko.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.7/README.md) | [sase-1ko.7](sase-1ko.7.md) | 1 |
| [bbugyi200.apollo.sase-1ko.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.8/README.md) | [sase-1ko.8](sase-1ko.8.md) | 1 |
| [bbugyi200.apollo.sase-1ko.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1ko.9.md) | [sase-1ko.9](sase-1ko.9.md) | 1 |
| [bbugyi200.apollo.sase-1ko.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1ko.land.md) | [sase-1ko](README.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@973017b`](https://github.com/sase-org/sase-core/commit/973017b6b6a91c0e843d60a65040c9496e94d423) | feat(instruction-manifest)!: add v2 delivery slots and fallback | [sase-1ko.2](sase-1ko.2.md) | 2026-10-13 19:38:10 EDT |
| sase | [`96090a5`](https://github.com/sase-org/sase/commit/96090a52cfb4b38a64e8a05a23d305bf0009080b) | feat(instructions): adopt manifest v2 delivery slots | [sase-1ko.2](sase-1ko.2.md) | 2026-10-13 19:44:26 EDT |
| sase | [`d69cd49`](https://github.com/sase-org/sase/commit/d69cd499dd26b04534b9b4a11af540e14a6c73af) | feat(instructions): land delivery-plan hook and declared-legacy fallback | [sase-1ko.5](sase-1ko.5.md) | 2026-10-13 21:37:34 EDT |
| sase | [`c5e4da7`](https://github.com/sase-org/sase/commit/c5e4da7065cc40a5e81163a949a499713994db06) | feat(instructions): enumerate dismissed runs and add instructions show | [sase-1ko.3](sase-1ko.3.md) | 2026-10-13 21:44:32 EDT |
| sase | [`26a12b6`](https://github.com/sase-org/sase/commit/26a12b63df1c995c6d24a408f43991f8cdca0e44) | feat(instructions): add channel-aware conformance scoreboard | [sase-1ko.6](sase-1ko.6.md) | 2026-10-13 23:20:38 EDT |
| sase | [`429353b`](https://github.com/sase-org/sase/commit/429353b015be5e4f644a6ee5762be5dd3df64e6b) | feat(codex): deliver explicit root instructions | [sase-1ko.8](sase-1ko.8.md) | 2026-10-14 00:17:31 EDT |
| sase | [`e79a89d`](https://github.com/sase-org/sase/commit/e79a89d755a1f91cb032bd2199709994ab9d5d9d) | feat(instructions): add handoff-aware declaration readout | [sase-1ko.4](sase-1ko.4.md) | 2026-10-14 00:20:55 EDT |
| sase | [`8847d07`](https://github.com/sase-org/sase/commit/8847d07a086b9e930f1a787425ec4c3272ea6824) | feat(instructions): add Grok and Muse explicit delivery | [sase-1ko.9](sase-1ko.9.md) | 2026-10-14 04:42:35 EDT |
| sase | [`d265233`](https://github.com/sase-org/sase/commit/d2652334910952f8c244b58d3d32f1ae4ed8d0fd) | feat(claude): deliver explicit root and helper instruction bundles | [sase-1ko.7](sase-1ko.7.md) | 2026-10-14 07:42:50 EDT |
| sase | [`88acef6`](https://github.com/sase-org/sase/commit/88acef62344479241af5036af108f92fbc71a1eb) | feat(instructions): record E3 explicit-delivery acceptance | [sase-1ko.10](sase-1ko.10.md) | 2026-10-14 09:18:29 EDT |
| sase | [`d070e6b`](https://github.com/sase-org/sase/commit/d070e6b2dc17d1229f6d13b2a4d0ab1dd25b0f5d) | fix(instructions): land remaining E3 explicit-delivery defects | [sase-1ko](README.md) | 2026-10-14 11:30:55 EDT |
| sase--plans | [`sase--plans@01b43c2`](https://github.com/sase-org/sase--plans/commit/01b43c257e7d65ec816036bf29ad1d4ca79340b6) | docs(e3): mark explicit delivery cutover plan done | [sase-1ko](README.md) | 2026-10-14 11:34:24 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.1a.cdx][1] | Understand user-requested instruction bundle migration rationale, phases, and completion state | 1 |
| read-by | [agent:research.1a.cld][2] | Research whether to proceed with or revert the instruction-bundle migration epic | 1 |
| read-by | [agent:research.1a.final][3] | Check E3 epic status, notes, and E4 handoff for instruction bundle transparency research | 1 |
| read-by | [agent:research.1a.grk][4] | Need the E3 instruction-migration epic scope, notes, and acceptance criteria | 1 |
| read-by | [agent:sase-1kl.4--1][5] | Check whether instructions epic owns the Master Gate reds | 1 |
| read-by | [agent:sase-1ko.6][6] | Need the spike-recorded auto-memory fingerprint for channel-counting | 1 |
| read-by | [agent:sase-1ko.7][7] | Resolve prior implementation notes and current integration state | 1 |
| read-by | [agent:sase-1ko.8][8] | Read E3 spike outcomes required by the Codex phase | 1 |
| read-by | [agent:toobig-7y.verify.0][9] | Need the active instruction-delivery epic scope before recording the repeated conformance test failure | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.1a.cdx/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.1a.cld/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.1a.final/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.1a.grk/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1kl.4.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.6/README.md
[7]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1ko.7.md
[8]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.8/README.md
[9]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.toobig-7y.verify.0/README.md

<!-- sase:referenced-by:end -->
