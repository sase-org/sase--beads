# Bead: sase-1h3 — E2: Instruction bundles in shadow mode (memory-built instruction migration)

[Bead Pages](../README.md) / sase-1h3

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0xc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0xc.md) · **Assignee:** `sase-1h3.land`
**Created:** 2026-10-06 12:43:24 EDT · **Closed:** 2026-10-06 18:09:16 EDT
**Plan:** [202610/e2\_instruction\_bundles\_shadow\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_instruction_bundles_shadow_mode.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/e2_instruction_bundles_shadow_mode.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/e2_instruction_bundles_shadow_mode.md

<!-- sase:links:end -->

## Description

Every root provider invocation renders the memory-built instruction bundle it would receive and records it with a sase-core-validated instruction manifest, without delivering it; a preview command, legacy parity checks, and scoreboard coverage prove the bundle matches today's files with the contract exactly once, so E3 can switch delivery on a proven renderer.

## Notes

[2026-10-06T21:45:29Z · sase-1h3.7] E2 acceptance record: render/parity/latency/budget evidence with declared pre-landing gaps

🔒 e2\_acceptance\_record.md

[2026-10-06T21:45:41Z · sase-1h3.7] E2 coverage JSON since hook landing: zero manifests pre-landing, zero errors

🔒 e2\_coverage\_empty.json

[2026-10-06T21:45:52Z · sase-1h3.7] E2 instruction budget baseline matrix for E7 ratchet

🔒 instructions\_budget\_baseline.json

[2026-10-06T22:09:16Z · sase-1h3.land] Land verified at origin/master 66d598d198. (1) All 7 phases closed with notes addressed; the six phase commits (ed2a8f78ad memory-units, ec6ffa33a8 manifest-wire, 22ea0cf4db compiler, 620e5310d4 invocation-hook, 8e4543bd43 render-cli, 66d598d198 scoreboard) are on origin/master. The sase-core pin fa390362 (instruction_manifest wire+binding) is the tip of sase-core origin/master. Code review: all three root provider.invoke sites route through invoke_with_instructions (fail-open, O_EXCL NN sequencing, env restore, flag-off passthrough); the architecture test plus 14 route tests cover ordinary/recovery/repair/fallback/no-artifacts/flag-off/compiler-failure. Re-ran from the workspace venv: codex vs grok render differ only in the provider section with equal common_digest 04ffcad9; root/helper/interactive/export overlays correct (decl 1/0/0/0, helper marker 0/1/0/0, export has no home.* included); repeat renders cmp-equal; render -p passes with tree unchanged; warm render 31-34 ms (cache hit); flag instruction_shadow_render is a sunset flag, on, with flag bead sase-1h4; memory init --check clean; doctor -D -C instructions includes instructions.coverage (SKIP, no manifests yet); verify -c runs; tests/instructions 106 passed plus the slow p95 latency test. sase tool run check b9aee6573a40: verdict no_new_failures (only 2 KNOWN symvision items). (2) Integration: the only non-epic commits since start (f84ba7223e pager copy, 9fc571b221 TUI load gauge) touch no instruction, provider-invoke, or memory code, so nothing to integrate. Declared gap: live N/N coverage cannot be observed yet because the installed sase is an editable install of the primary checkout, which is still behind origin by the 4 E2 commits pending auto-sync. The 7-day shadow readout is tracked by flag bead sase-1h4 and the plan's watch metrics. (3) Follow-ups: symvision _runs (proposed by .1/.3/.4/.6/.7) was root-caused to the cross-file import of the private module sase.instructions._runs from E1 08c8a56b36 (not the two reported files) and filed as new task sase-1h6 (ci, small). The registry pending-claim flake (.2) is a duplicate of sase-1em (+1). The two completion host-store test leaks (.6 note #2) duplicate sase-14o (+1). No proposals declined. No epic-symbol entries.

## Attachments

- 🔒 e2\_acceptance\_record.md · text/markdown · 5.88379 KiB (private attachment)
- 🔒 e2\_coverage\_empty.json · application/json · 49.6592 KiB (private attachment)
- 🔒 instructions\_budget\_baseline.json · application/json · 61.8105 KiB (private attachment)

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1h3.1](sase-1h3.1.md) | Legacy instruction renderer exposes structured, cwd-free memory units | ✓ closed | medium | 2026-10-06 | 1 | 1 |
| [sase-1h3.2](sase-1h3.2.md) | Instruction manifest wire schema in sase-core, binding, adapter, and pin move | ✓ closed | medium | 2026-10-06 | 1 | 2 |
| [sase-1h3.3](sase-1h3.3.md) | Python instruction compiler: layers, overlays, facts, manifest assembly, render cache | ✓ closed | medium | 2026-10-06 | 1 | 1 |
| [sase-1h3.4](sase-1h3.4.md) | \`sase instructions render\` preview and legacy parity checks | ✓ closed | medium | 2026-10-06 | 1 | 1 |
| [sase-1h3.5](sase-1h3.5.md) | Shadow render at every root provider invocation, behind one boundary | ✓ closed | medium | 2026-10-06 | 1 | 1 |
| [sase-1h3.6](sase-1h3.6.md) | Scoreboard manifest coverage and intended-vs-observed section diff | ✓ closed | medium | 2026-10-06 | 1 | 1 |
| [sase-1h3.7](sase-1h3.7.md) | Live coverage, parity, latency, budget baseline, and acceptance record | ✓ closed | small | 2026-10-06 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1h3: E2: Instruction bundles in shadow mode (memory-built instruction migration) [closed]"]
    n1["sase-1h3.1: Legacy instruction renderer exposes structured, cwd-free memory units [closed]"]
    n2["sase-1h3.2: Instruction manifest wire schema in sase-core, binding, adapter, and pin move [closed]"]
    n3["sase-1h3.3: Python instruction compiler: layers, overlays, facts, manifest assembly, render cache [closed]"]
    n4["sase-1h3.4: `sase instructions render` preview and legacy parity checks [closed]"]
    n5["sase-1h3.5: Shadow render at every root provider invocation, behind one boundary [closed]"]
    n6["sase-1h3.6: Scoreboard manifest coverage and intended-vs-observed section diff [closed]"]
    n7["sase-1h3.7: Live coverage, parity, latency, budget baseline, and acceptance record [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n3
    n2 -.-> n3
    n3 -.-> n4
    n3 -.-> n5
    n4 -.-> n7
    n5 -.-> n6
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h3.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h3.1.md) | [sase-1h3.1](sase-1h3.1.md) | 1 |
| [bbugyi200.athena.sase-1h3.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h3.2.md) | [sase-1h3.2](sase-1h3.2.md) | 2 |
| [bbugyi200.athena.sase-1h3.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h3.3.md) | [sase-1h3.3](sase-1h3.3.md) | 1 |
| [bbugyi200.athena.sase-1h3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h3.4/README.md) | [sase-1h3.4](sase-1h3.4.md) | 1 |
| [bbugyi200.athena.sase-1h3.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h3.5.md) | [sase-1h3.5](sase-1h3.5.md) | 1 |
| [bbugyi200.athena.sase-1h3.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h3.6/README.md) | [sase-1h3.6](sase-1h3.6.md) | 1 |
| [bbugyi200.athena.sase-1h3.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h3.7/README.md) | [sase-1h3.7](sase-1h3.7.md) | 0 |
| [bbugyi200.athena.sase-1h3.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h3.land/README.md) | [sase-1h3](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ed2a8f7`](https://github.com/sase-org/sase/commit/ed2a8f78ad273cf6dccb40b5c041e77e2f70976a) | feat(instructions): expose structured cwd-free memory units for legacy renderer | [sase-1h3.1](sase-1h3.1.md) | 2026-10-06 13:41:54 EDT |
| sase-core | [`sase-core@fa39036`](https://github.com/sase-org/sase-core/commit/fa390362a556fe156701ee6bdf505411d4f0f7c5) | feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2) | [sase-1h3.2](sase-1h3.2.md) | 2026-10-06 14:15:22 EDT |
| sase | [`ec6ffa3`](https://github.com/sase-org/sase/commit/ec6ffa33a8019ccc4c7121199fb707774796682b) | feat(instructions): manifest-wire sase adapter, parity fixture, and docs (sase-1h3.2) | [sase-1h3.2](sase-1h3.2.md) | 2026-10-06 14:19:33 EDT |
| sase | [`22ea0cf`](https://github.com/sase-org/sase/commit/22ea0cf4db9b383bb2d907f31f0884cc0de3a6e9) | feat(instructions): add instruction bundle compiler with cache and directives | [sase-1h3.3](sase-1h3.3.md) | 2026-10-06 15:35:31 EDT |
| sase | [`620e531`](https://github.com/sase-org/sase/commit/620e5310d48952dc5994d0eca91d750fd9789785) | feat(instructions): shadow render bundles at provider invoke boundary | [sase-1h3.5](sase-1h3.5.md) | 2026-10-06 16:31:23 EDT |
| sase | [`8e4543b`](https://github.com/sase-org/sase/commit/8e4543bd43a34c429782df8ca441f2438335ce11) | feat(instructions): add render CLI with parity preview and section filtering | [sase-1h3.4](sase-1h3.4.md) | 2026-10-06 17:09:44 EDT |
| sase | [`66d598d`](https://github.com/sase-org/sase/commit/66d598d1987bdee617cb01e8abe3664dbc0a911d) | feat(instructions): add scoreboard coverage, verify diff and doctor check | [sase-1h3.6](sase-1h3.6.md) | 2026-10-06 17:24:45 EDT |
| sase--plans | [`sase--plans@c19e832`](https://github.com/sase-org/sase--plans/commit/c19e8323a5b810aa7e31cb9dcb8829c72b465d1c) | chore(plans): mark E2 instruction bundles shadow-mode plan done (sase-1h3) | [sase-1h3](README.md) | 2026-10-06 18:10:41 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h3.6][1] | Need epic children status | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h3.6/README.md

<!-- sase:referenced-by:end -->
