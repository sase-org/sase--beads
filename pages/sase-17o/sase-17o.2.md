# Bead: sase-17o.2 — Publish bead waits and project awaits links

[Bead Pages](../README.md) / [sase-17o](README.md) / sase-17o.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qk.md) · **Assignee:** `sase-17o.2` · **Size:** medium
**Created:** 2026-09-24 08:23:09 EDT · **Closed:** 2026-09-24 09:14:15 EDT
**Plan:** [202609/agent\_wait\_bead\_links.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_wait_bead_links.md)

## Description

wait-projection: publish `wait_for_beads` as portable agent metadata, add an `agent-wait-bead` projection rule emitting `agent:<name> awaits bead:<id>`, bump the sase-core pin, and update docs, TUI sigils, snapshots, and tests.

## Notes

[2026-09-24T12:55:31Z · sase-17o.2] PROPOSED FOLLOW-UP: agent-to-agent waits (%wait:<agent>) still produce no artifact link; awaits was named so it can later accept agent targets

[2026-09-24T12:56:08Z · sase-17o.2] PROPOSED FOLLOW-UP: drop the Python stale-binding relation fallbacks once the installed sase-core-rs floor includes awaits

[2026-09-24T13:03:40Z · sase-17o.2] PROPOSED FOLLOW-UP: stale untracked prompt-archive objects in agents sidecar (files/objects/sha256/40/40de62, 41/414a92, 5b/5bd2b6 from Aug/Sep) are protected+foreign and block sase final prepare for every agent; needs owner cleanup

[2026-09-24T13:13:31Z · sase-17o.2] PROPOSED FOLLOW-UP: just check symvision gate fails identically on clean HEAD (66 pre-existing private-import violations); needs owner triage, blocks every agents just check

[2026-09-24T13:14:15Z · sase-17o.2] wait-projection done: pin eef7ca4, awaits fallback+rule, wait_for_beads published (live+dismissed), sigil+docs+registry regenerated; 207 focused tests pass, fmt/ruff/mypy clean; symvision failure pre-existing on HEAD (identical 66 violations)

## Dependencies

- **Depends on:** [sase-17o.1](sase-17o.1.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17o.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17o.2/README.md) | [sase-17o.2](sase-17o.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8d97ef7`](https://github.com/sase-org/sase/commit/8d97ef7661de6b7aa42cf979d166606c7ee1d815) | feat(wait-links): publish wait\_for\_beads and project agent awaits bead links (sase-17o.2) | [sase-17o.2](sase-17o.2.md) | 2026-09-24 09:16:17 EDT |
