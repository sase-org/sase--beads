# Bead: sase-az — Unified "Copy as…" palette

[Bead Pages](../README.md) / sase-az

**Status:** ✓ closed · **Resolution:** done · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-az.land`
**Created:** 2026-07-29 23:12:27 UTC · **Closed:** 2026-07-30 02:23:20 UTC
**Plan:** [202607/copy\_as\_palette.md](https://github.com/sase-org/sase--plans/blob/main/202607/copy_as_palette.md)

## Description

Pressing the copy prefix anywhere in ACE opens one beautiful, discoverable "Copy as…" palette: every existing copy target keeps its key as an accelerator, new Markdown-link and metadata-JSON representations join the reference/path/contents targets, marked sets pluralize into paste-ready forms, the artifact-files modal gains the full file-kind representation set, and every copy in the TUI rides one delivery seam that pairs OSC 52 with the subprocess adapter, names exactly what was copied, and leaves the generated text selectable when no transport works.

## Notes

[2026-07-30T02:23:20Z · sase-az.land] Re-verified phase commits 77ec8798e (delivery), cf844c3e5 (registry/representations), 3da9140b4 (palette), and 132bd79c7 (artifact-files modal), plus all four child beads closed/done. Completed Files integration with the full warm-only palette vocabulary, compatibility-preserving %L link and %j JSON keys, dispatcher-collision precedence, shared link/JSON representation routing, dead JSON-branch cleanup, and mixed text/binary partial counts. Validation: 159 focused clipboard/palette/files/help tests passed; direct clipboard sweep finds only actions/clipboard/_delivery.py; just check passed formatting, keep-sorted, Ruff, mypy, pyscripts, changelog, Symvision, and toobig before the known plans-sidecar prompt/reverse-link validator stopped on 8 unrelated errors; full just test reached 24,104 passed and 7 skipped with one unrelated gate-debug ordering race that passed in isolation and one intentional Help golden delta; after inspection/update, the complete visual lane passed 388 with 1 skip.

[2026-07-30T02:25:31Z · sase-az.land] Post-close landing verification: just symvision is clean with no stale epic exemptions or dead-symbol cleanup required; the complete visual suite passes 388 tests with 1 skip after inspecting and accepting the intentional Help-row scrollbar delta; the linked epic plan now has status: done as its only sidecar diff. Final-state just check again passes all formatting/lint/Symvision/toobig stages and stops only on the same 8 unrelated plans-sidecar prompt/reverse-link validation errors.

[2026-07-30T02:26:41Z · sase-az.land] Finalizer verification: 159 focused tests passed; visual suite 388 passed and 1 skipped; post-close Symvision clean; just check passed all code-quality lanes and stopped only on eight unrelated pre-existing plans-sidecar link errors.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-az.1](sase-az.1.md) | One clipboard delivery seam with OSC 52 and a selectable fallback | ✓ closed | medium | 0 | 0 |
| [sase-az.2](sase-az.2.md) | Representation targets and one copy-target registry | ✓ closed | medium | 0 | 0 |
| [sase-az.3](sase-az.3.md) | The Copy-as palette modal | ✓ closed | large | 0 | 0 |
| [sase-az.4](sase-az.4.md) | File-kind representations in the artifact-files modal | ✓ closed | medium | 0 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-az: Unified \"Copy as…\" palette [closed]"]
    n1["sase-az.1: One clipboard delivery seam with OSC 52 and a selectable fallback [closed]"]
    n2["sase-az.2: Representation targets and one copy-target registry [closed]"]
    n3["sase-az.3: The Copy-as palette modal [closed]"]
    n4["sase-az.4: File-kind representations in the artifact-files modal [closed]"]
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
| bbugyi200.athena.sase-az.land--code | [sase-az](README.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a8eb1ed`](https://github.com/sase-org/sase--plans/commit/a8eb1ed00944a60f8c107671c43ad74961feb3fd) | docs(plans): mark copy-as palette complete | [sase-az](README.md) | 2026-07-30 02:29:17 |
