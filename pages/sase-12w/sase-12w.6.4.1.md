# Bead: sase-12w.6.4.1 — Restore portable sudo-runner release builds

[Bead Pages](../README.md) / [sase-12w.6.4](sase-12w.6.4.md) / sase-12w.6.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-12w.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-12w.6.land.md) · **Assignee:** `sase-12w.6.4.1` · **Size:** medium
**Created:** 2026-09-18 19:35:02 EDT · **Closed:** 2026-09-18 20:24:00 EDT
**Plan:** [202609/publish\_detached\_sudo\_core.md](https://github.com/sase-org/sase--plans/blob/main/202609/publish_detached_sudo_core.md)

## Description

core-portability: fix the epic-introduced macOS initgroups type mismatch without weakening account-switch validation, prove the runner on Linux and with an Apple-target compile or release-equivalent check, and let the normal sase-core release workflow publish the repaired contracts.

## Notes

[2026-09-19T00:24:00Z · sase-12w.6.4.1] Verified checked initgroups base-group conversion preserving initgroups/setgid/setuid order; cargo fmt --check, focused sudo_runner tests, focused sase_gateway clippy, Apple-target initgroups compile probe, and just check passed (after rerunning one transient Text-file-busy test flake); epic-symbols reported none.

## Dependencies

- **Blocks:** [sase-12w.6.4.2](sase-12w.6.4.2.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12w.6.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12w.6.4.1/README.md) | [sase-12w.6.4.1](sase-12w.6.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4a8c6d4`](https://github.com/sase-org/sase-core/commit/4a8c6d40de0fcbdb4ea11e051b8b99656fd20589) | fix(sudo): check initgroups base group on apple | [sase-12w.6.4.1](sase-12w.6.4.1.md) | 2026-09-18 20:25:28 EDT |
