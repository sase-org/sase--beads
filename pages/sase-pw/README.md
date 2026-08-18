# Bead: sase-pw — Current project, derived from the VCS xprompt MRU store

[Bead Pages](../README.md) / sase-pw

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.062.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.062.f1.md) · **Assignee:** `sase-pw.land`
**Created:** 2026-08-18 11:30:28 EDT
**Plan:** [202608/current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/current_project.md)

## Description

SASE has one "current project" derived from the VCS xprompt MRU head, shown as a uniquely colored `+<project>` chip in the ACE top bar, and used as the default project filter on every TUI surface that can filter by project.

## Notes

[2026-08-18T17:33:03Z · 06d] DISCOVERED ISSUE: just check lint (symvision) fails on unused public project_accent and project_accent_map in src/sase/ace/tui/project_styles.py. Closed sase-pw.2 landed both symbols for later phases; they still have no non-test caller and no --epic-symbol whitelist. sase-pw.4 (top-bar +project chip) is the intended first consumer. Re-key with --epic-symbol sase-pw.4(project_accent) and --epic-symbol sase-pw.4(project_accent_map), or consume them in sase-pw.4. Unrelated to the in-flight @path bead-CLI tale.

[2026-08-18T17:49:59Z · sase-ps.land] DISCOVERED ISSUE (corroborating the 2026-08-18T17:33:03Z entry from 06d): the sase-ps land agent independently reproduced this on a clean tree at 88d2a1582 with 'just install' already run. 'just symvision' exits 1 with: Unused public functions/classes — project_accent in src/sase/ace/tui/project_styles.py, project_accent_map in src/sase/ace/tui/project_styles.py. Both symbols landed in 129bb631d (closed phase sase-pw.2) and still have no non-test caller; the only callers are tests/ace/tui/test_project_styles.py. The Justfile symvision line carries no --epic-symbol entry for either symbol (its only entries are sase-n4/sase-n4.5). Impact: 'just check'/'just check-full' is red at the symvision gate for every agent on this host until sase-pw.4 consumes them or the Justfile is re-keyed with --epic-symbol "sase-pw.4(project_accent)" and --epic-symbol "sase-pw.4(project_accent_map)". Raised as a PROPOSED FOLLOW-UP by epic phase sase-ps.4; not caused by sase-ps.

[2026-08-18T18:00:09Z · sase-px] DISCOVERED ISSUE: Independently reproduced while closing sase-px (glossary color_system mypy fix). just check passed lint (mypy) then failed lint (symvision) on unused public project_accent and project_accent_map in src/sase/ace/tui/project_styles.py. sase-px does not touch that file. Confirms the 2026-08-18T17:33:03Z and 2026-08-18T17:49:59Z notes: closed sase-pw.2 landed the symbols, sase-pw.4 is the intended consumer, and the Justfile still has no --epic-symbol whitelist for either name.

[2026-08-18T18:56:20Z · 06f] DISCOVERED ISSUE: just check lint (symvision) fails on five stale --epic-symbol entries keyed to closed phase sase-pw.4: CurrentProject, peek_current_project_change_token, project_accent, project_accent_map, resolve_current_project. Reproduced on HEAD c5a0dcf4a while implementing kill-and-edit identity (this tree does not touch Justfile or those symbols). just check passed fmt/ruff/mypy/flags/pyscripts/test-waits/changelog/terminology, then died at _lint-symvision: "bead sase-pw.4 is closed. Remove this stale --epic-symbol entry and clean up the symbol." sase-pw.4 closed at 2026-08-18T18:46:44Z claiming sase bead epic-symbols sase-pw.4 reported no leftovers and that unused project_accent_map was re-keyed to sase-pw.8, but this workspace Justfile still lists all five as sase-pw.4(...). Parent epic sase-pw is still in_progress (open phases .5-.9). Same mid-epic leftover pattern as sase-o7. I did not edit the Justfile.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-pw.1](sase-pw.1.md) | Current-project resolver over the VCS xprompt MRU | ✓ closed | medium | 2026-08-18 | 1 | 1 |
| [sase-pw.2](sase-pw.2.md) | Per-project accent colors | ✓ closed | small | 2026-08-18 | 1 | 1 |
| [sase-pw.3](sase-pw.3.md) | ace.current\_project configuration | ✓ closed | small | 2026-08-18 | 1 | 1 |
| [sase-pw.4](sase-pw.4.md) | Top-bar +project indicator | ✓ closed | medium | 2026-08-18 | 1 | 1 |
| [sase-pw.5](sase-pw.5.md) | Artifacts scope and Stitches startup filter | ✓ closed | medium | 2026-08-18 | 1 | 1 |
| [sase-pw.6](sase-pw.6.md) | Statistics, inventory, Glossary, and the + picker | ◐ in_progress | medium | 2026-08-18 | 1 | 0 |
| [sase-pw.7](sase-pw.7.md) | Agents-tab project scoping | ◐ in_progress | medium | 2026-08-18 | 1 | 0 |
| [sase-pw.8](sase-pw.8.md) | sase project current | ◐ in_progress | small | 2026-08-18 | 1 | 0 |
| [sase-pw.9](sase-pw.9.md) | Visual snapshot, help text, and full verification | ◐ in_progress | small | 2026-08-18 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-pw: Current project, derived from the VCS xprompt MRU store [in_progress]"]
    n1["sase-pw.1: Current-project resolver over the VCS xprompt MRU [closed]"]
    n2["sase-pw.2: Per-project accent colors [closed]"]
    n3["sase-pw.3: ace.current_project configuration [closed]"]
    n4["sase-pw.4: Top-bar +project indicator [closed]"]
    n5["sase-pw.5: Artifacts scope and Stitches startup filter [closed]"]
    n6["sase-pw.6: Statistics, inventory, Glossary, and the + picker [in_progress]"]
    n7["sase-pw.7: Agents-tab project scoping [in_progress]"]
    n8["sase-pw.8: sase project current [in_progress]"]
    n9["sase-pw.9: Visual snapshot, help text, and full verification [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n1 -.-> n4
    n1 -.-> n5
    n1 -.-> n6
    n1 -.-> n7
    n1 -.-> n8
    n2 -.-> n4
    n2 -.-> n8
    n3 -.-> n4
    n3 -.-> n5
    n3 -.-> n6
    n3 -.-> n7
    n4 -.-> n9
    n5 -.-> n9
    n6 -.-> n9
    n7 -.-> n9
    n8 -.-> n9
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pw.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pw.1/README.md) | [sase-pw.1](sase-pw.1.md) | 1 |
| [bbugyi200.athena.sase-pw.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pw.2/README.md) | [sase-pw.2](sase-pw.2.md) | 1 |
| [bbugyi200.athena.sase-pw.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pw.3/README.md) | [sase-pw.3](sase-pw.3.md) | 1 |
| [bbugyi200.athena.sase-pw.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pw.4/README.md) | [sase-pw.4](sase-pw.4.md) | 1 |
| [bbugyi200.athena.sase-pw.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-pw.5.md) | [sase-pw.5](sase-pw.5.md) | 1 |
| [bbugyi200.athena.sase-pw.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pw.6/README.md) | [sase-pw.6](sase-pw.6.md) | 0 |
| [bbugyi200.athena.sase-pw.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-pw.7.md) | [sase-pw.7](sase-pw.7.md) | 0 |
| [bbugyi200.athena.sase-pw.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-pw.8.md) | [sase-pw.8](sase-pw.8.md) | 0 |
| [bbugyi200.athena.sase-pw.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pw.9/README.md) | [sase-pw.9](sase-pw.9.md) | 0 |
| [bbugyi200.athena.sase-pw.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pw.land/README.md) | [sase-pw](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`129bb63`](https://github.com/sase-org/sase/commit/129bb631d3725417e77b7d97ef8e184f52dbf339) | feat(tui): add per-project accent color palette | [sase-pw.2](sase-pw.2.md) | 2026-08-18 11:52:46 EDT |
| sase | [`54083ca`](https://github.com/sase-org/sase/commit/54083ca47c3b1fa07ff4b435a443945da1a3a2c4) | feat(ace): add typed ace.current\_project config | [sase-pw.3](sase-pw.3.md) | 2026-08-18 12:19:58 EDT |
| sase | [`4cf7672`](https://github.com/sase-org/sase/commit/4cf7672bdf783666a3ecacaa7d72e29d6bf40a52) | feat(project): derive current project from the VCS xprompt MRU | [sase-pw.1](sase-pw.1.md) | 2026-08-18 13:55:49 EDT |
| sase | [`7596e4e`](https://github.com/sase-org/sase/commit/7596e4e46ed68e977072df94d0a69a93069909ee) | feat(ace): add current-project chip to the ACE top bar | [sase-pw.4](sase-pw.4.md) | 2026-08-18 14:49:32 EDT |
| sase | [`d6f88f7`](https://github.com/sase-org/sase/commit/d6f88f7b9e73d148ee15e5e01430a9b6ba4b9e0c) | feat(tui): seed Artifacts scope from the current project | [sase-pw.5](sase-pw.5.md) | 2026-08-18 15:46:22 EDT |
