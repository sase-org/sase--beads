# Bead: sase-m9.1.1 — Sase agent and shell taxonomy migration

[Bead Pages](../README.md) / [sase-m9.1](sase-m9.1.md) / sase-m9.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.1.md) · **Assignee:** `sase-m9.1.1.land`
**Created:** 2026-08-14 19:23:30 EDT · **Closed:** 2026-08-14 21:36:04 EDT
**Plan:** [202608/shell\_taxonomy.md](https://github.com/sase-org/sase--plans/blob/main/202608/shell_taxonomy.md)

## Description

Replace the agent-lane term with the canonical sase-agent and sase-shell model, preserve serialized and Python compatibility where required, and migrate monitor CLI language without changing runtime behavior.

## Notes

[2026-08-15T01:36:04Z · sase-m9.1.1.land] Landed shell taxonomy cleanup for user-facing monitor/agent-family docs and help text while preserving compatibility/internal lane APIs. Verified earlier in this workspace: generated skill preview clean, sase memory init --check passed, focused suite passed (399 tests), and just check passed with scoped tests escalating to the full suite. Finalizer also reran git diff --check clean. just check-full monitor result was not confirmed under the single-turn finalizer contract.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.1.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.1.1.land.md) | [sase-m9.1.1](sase-m9.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`76356cf`](https://github.com/sase-org/sase/commit/76356cf57d71e7574350f003f15caea0f50d9c0d) | docs: align shell taxonomy wording | [sase-m9.1.1](sase-m9.1.1.md) | 2026-08-14 21:36:53 EDT |
