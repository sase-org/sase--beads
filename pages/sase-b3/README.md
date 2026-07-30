# Bead: sase-b3 — Fuzzy artifact-reference completion with matched-run highlighting

[Bead Pages](../README.md) / sase-b3

**Status:** ◐ in_progress · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b3.land`
**Created:** 2026-07-30 08:18:13 UTC
**Plan:** [202607/fuzzy\_artifact\_ref\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202607/fuzzy_artifact_ref_completion.md)

## Description

Typing an artifact reference finds the file by any memorable fragment of its path or title in both the ACE prompt input and external editors, every candidate a reference can name is actually reachable, and every row shows exactly which characters the query matched.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-b3.1](sase-b3.1.md) | Canonical fuzzy matcher in sase-core | ✓ closed | medium | 0 | 0 |
| [sase-b3.2](sase-b3.2.md) | Bundled document discovery depth | ✓ closed | small | 0 | 0 |
| [sase-b3.3](sase-b3.3.md) | Fuzzy at-reference menu and match runs on the wire | ✓ closed | medium | 0 | 0 |
| [sase-b3.4](sase-b3.4.md) | Zero-marshalling payload index binding | ✓ closed | medium | 0 | 0 |
| [sase-b3.5](sase-b3.5.md) | Server-side fuzzy completion for editors | ✓ closed | small | 0 | 0 |
| [sase-b3.6](sase-b3.6.md) | Reachable, bounded, per-kind payload catalogs | ✓ closed | medium | 0 | 0 |
| [sase-b3.7](sase-b3.7.md) | Prompt-input rendering of paths and matched runs | ✓ closed | medium | 0 | 0 |
| [sase-b3.8](sase-b3.8.md) | Ctrl+R finder on the shared matcher | ✓ closed | small | 0 | 0 |
| [sase-b3.9](sase-b3.9.md) | Docs, core floor bump, and end-to-end verification | ✓ closed | small | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-b3: Fuzzy artifact-reference completion with matched-run highlighting [in_progress]"]
    n1["sase-b3.1: Canonical fuzzy matcher in sase-core [closed]"]
    n2["sase-b3.10: Editor parity for fuzzy artifact-reference completion [in_progress]"]
    n3["sase-b3.10.1: Fuzzy ranking in the agent and indexed-file collectors [closed]"]
    n4["sase-b3.10.2: Real titles on editor payload rows [closed]"]
    n5["sase-b3.10.3: Editor payload reach and disclosed truncation [closed]"]
    n6["sase-b3.10.4: Docs, release, and epic landing [closed]"]
    n7["sase-b3.2: Bundled document discovery depth [closed]"]
    n8["sase-b3.3: Fuzzy at-reference menu and match runs on the wire [closed]"]
    n9["sase-b3.4: Zero-marshalling payload index binding [closed]"]
    n10["sase-b3.5: Server-side fuzzy completion for editors [closed]"]
    n11["sase-b3.6: Reachable, bounded, per-kind payload catalogs [closed]"]
    n12["sase-b3.7: Prompt-input rendering of paths and matched runs [closed]"]
    n13["sase-b3.8: Ctrl+R finder on the shared matcher [closed]"]
    n14["sase-b3.9: Docs, core floor bump, and end-to-end verification [closed]"]
    n0 --> n1
    n0 --> n2
    n2 --> n3
    n2 --> n4
    n2 --> n5
    n2 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n0 --> n11
    n0 --> n12
    n0 --> n13
    n0 --> n14
    n1 -.-> n8
    n3 -.-> n5
    n4 -.-> n5
    n5 -.-> n6
    n7 -.-> n11
    n8 -.-> n9
    n8 -.-> n10
    n9 -.-> n11
    n10 -.-> n14
    n11 -.-> n12
    n12 -.-> n13
    n13 -.-> n14
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-b3.10.4 | [sase-b3.10.4](sase-b3.10.4.md) | 1 |
| bbugyi200.athena.sase-b3.9 | [sase-b3.9](sase-b3.9.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`2e0f6a0`](https://github.com/sase-org/sase-nvim/commit/2e0f6a08a437b171e69e15c17a5300b75c37c395) | docs: document fuzzy artifact reference completion | [sase-b3.9](sase-b3.9.md) | 2026-07-30 10:35:51 |
| [`caf0d51`](https://github.com/sase-org/sase-nvim/commit/caf0d51d5da86980f68a852a69d83ef01720ae8a) | test: cover fuzzy agent-reference completion end to end | [sase-b3.10.4](sase-b3.10.4.md) | 2026-07-30 12:00:58 |
