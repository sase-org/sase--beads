# Bead: sase-ej.5 — Keep validation green while publication is pending

[Bead Pages](../README.md) / [sase-ej](README.md) / sase-ej.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sh/README.md) · **Assignee:** `sase-ej.5` · **Size:** small
**Created:** 2026-08-03 06:21:16 EDT · **Closed:** 2026-08-03 09:17:18 EDT
**Plan:** [202608/async\_sidecar\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/async_sidecar_publication.md)

## Description

validate: remove the dead prompt-to-plan link validation and make every remaining prompt-archive and plan check tolerant of a non-empty publication queue so `just check` never depends on sidecar publication.

## Notes

[2026-08-03T13:17:18Z · sase-ej.5] Removed dead prompt-to-plan link validation (missing-link/reverse-link/unpaired-file/cross-kind link-kind) and the --strict flag end to end; made prompt-archive validation queue-aware (prompt-unpublished reports 'queued' when an agent_hood request is pending); confirmed committed-plan schema validation and the plan's own PROMPT-bullet checks pass with unrefreshed AGENTS/COMMITS sections and unpublished prompts. Added a combined test proving both validate_sdd_tree and validate_prompt_archive stay ok with a non-empty publication queue and an unpublished prompt. just lint (ruff, mypy, symvision, pyscripts, changelog) and the full just test suite (25691 passed, 7 skipped) both pass.

## Dependencies

- **Depends on:** [sase-ej.4](sase-ej.4.md) ✓
- **Blocks:** [sase-ej.6](sase-ej.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ej.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.5/README.md) | [sase-ej.5](sase-ej.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1116bcc`](https://github.com/sase-org/sase/commit/1116bccb0a4390e748a4042b9e92bbcb50d991a2) | feat(sdd)!: keep validation green while sidecar publication is pending | [sase-ej.5](sase-ej.5.md) | 2026-08-03 09:18:45 EDT |
