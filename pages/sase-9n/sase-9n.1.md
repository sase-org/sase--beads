# Bead: sase-9n.1 — Allow one template marker in each of a chop proposal's clan and member

[Bead Pages](../README.md) / [sase-9n](README.md) / sase-9n.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9n.1` · **Size:** small
**Created:** 2026-07-25 16:59:26 UTC · **Closed:** 2026-07-25 17:05:04 UTC
**Plan:** [202607/toobig\_split\_at\_names.md](https://github.com/sase-org/sase--plans/blob/main/202607/toobig_split_at_names.md)

## Description

"Phase 1 - Core: allow one marker in each of clan and member" section: relax `validate_clan_member_identity` in the sase-core chop validator so a composed clan-member name may carry one `@` from the clan template and one from the member template, keeping the per-component "at most one marker" rule, and update the Rust unit tests that pin the old `ambiguous_agent_name_template` behavior.

## Dependencies

- **Blocks:** [sase-9n.2](sase-9n.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9n.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9n.1/README.md) | [sase-9n.1](sase-9n.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@5372a48`](https://github.com/sase-org/sase-core/commit/5372a4877fc970222311f1a3b4a734b85c83208b) | feat(axe\_chop): allow one template marker in each of a chop clan and member (sase-9n.1) | [sase-9n.1](sase-9n.1.md) | 2026-07-25 17:06:22 |
