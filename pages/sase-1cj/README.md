# Bead: sase-1cj — Next-word prediction chains in the prompt input

[Bead Pages](../README.md) / sase-1cj

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.2x` · **Assignee:** `sase-1cj.land`
**Created:** 2026-09-29 07:14:24 EDT
**Plan:** [202609/prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_next_word_prediction.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/prompt_next_word_prediction.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/prompt_next_word_prediction.md

<!-- sase:links:end -->

## Description

In the prompt input, pressing Ctrl+T repeatedly first completes the current word, then previews and accepts confident guesses for the next words. The guesses come from the user's own typed prompt history (weighted toward the same project, with the cross-machine prompt archive as a low-weight source) and appear as dim inline ghost text before anything is inserted. Predictions come from the Rust core in well under a millisecond and never block typing.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1cj.1](sase-1cj.1.md) | Ctrl+T accepts the highlighted word-menu row | ✓ closed | small | 2026-09-29 | 1 | 0 |
| [sase-1cj.10](sase-1cj.10.md) | Cross-machine prompt archive as a low-weight source | ◐ in_progress | medium | 2026-09-29 | 1 | 0 |
| [sase-1cj.11](sase-1cj.11.md) | Opt-in automatic ghost at word boundaries | ◐ in_progress | small | 2026-09-29 | 1 | 0 |
| [sase-1cj.2](sase-1cj.2.md) | Record typed vs generated origin on prompt history rows | ✓ closed | medium | 2026-09-29 | 1 | 1 |
| [sase-1cj.3](sase-1cj.3.md) | Rust prompt\_prediction engine in sase-core | ◐ in_progress | medium | 2026-09-29 | 1 | 0 |
| [sase-1cj.4](sase-1cj.4.md) | PyO3 handles, Python facade, and pin for prompt prediction | ◐ in_progress | small | 2026-09-29 | 1 | 0 |
| [sase-1cj.5](sase-1cj.5.md) | Off-thread prediction corpus warm cache for the TUI | ◐ in_progress | medium | 2026-09-29 | 1 | 0 |
| [sase-1cj.6](sase-1cj.6.md) | Ghost-text next-word chain on Ctrl+T | ◐ in_progress | medium | 2026-09-29 | 1 | 0 |
| [sase-1cj.7](sase-1cj.7.md) | Explicit next\_word menu and word-end fallback | ◐ in_progress | medium | 2026-09-29 | 1 | 0 |
| [sase-1cj.8](sase-1cj.8.md) | Context-aware current-word ranking | ◐ in_progress | medium | 2026-09-29 | 1 | 0 |
| [sase-1cj.9](sase-1cj.9.md) | Prequential replay harness and preset calibration | ◐ in_progress | medium | 2026-09-29 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1cj: Next-word prediction chains in the prompt input [in_progress]"]
    n1["sase-1cj.1: Ctrl+T accepts the highlighted word-menu row [closed]"]
    n2["sase-1cj.10: Cross-machine prompt archive as a low-weight source [in_progress]"]
    n3["sase-1cj.11: Opt-in automatic ghost at word boundaries [in_progress]"]
    n4["sase-1cj.2: Record typed vs generated origin on prompt history rows [closed]"]
    n5["sase-1cj.3: Rust prompt_prediction engine in sase-core [in_progress]"]
    n6["sase-1cj.4: PyO3 handles, Python facade, and pin for prompt prediction [in_progress]"]
    n7["sase-1cj.5: Off-thread prediction corpus warm cache for the TUI [in_progress]"]
    n8["sase-1cj.6: Ghost-text next-word chain on Ctrl+T [in_progress]"]
    n9["sase-1cj.7: Explicit next_word menu and word-end fallback [in_progress]"]
    n10["sase-1cj.8: Context-aware current-word ranking [in_progress]"]
    n11["sase-1cj.9: Prequential replay harness and preset calibration [in_progress]"]
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
    n0 --> n11
    n1 -.-> n8
    n4 -.-> n7
    n5 -.-> n6
    n6 -.-> n7
    n6 -.-> n11
    n7 -.-> n2
    n7 -.-> n8
    n7 -.-> n10
    n7 -.-> n11
    n8 -.-> n9
    n9 -.-> n3
    n9 -.-> n10
    n11 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.1/README.md) | [sase-1cj.1](sase-1cj.1.md) | 0 |
| [bbugyi200.athena.sase-1cj.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.10/README.md) | [sase-1cj.10](sase-1cj.10.md) | 0 |
| [bbugyi200.athena.sase-1cj.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.11/README.md) | [sase-1cj.11](sase-1cj.11.md) | 0 |
| [bbugyi200.athena.sase-1cj.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.2/README.md) | [sase-1cj.2](sase-1cj.2.md) | 1 |
| [bbugyi200.athena.sase-1cj.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.3/README.md) | [sase-1cj.3](sase-1cj.3.md) | 0 |
| [bbugyi200.athena.sase-1cj.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.4/README.md) | [sase-1cj.4](sase-1cj.4.md) | 0 |
| [bbugyi200.athena.sase-1cj.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.5/README.md) | [sase-1cj.5](sase-1cj.5.md) | 0 |
| [bbugyi200.athena.sase-1cj.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.6/README.md) | [sase-1cj.6](sase-1cj.6.md) | 0 |
| [bbugyi200.athena.sase-1cj.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.7/README.md) | [sase-1cj.7](sase-1cj.7.md) | 0 |
| [bbugyi200.athena.sase-1cj.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.8/README.md) | [sase-1cj.8](sase-1cj.8.md) | 0 |
| [bbugyi200.athena.sase-1cj.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.9/README.md) | [sase-1cj.9](sase-1cj.9.md) | 0 |
| [bbugyi200.athena.sase-1cj.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.land/README.md) | [sase-1cj](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eaa4aa4`](https://github.com/sase-org/sase/commit/eaa4aa4aa72d67f27156e22cd7939422e87f4afc) | feat(prompt-history): record typed vs generated origin on prompt rows | [sase-1cj.2](sase-1cj.2.md) | 2026-09-29 07:44:59 EDT |
