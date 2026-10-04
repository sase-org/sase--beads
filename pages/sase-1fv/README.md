# Bead: sase-1fv — Edit existing macros and snippets from the Ctrl+G x / Ctrl+G t location picker

[Bead Pages](../README.md) / sase-1fv

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0w7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0w7.md) · **Assignee:** `sase-1fv.land`
**Created:** 2026-10-04 06:32:58 EDT
**Plan:** [202610/existing\_macro\_snippet\_editing.md](https://github.com/sase-org/sase--plans/blob/main/202610/existing_macro_snippet_editing.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/existing_macro_snippet_editing.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/existing_macro_snippet_editing.md

<!-- sase:links:end -->

## Description

From the prompt input, `Ctrl+G x` / `Ctrl+G t` (and `gx` / `gt`) offer an `e` (existing) row in the location picker that opens a beautiful fuzzy finder over every macro or snippet definition in every supported file. Picking one opens it in the existing mini-macro / snippet pane for in-place editing, or starts a guided override when the definition is read-only. Every path that would redefine an existing macro or snippet, whatever destination the user chose, shows an accurate warning that names where the name already lives and whether the new copy will take effect.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1fv.1](sase-1fv.1.md) | Accurate macro redefinition analysis and warnings | ✓ closed | medium | 2026-10-04 | 1 | 1 |
| [sase-1fv.2](sase-1fv.2.md) | Provenance-accurate snippet redefinition analysis and warnings | ✓ closed | medium | 2026-10-04 | 1 | 1 |
| [sase-1fv.3](sase-1fv.3.md) | Existing row and override mode in the save-location picker | ✓ closed | medium | 2026-10-04 | 1 | 1 |
| [sase-1fv.4](sase-1fv.4.md) | Existing-definition fuzzy finder modal | ✓ closed | medium | 2026-10-04 | 1 | 1 |
| [sase-1fv.5](sase-1fv.5.md) | Wire the existing path into the mini-macro flow | ✓ closed | medium | 2026-10-04 | 1 | 1 |
| [sase-1fv.6](sase-1fv.6.md) | Wire the existing path into the snippet flow | ◐ in_progress | medium | 2026-10-04 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1fv: Edit existing macros and snippets from the Ctrl+G x / Ctrl+G t location picker [in_progress]"]
    n1["sase-1fv.1: Accurate macro redefinition analysis and warnings [closed]"]
    n2["sase-1fv.2: Provenance-accurate snippet redefinition analysis and warnings [closed]"]
    n3["sase-1fv.3: Existing row and override mode in the save-location picker [closed]"]
    n4["sase-1fv.4: Existing-definition fuzzy finder modal [closed]"]
    n5["sase-1fv.5: Wire the existing path into the mini-macro flow [closed]"]
    n6["sase-1fv.6: Wire the existing path into the snippet flow [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n4
    n2 -.-> n4
    n3 -.-> n5
    n4 -.-> n5
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1fv.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fv.1/README.md) | [sase-1fv.1](sase-1fv.1.md) | 1 |
| [bbugyi200.athena.sase-1fv.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1fv.2.md) | [sase-1fv.2](sase-1fv.2.md) | 1 |
| [bbugyi200.athena.sase-1fv.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fv.3/README.md) | [sase-1fv.3](sase-1fv.3.md) | 1 |
| [bbugyi200.athena.sase-1fv.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fv.4/README.md) | [sase-1fv.4](sase-1fv.4.md) | 1 |
| [bbugyi200.athena.sase-1fv.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1fv.5.md) | [sase-1fv.5](sase-1fv.5.md) | 1 |
| [bbugyi200.athena.sase-1fv.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fv.6/README.md) | [sase-1fv.6](sase-1fv.6.md) | 0 |
| [bbugyi200.athena.sase-1fv.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fv.land/README.md) | [sase-1fv](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a963c0d`](https://github.com/sase-org/sase/commit/a963c0d3da2572a0c623a503286160e979d27db5) | feat(ace): warn accurately on mini-macro redefinitions | [sase-1fv.1](sase-1fv.1.md) | 2026-10-04 07:33:32 EDT |
| sase | [`763cc9f`](https://github.com/sase-org/sase/commit/763cc9fca334c8d2009789f368ef01aa9f40debe) | feat(tui): add Existing row and override mode to the save-location picker | [sase-1fv.3](sase-1fv.3.md) | 2026-10-04 07:41:30 EDT |
| sase | [`2608a24`](https://github.com/sase-org/sase/commit/2608a2439e1dd058d86ac1650abb91c8d2b6c3c9) | feat(snippet): replace inverted collision with provenance redefinition | [sase-1fv.2](sase-1fv.2.md) | 2026-10-04 08:41:50 EDT |
| sase | [`4d38e39`](https://github.com/sase-org/sase/commit/4d38e39702e9871be0b0ecfe8d121de6d3afbc82) | feat(tui): add existing-definition finder modal and entry model | [sase-1fv.4](sase-1fv.4.md) | 2026-10-04 10:44:11 EDT |
| sase | [`d6e856f`](https://github.com/sase-org/sase/commit/d6e856f4d9469fa2fb7cd4b9cc055d44abbcb5a9) | feat(tui): wire existing-definition path into mini-macro flow | [sase-1fv.5](sase-1fv.5.md) | 2026-10-04 11:53:53 EDT |
