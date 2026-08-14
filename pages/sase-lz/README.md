# Bead: sase-lz — Full model-pool support in the Models panel alias editor

[Bead Pages](../README.md) / sase-lz

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.014](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.014.md) · **Assignee:** `sase-lz.land`
**Created:** 2026-08-14 10:49:15 EDT · **Closed:** 2026-08-14 13:08:34 EDT
**Plan:** [202608/models\_panel\_pool\_authoring.md](https://github.com/sase-org/sase--plans/blob/main/202608/models_panel_pool_authoring.md)

## Description

Model alias definitions overridden from the ACE Models panel can specify round-robin pools and ordered fallback chains through a guided, keyboard-driven builder instead of hand-typed free text, the temporary-override path refuses selector expressions instead of silently persisting a corrupted single target, and the docs describe the shipped behavior.

## Notes

[2026-08-14T17:08:34Z · sase-lz.land] Implemented selector-builder custom input validation for typed selector expressions, added regression coverage for typed pool/fallback and malformed mixed selector input, corrected ACE docs wording, ran focused non-visual tests (128 passed), ran just test-visual (unrelated agents_retry_e2e_running_fallback_120x40 snapshot mismatch corroborated on sase-dc), and ran just check (passed).

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-lz.1](sase-lz.1.md) | Reject selector expressions in the temporary-override path | ✓ closed | small | 2026-08-14 | 1 | 1 |
| [sase-lz.2](sase-lz.2.md) | Parse-based selector detection and prefilled custom input | ✓ closed | small | 2026-08-14 | 1 | 1 |
| [sase-lz.3](sase-lz.3.md) | Guided pool and fallback builder modal | ✓ closed | medium | 2026-08-14 | 1 | 1 |
| [sase-lz.4](sase-lz.4.md) | Documentation sync for selector authoring | ✓ closed | small | 2026-08-14 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-lz: Full model-pool support in the Models panel alias editor [closed]"]
    n1["sase-lz.1: Reject selector expressions in the temporary-override path [closed]"]
    n2["sase-lz.2: Parse-based selector detection and prefilled custom input [closed]"]
    n3["sase-lz.3: Guided pool and fallback builder modal [closed]"]
    n4["sase-lz.4: Documentation sync for selector authoring [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lz.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lz.1/README.md) | [sase-lz.1](sase-lz.1.md) | 1 |
| [bbugyi200.athena.sase-lz.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lz.2/README.md) | [sase-lz.2](sase-lz.2.md) | 1 |
| [bbugyi200.athena.sase-lz.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lz.3/README.md) | [sase-lz.3](sase-lz.3.md) | 1 |
| [bbugyi200.athena.sase-lz.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lz.4/README.md) | [sase-lz.4](sase-lz.4.md) | 1 |
| [bbugyi200.athena.sase-lz.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-lz.land.md) | [sase-lz](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`adea6b1`](https://github.com/sase-org/sase/commit/adea6b1dfcc250fe7cfc8f4e756d105338f4e2da) | fix(ace): reject selector expressions in the temporary-override picker | [sase-lz.1](sase-lz.1.md) | 2026-08-14 11:01:28 EDT |
| sase | [`a605d5c`](https://github.com/sase-org/sase/commit/a605d5c09e4e43007d8a019c34aaab233d078fac) | refactor(ace): parse selector expressions instead of sniffing substrings in alias Edit | [sase-lz.2](sase-lz.2.md) | 2026-08-14 11:43:11 EDT |
| sase | [`877465a`](https://github.com/sase-org/sase/commit/877465a5ad4478e9fdc068c3668be928f72daf66) | feat(ace): add guided selector builder modal for model pools | [sase-lz.3](sase-lz.3.md) | 2026-08-14 12:27:54 EDT |
| sase | [`4d5598e`](https://github.com/sase-org/sase/commit/4d5598eaf4fffd6ba3c4f5904e95f7dbec4a9749) | docs(ace): correct selector authoring docs for Edit/Override and builder | [sase-lz.4](sase-lz.4.md) | 2026-08-14 12:43:46 EDT |
| sase | [`6ee3347`](https://github.com/sase-org/sase/commit/6ee334708e366715046bc7f871ca66f234794126) | fix(ace): reject typed selectors in builder members | [sase-lz](README.md) | 2026-08-14 13:09:42 EDT |
