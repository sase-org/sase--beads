# Bead: sase-jd.3 — PR\_ORIGIN field, SASE\_PATCH stamp, and the external-Patch safety exclusion

[Bead Pages](../README.md) / [sase-jd](README.md) / sase-jd.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xp](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xp/README.md) · **Assignee:** `sase-jd.3` · **Size:** medium
**Created:** 2026-08-10 19:14:03 EDT
**Plan:** [202608/external\_artifact\_ingestion.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_artifact_ingestion.md)

## Description

pr_origin: add the tri-state PR_ORIGIN Patch field across parser, storage, section order, and the four ACE styling surfaces; stamp SASE_PATCH in append_pr_tags; and structurally exclude external Patches from AXE work before any importer can create one.

## Notes

[2026-08-10T23:43:06Z · sase-jd.3] PROPOSED FOLLOW-UP: Remove stale Symvision epic-symbol override — just check fails because --epic-symbol sase-j3(SnippetTriggerMatch) points at closed bead sase-j3.

[2026-08-10T23:43:49Z · sase-jd.3] PROPOSED FOLLOW-UP: Restore PR_ORIGIN Vim syntax styling surface — linked chezmoi checkout lacks home/dot_config/nvim/syntax/saseproject.vim or an obvious generated source for this plan item.

## Dependencies

- **Blocks:** [sase-jd.5](sase-jd.5.md) ◐ · ⧖ 2026-08-10
- **Blocks:** [sase-jd.7](sase-jd.7.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jd.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jd.3/README.md) | [sase-jd.3](sase-jd.3.md) | 0 |
