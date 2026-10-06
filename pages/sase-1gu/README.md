# Bead: sase-1gu — E1: Instruction scoreboard and stopgaps (memory-built instruction migration)

[Bead Pages](../README.md) / sase-1gu

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0x2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0x2.md) · **Assignee:** `sase-1gu.land`
**Created:** 2026-10-05 15:52:18 EDT · **Closed:** 2026-10-06 12:05:33 EDT
**Plan:** [202610/e1\_instruction\_scoreboard\_and\_stopgaps.md](https://github.com/sase-org/sase--plans/blob/main/202610/e1_instruction_scoreboard_and_stopgaps.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/e1_instruction_scoreboard_and_stopgaps.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/e1_instruction_scoreboard_and_stopgaps.md

<!-- sase:links:end -->

## Description

One read-only command, `sase instructions verify`, shows what each provider's SASE runs and native helpers actually loaded, read from the providers' own session records. It reproduces today's delivery bugs: Claude and Codex load the contract twice, Muse gets no home layer, and Grok gets nothing. The two measured harms stop. Grok root runs get the SASE single-turn directive and the project `AGENTS.md` exactly once through `--rules`. Claude native helpers get a packaged helper template, and a per-run PreToolUse guard denies their root-only operations (`sase final …`, turn-ending skills). Both stopgaps have sunset kill switches. Baseline and after scoreboard JSON plus an acceptance record are attached to this epic, and bead `sase-1gj` is closed as superseded.

## Notes

[2026-10-05T21:08:00Z · sase-1gu.2] E1 scoreboard live baseline: claude 2x, codex 1x (observed; see note), muse 1x no-home, grok 0

🔒 instructions\_baseline.json

[2026-10-06T12:44:33Z · sase-1gu.6--1] E1 acceptance probes did NOT run: LaunchApproval launch-ac9ca583-8595-4bc8-90cd-42b631170bbe answered Approve but dispatch failed with ImportError: cannot import name add_or_update_prompt from partially initialized module sase.history.prompt_store_mutations (circular import). Reproduced in this workspace with .venv/bin/python importing sase.history.prompt_store_mutations first (prompt_store_mutations line 9 imports prompt_store; prompt_store line 477 imports back from prompt_store_mutations); importing prompt_store first succeeds. No Grok/Claude probe agents assumed running; dispatch_status=failed. Attached artifacts unchanged: instructions_baseline.json already on this epic; no after-JSON or acceptance record exists to attach. Leaving sase-1gu.6 and sase-1gj open per acceptance checkpoint. epic-symbols for sase-1gu.6 verified clean.

[2026-10-06T14:31:06Z · sase-1gu.6] E1 acceptance record and after-scoreboard (probes blocked pre-existing, see record) 🔒 e1\_after\_scoreboard.json 🔒 e1\_acceptance\_record.md -r Attach E1 after JSON and acceptance record to epic

[2026-10-06T15:13:15Z · sase-1gu.land] LAND TRIAGE (sase-1gu.land) of PROPOSED FOLLOW-UPs: (1) sase-1gu.1#1 / sase-1gu.4#2 macro-terminology infographic residuals: DECLINED, already resolved (tests/test_macro_terminology.py 10 passed at 17c7f66bb3; sase-1eq.12.3 relabel closed). (2) sase-1gu.2#1 _lint-flags vs flag bead sase-1gw: DECLINED, resolved once sase-1gu.4 landed (just _lint-flags passes at HEAD). (3) sase-1gu.2#2 codex observed 1x vs plan 2x: NOT a distinct follow-up. It is a scoreboard parser bug caused by this epic: Codex 0.160.1 joins home and project docs inside one '# AGENTS.md instructions' <INSTRUCTIONS> block separated by '--- project-doc ---', and src/sase/instructions/codex.py counts one source. Folded into the remaining-work tale. (4) sase-1gu.6#1 stale sase-core schema in just check _setup: DECLINED, resolved (just _setup rebuilt sase_core_rs 0.37.0 cleanly; 164 E1-scoped tests pass). (5) sase-1gu.6#2 sase.history circular import breaking LaunchApproval dispatch: not caused by E1 (ad7f3a19a3, closed epic sase-1d8); filed as task sase-1h2 (bug, small, ready, related sase-1cf). Its 're-request the probes' half is moot: acceptance evidence was gathered without LaunchApproval (next note).

[2026-10-06T15:13:26Z · sase-1gu.land] LAND ACCEPTANCE EVIDENCE (2026-10-06, host primary checkout at 17c7f66bb3, contains 724f9ea9c2/421c3ba045/08c8a56b36/28f99cb4ca/336d754b4c; Grok fix deployed 2026-10-05 16:34 EDT, Claude helper channel deployed 2026-10-06 05:26 EDT). GROK: real post-fix root session (build 2026-10-05T22:38:12Z, cwd sase_10, audience primary) system_prompt.txt has exactly one <human_rules> block with 1x 'SASE single-turn instructions for Grok:', 1x project H1, contract 1x; prompt_context.json agents_md_files: []. 'sase instructions verify --since 24h' grok row: contract '1x [0,1]', project ok, directive ok, native-full 0. Plus the sase-1gu.3 canary. CLAUDE: the land agent's own run (claude argv carries --settings guard plus --append-subagent-system-prompt-file .../claude_helper_instructions.md) spawned one general-purpose and one Explore helper. Both helper prompt_snapshot attachments carry '# SASE Helper Instructions'. Both refused 'sase final submit /dev/null' from the template text before any tool call: 0 attempts, 0 accepted. Running the live hook command from this run's --settings: helper 'sase final submit', 'FOO=1 .venv/bin/sase final prepare x', and Skill sase_final are denied with 'SASE helper guard:'; helper 'sase final status' and the root submit are allowed. The sase-1gu.4 raw probe already proved deny-under-bypass end to end. Doctor: providers.claude_helper_channel OK; sase flag list shows both sunset flags on; sase memory init --check clean; decisions:helpers-return-roots-declare resolves.

[2026-10-06T15:26:43Z · sase-1gu.land] Corrected baseline: Claude 2x, Codex 2x, Muse 1x no-home, Grok 0

[instructions\_baseline\_v2.json]

[2026-10-06T15:26:55Z · sase-1gu.land] After scoreboard: Grok 1x project/directive ok, -p grok returns rows

[e1\_after\_scoreboard\_v2.json]

[2026-10-06T15:27:06Z · sase-1gu.land] Acceptance record v2 for scoreboard fixes

[e1\_acceptance\_record\_v2.md]

[2026-10-06T16:05:33Z · sase-1gu.land--2] E1 land closeout: scoreboard fixes landed (Codex 2x count, Grok verify rows, instructions verify help text; completion snapshot regenerated via just sync-completion-spec). Re-captured baseline v2 (instructions_baseline_v2.json) and after JSON (e1_after_scoreboard_v2.json) plus acceptance record v2 attached (notes #6-8). Check run eb3f153b83950a46b4667df264f73e8b: verdict no_new_failures, only the 2 KNOWN symvision _runs private-import items (src/sase/agents_sync/v2_snapshot_io.py, src/sase/ace/tui/widgets/decks/final/overview_card.py); just symvision reproduces the same 2 items. Follow-up sase-1h2 filed for the sase.history circular import. Plan 202610/e1_instruction_scoreboard_and_stopgaps.md status set done.

## Attachments

- 🔒 instructions\_baseline.json · application/json · 1.47852 KiB (private attachment)
- 🔒 e1\_acceptance\_record.md · text/markdown · 2.81152 KiB (private attachment)
- 🔒 e1\_after\_scoreboard.json · application/json · 1.48633 KiB (private attachment)
- 🌐 instructions\_baseline\_v2.json · application/json · 1.47852 KiB
- 🌐 e1\_after\_scoreboard\_v2.json · application/json · 1.76855 KiB
- 🌐 e1\_acceptance\_record\_v2.md · text/markdown · 4.09961 KiB

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1gu.1](sase-1gu.1.md) | The \`sase instructions\` command group absorbs \`sase memory agent-docs\` | ✓ closed | small | 2026-10-05 | 1 | 1 |
| [sase-1gu.2](sase-1gu.2.md) | \`sase instructions verify\`: observed-mode scoreboard and doctor group | ✓ closed | medium | 2026-10-05 | 1 | 1 |
| [sase-1gu.3](sase-1gu.3.md) | Grok root runs receive the directive and project AGENTS.md once via --rules | ✓ closed | small | 2026-10-05 | 1 | 1 |
| [sase-1gu.4](sase-1gu.4.md) | Claude native helpers get a helper template and a root-only PreToolUse guard | ✓ closed | medium | 2026-10-05 | 1 | 1 |
| [sase-1gu.5](sase-1gu.5.md) | Root-only contract sentence, decision record, capability docs, ownership inventory | ✓ closed | medium | 2026-10-05 | 1 | 1 |
| [sase-1gu.6](sase-1gu.6.md) | Live probes, after-scoreboard, acceptance record, close sase-1gj | ✓ closed | small | 2026-10-05 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1gu: E1: Instruction scoreboard and stopgaps (memory-built instruction migration) [closed]"]
    n1["sase-1gu.1: The `sase instructions` command group absorbs `sase memory agent-docs` [closed]"]
    n2["sase-1gu.2: `sase instructions verify`: observed-mode scoreboard and doctor group [closed]"]
    n3["sase-1gu.3: Grok root runs receive the directive and project AGENTS.md once via --rules [closed]"]
    n4["sase-1gu.4: Claude native helpers get a helper template and a root-only PreToolUse guard [closed]"]
    n5["sase-1gu.5: Root-only contract sentence, decision record, capability docs, ownership inventory [closed]"]
    n6["sase-1gu.6: Live probes, after-scoreboard, acceptance record, close sase-1gj [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n2
    n2 -.-> n5
    n3 -.-> n5
    n4 -.-> n5
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1gu.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.1/README.md) | [sase-1gu.1](sase-1gu.1.md) | 1 |
| [bbugyi200.athena.sase-1gu.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.2/README.md) | [sase-1gu.2](sase-1gu.2.md) | 1 |
| [bbugyi200.athena.sase-1gu.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.3/README.md) | [sase-1gu.3](sase-1gu.3.md) | 1 |
| [bbugyi200.athena.sase-1gu.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.4/README.md) | [sase-1gu.4](sase-1gu.4.md) | 1 |
| [bbugyi200.athena.sase-1gu.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.5/README.md) | [sase-1gu.5](sase-1gu.5.md) | 1 |
| [bbugyi200.athena.sase-1gu.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.6/README.md) | [sase-1gu.6](sase-1gu.6.md) | 0 |
| [bbugyi200.athena.sase-1gu.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1gu.land.md) | [sase-1gu](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`724f9ea`](https://github.com/sase-org/sase/commit/724f9ea9c204296569c103f4ca6ceaa118d5e509) | feat(llm-provider): add Grok provider core with docs and registry | [sase-1gu.3](sase-1gu.3.md) | 2026-10-05 16:04:16 EDT |
| sase | [`8071b49`](https://github.com/sase-org/sase/commit/8071b49282a7642d0eab85a97fe8f65bbf179a92) | feat(cli)!: add sase instructions group absorbing memory agent-docs | [sase-1gu.1](sase-1gu.1.md) | 2026-10-05 16:37:13 EDT |
| sase | [`421c3ba`](https://github.com/sase-org/sase/commit/421c3ba045b9f7376c4f5bc05eb6c01d4acfdaf7) | feat(claude): add helper guard and channel with sunset flag | [sase-1gu.4](sase-1gu.4.md) | 2026-10-05 17:13:38 EDT |
| sase | [`08c8a56`](https://github.com/sase-org/sase/commit/08c8a56b365119cc9ba962d9ebd6cf4be5113e12) | feat(instructions): add observed-mode instruction delivery verifier | [sase-1gu.2](sase-1gu.2.md) | 2026-10-05 17:18:38 EDT |
| sase | [`336d754`](https://github.com/sase-org/sase/commit/336d754b4c48534acbeb2824541293481ac50a7c) | feat(instructions): root-only final declaration with helper-return contract | [sase-1gu.5](sase-1gu.5.md) | 2026-10-06 08:02:38 EDT |
| sase | [`9e4b976`](https://github.com/sase-org/sase/commit/9e4b9767d29f77cb7e1d67e4f67ac133b923b286) | feat(instructions): land E1 scoreboard fixes and stopgaps | [sase-1gu](README.md) | 2026-10-06 12:07:34 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1gu.2][1] | epic context | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.2/README.md

<!-- sase:referenced-by:end -->
