# Bead: sase-1jx.12.1.1 — Render provider creation fields and constraints

[Bead Pages](../README.md) / [sase-1jx.12.1](sase-1jx.12.1.md) / sase-1jx.12.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.12](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.12.md) · **Assignee:** `sase-1jx.12.1.1` · **Size:** medium
**Created:** 2026-10-12 10:07:51 EDT · **Closed:** 2026-10-12 10:34:18 EDT
**Plan:** [202610/create\_repository\_wizard.md](https://github.com/sase-org/sase--plans/blob/main/202610/create_repository_wizard.md)

## Description

provider-form: implement the standalone RepoCreationForm widget with all five field kinds, searchable typed choices, Advanced disclosure, and Rust lenient evaluation; verify constraints and deterministic widget snapshots without exposing a new production entry point.

## Notes

[2026-10-12T14:34:02Z · sase-1jx.12.1.1] PROPOSED FOLLOW-UP: Resolve the known unrelated Symvision private import of _load_archive_bundle in src/sase/ace/tui/actions/agents/_archive_reader.py; sase tool run check recorded KNOWN witness 12e0a500206437d2397055336b9b9f45. This is already tracked as a DISCOVERED ISSUE on active epic sase-1jm; searches found no task bead.

[2026-10-12T14:34:18Z · sase-1jx.12.1.1] Implemented the standalone provider creation form and typed searchable picker. Seven focused tests passed; the two PNG snapshots are clean, including a TZ=UTC check. sase tool run check reported no new failures and one KNOWN unrelated Symvision _load_archive_bundle import, recorded as a proposed follow-up on this bead.

## Dependencies

- **Blocks:** [sase-1jx.12.1.2](sase-1jx.12.1.2.md) ◐ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.12.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.12.1.1/README.md) | [sase-1jx.12.1.1](sase-1jx.12.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0defe76`](https://github.com/sase-org/sase/commit/0defe76db8bd45af79f5fe4b070b374f28fc34fd) | feat(tui): add provider repository creation form | [sase-1jx.12.1.1](sase-1jx.12.1.1.md) | 2026-10-12 10:35:53 EDT |
