# Bead: sase-1ko.8 — Codex developer-instructions delivery, project-doc suppression, and shadow-home hygiene (folds sase-11s)

[Bead Pages](../README.md) / [sase-1ko](README.md) / sase-1ko.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.8` · **Size:** medium
**Created:** 2026-10-13 18:10:36 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

## Description

codex: create the `codex_explicit_instructions` sunset flag. When it is on, deliver the whole root bundle through `developer_instructions`, add `project_doc_max_bytes=0` in SASE-managed projects only, and leave the shadow home without any SASE AGENTS.md. Rebuild the shadow home from an allowlist so shared sqlite state is never linked (closes sase-11s), and declare the subagent slot inherits_root.

## Dependencies

- **Depends on:** [sase-1ko.1](sase-1ko.1.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.10](sase-1ko.10.md) ◐ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.5](sase-1ko.5.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.6](sase-1ko.6.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.8/README.md) | [sase-1ko.8](sase-1ko.8.md) | 0 |
