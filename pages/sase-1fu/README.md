# Bead: sase-1fu — Restore visible Muse reply streaming without fragmenting replies

[Bead Pages](../README.md) / sase-1fu

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vt](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vt.md) · **Assignee:** `sase-1fu.land`
**Created:** 2026-10-03 15:03:50 EDT · **Closed:** 2026-10-04 09:43:48 EDT
**Plan:** [202610/muse\_reply\_streaming.md](https://github.com/sase-org/sase--plans/blob/main/202610/muse_reply_streaming.md)

## Description

Muse reply deltas reach the selected agent's visible Reply card during generation, before terminal completion, with intact text, responsive navigation, and correctly framed interactive console output.

## Notes

[2026-10-04T13:34:24Z · sase-1fu.land] Landing triage of PROPOSED FOLLOW-UP notes, before the empty-placeholder tale.

sase-1fu.2 note #1 (macro terminology, tests/xprompt): declined as a new task. The directory is gone in this workspace. The same failure is already DISCOVERED ISSUE note #2 on in-progress epic sase-1eq, whose guard rglobs the working tree and trips on ignored leftover directories. Corroborated on sase-1eq from this landing.

sase-1fu.3 note #1 (five unused-public symbols in src/sase/axe/runner_kill_provenance.py): declined as a new task. The file is unchanged by this epic. The same symbols are already DISCOVERED ISSUE note #2 on in-progress epic sase-1c1. ToolRun 36fe89baea7b23b1af881edd8a1f96af classified all five KNOWN under witness a0f7a0a8506dc6222c50650d47dd4f95. Corroborated on sase-1c1 from this landing. sase-1ay is a different symbol set.

sase-1fu.4 note #1 (test_prompt_tab_focus_steal.py, five FrontmatterPanel.on_mount NoMatches(#frontmatter-raw) teardown errors under pytest -n 4, passed alone per sase-1fu.1): filed ready flake task sase-1fy, size large, linked to sase-1fu.4, sase-1fu.1, sase-pe, and sase-j7. Not epic-caused: frontmatter_panel.py is outside this epic. sase-pe is a different closed node. sase-j7 does not name this node and the failure is not confirmed to be process-global state, so it was not left only as an epic note.

sase-1fu.4 note #2 (repeat the real long Muse reply capture after quota reset): declined. Installed Muse 1.4.2-R4684.1 returned API 429 until 2026-10-05T00:00:00Z. The mounted production-parser test already proves transport-to-paint. A one-shot capture after the quota reset is not a product defect.

Muse comments that say a terminal event never returns deltas were not a child follow-up. Declined. A textless terminal still returns the deltas, which is the salvage contract, and _resolve_muse_content already says so.

Empty-snapshot placeholder clobber is caused by this epic and is the remaining tale: sase_plan_live_reply_empty_placeholder.md. sase bead epic-symbols sase-1fu listed no entries at triage. sase-1fu has no parent_id.

[2026-10-04T13:43:48Z · sase-1fu.land] Verified phases sase-1fu.1 through sase-1fu.4 are closed and their code is on master: selected Reply follow in _live_reply_follow.py, bounded JSONL reads in _subprocess_stream.py, Rich FileProxy framing in _subprocess_artifacts.py, the mounted gated-Muse test, and the docs/llms.md streaming paragraph. This tale stops empty snapshots from replacing first-paint reply copy, and docs/ace.md matches that behavior; focused pytest result: 5 passed in 10.10s. Follow-ups already triaged before this tale: sase-1fu.2's tests/xprompt terminology failure is the ignored-directory scan recorded on epic sase-1eq (corroborated again at landing; no new task); sase-1fu.3's five runner_kill_provenance.py Symvision symbols are the pre-existing set on epic sase-1c1 (corroborated again; no new task); sase-1fu.4's prompt-tab focus failures are flake task sase-1fy, linked to the proposing phase. The real Muse capture after API 429 was declined: installed Muse 1.4.2-R4684.1 was quota-blocked until 2026-10-05T00:00:00Z, and the mounted production parser proves transport-to-paint. Muse comments saying a terminal event never returns deltas were declined: a textless terminal still returns deltas, which is the salvage contract, and _resolve_muse_content already says so. sase bead epic-symbols sase-1fu returned: No --epic-symbol entries for sase-1fu. No parent bead.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1fu.1](sase-1fu.1.md) | Refresh the selected live Reply card | ✓ closed | medium | 2026-10-03 | 1 | 1 |
| [sase-1fu.2](sase-1fu.2.md) | Drain provider JSONL promptly and preserve UTF-8 | ✓ closed | medium | 2026-10-03 | 1 | 1 |
| [sase-1fu.3](sase-1fu.3.md) | Preserve complete console lines under the provider timer | ✓ closed | small | 2026-10-03 | 1 | 1 |
| [sase-1fu.4](sase-1fu.4.md) | Verify the complete Muse streaming path and document its behavior | ✓ closed | medium | 2026-10-03 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1fu: Restore visible Muse reply streaming without fragmenting replies [closed]"]
    n1["sase-1fu.1: Refresh the selected live Reply card [closed]"]
    n2["sase-1fu.2: Drain provider JSONL promptly and preserve UTF-8 [closed]"]
    n3["sase-1fu.3: Preserve complete console lines under the provider timer [closed]"]
    n4["sase-1fu.4: Verify the complete Muse streaming path and document its behavior [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n4
    n2 -.-> n4
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1fu.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fu.1/README.md) | [sase-1fu.1](sase-1fu.1.md) | 1 |
| [bbugyi200.athena.sase-1fu.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fu.2/README.md) | [sase-1fu.2](sase-1fu.2.md) | 1 |
| [bbugyi200.athena.sase-1fu.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1fu.3.md) | [sase-1fu.3](sase-1fu.3.md) | 1 |
| [bbugyi200.athena.sase-1fu.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1fu.4.md) | [sase-1fu.4](sase-1fu.4.md) | 0 |
| [bbugyi200.athena.sase-1fu.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1fu.land.md) | [sase-1fu](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ca1ffac`](https://github.com/sase-org/sase/commit/ca1ffac8e3f3debe5a44045bb9ceccb16c5bc839) | fix(muse): preserve streamed reply framing | [sase-1fu.3](sase-1fu.3.md) | 2026-10-03 15:45:04 EDT |
| sase | [`3929830`](https://github.com/sase-org/sase/commit/392983091d82799747bc1222ac7c0f9151167c5a) | fix(llm-provider): drain JSONL streams incrementally | [sase-1fu.2](sase-1fu.2.md) | 2026-10-03 16:21:13 EDT |
| sase | [`2307212`](https://github.com/sase-org/sase/commit/2307212bcd88bcf2b5773cf93d73d9be3f84eb0d) | feat(ace): follow selected live agent replies | [sase-1fu.1](sase-1fu.1.md) | 2026-10-03 18:05:12 EDT |
| sase | [`e1fa79d`](https://github.com/sase-org/sase/commit/e1fa79db96edf20ee4f5854d9fa5cd4eefa30bba) | fix(ace): preserve empty live reply placeholder | [sase-1fu](README.md) | 2026-10-04 11:04:37 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1fu.4--5][1] | Verify the parent epic remains open after closing only phase four | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1fu.4.md

<!-- sase:referenced-by:end -->
