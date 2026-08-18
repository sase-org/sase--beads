# Bead: sase-p2 — Repo mentions in the prompt — highlight, preview, and jump

[Bead Pages](../README.md) / sase-p2

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.059](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.059.md) · **Assignee:** `sase-p2.land`
**Created:** 2026-08-17 18:09:16 EDT
**Plan:** [202608/prompt\_repo\_mentions.md](https://github.com/sase-org/sase--plans/blob/main/202608/prompt_repo_mentions.md)

## Description

Repo names typed into any ACE prompt input (`sase-core`, `chezmoi`, `gh:owner/repo`) are highlighted in their own color with the same underlined link affordance glossary terms already use, and `K` / `Ctrl+]` open a repo card and the repo itself.

## Notes

[2026-08-18T01:03:11Z · toobig-30.split_file.src.sase.completion.candidates.catalog.0] DISCOVERED ISSUE: phase sase-p2.2 closed at 2026-08-18T00:45:45Z with its six Justfile --epic-symbol entries still keyed to that phase bead, so `just _lint-symvision` (and therefore every agent's mandatory `just check`) now fails repo-wide while this epic is still in progress.

REPRODUCTION: `just check` on a tree whose only diff is an unrelated refactor (splitting src/sase/completion/candidates/catalog.py) passes fmt/keep-sorted/ruff/mypy/flags/pyscripts/test-waits/changelog/terminology and then fails at lint (symvision) with six identical errors: "--epic-symbol 'sase-p2.2(<symbol>)': bead 'sase-p2.2' is closed. Remove this stale --epic-symbol entry and clean up the symbol." Entries are Justfile lines 336-341: EditorRepoMentionCatalog, EditorRepoMentionCatalogResult, RepoMentionSpan, editor_repo_mention_catalog_for_project, lookup_repo_mention, scan_repo_mentions.

CONFIRMED UNRELATED TO THE REPORTING DIFF: re-running the same symvision invocation with only those six entries dropped reports exactly those six symbols in src/sase/xprompt/repo_mention_catalog.py as unused public defs and nothing else -- i.e. the whitelist is still doing real work and the symbols are simply not consumed yet.

WHY IT LANDS ON THIS EPIC: the symbols' intended consumer is phase sase-p2.3 (K opens the repo card), which is IN_PROGRESS. The exemptions are still legitimate; they are just keyed to a bead that closed early. The fix is to retarget lines 336-341 to the still-open bead that will consume them (sase-p2.3, or the epic sase-p2) rather than to delete the symbols. RELATED: task sase-o7 tracks the systemic version of this gap.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-p2.1](sase-p2.1.md) | Repo mention catalog | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p2.2](sase-p2.2.md) | Prompt highlighting | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p2.3](sase-p2.3.md) | K opens the repo card | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p2.4](sase-p2.4.md) | Ctrl+\] opens the repo | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-p2: Repo mentions in the prompt — highlight, preview, and jump [in_progress]"]
    n1["sase-p2.1: Repo mention catalog [closed]"]
    n2["sase-p2.2: Prompt highlighting [closed]"]
    n3["sase-p2.3: K opens the repo card [closed]"]
    n4["sase-p2.4: Ctrl+] opens the repo [in_progress]"]
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
| [bbugyi200.athena.sase-p2.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p2.1/README.md) | [sase-p2.1](sase-p2.1.md) | 1 |
| [bbugyi200.athena.sase-p2.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p2.2.md) | [sase-p2.2](sase-p2.2.md) | 1 |
| [bbugyi200.athena.sase-p2.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p2.3.md) | [sase-p2.3](sase-p2.3.md) | 1 |
| [bbugyi200.athena.sase-p2.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p2.4/README.md) | [sase-p2.4](sase-p2.4.md) | 0 |
| [bbugyi200.athena.sase-p2.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p2.land/README.md) | [sase-p2](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fb16cfa`](https://github.com/sase-org/sase/commit/fb16cfaf85fdcc9a29ba9ba64c89f6344d7e3d2e) | feat(xprompt): add project-scoped repo mention catalog | [sase-p2.1](sase-p2.1.md) | 2026-08-17 18:59:46 EDT |
| sase | [`6c41322`](https://github.com/sase-org/sase/commit/6c4132221e506c72171827e40d9e52693b167d7c) | feat(ace): highlight repo names in the prompt as lavender links | [sase-p2.2](sase-p2.2.md) | 2026-08-17 20:52:32 EDT |
| sase | [`f54a911`](https://github.com/sase-org/sase/commit/f54a911753be1eed4a6576f4a14fdde7389940fe) | feat(ace): add K repo preview card for mentioned repos | [sase-p2.3](sase-p2.3.md) | 2026-08-17 22:03:01 EDT |
