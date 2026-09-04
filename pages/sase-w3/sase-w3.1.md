# Bead: sase-w3.1 — Canonical ref→row resolution rules in sase-core

[Bead Pages](../README.md) / [sase-w3](README.md) / sase-w3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.b](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.b.md) · **Assignee:** `sase-w3.1` · **Size:** large
**Created:** 2026-09-03 12:48:26 EDT · **Closed:** 2026-09-03 17:03:48 EDT
**Plan:** [202609/link\_follow\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/link_follow_reliability.md)

## Description

core-ref-resolution: port ref→row-identity matching predicates (bead kind/project-insensitive ids, plan tri-kind documents, stitch SHA prefixes, patch project disambiguation, agent aliases, file logical ids) into the sase-core Rust crate with wire types, sase_core_py bindings, and a Python facade that backs _known_target_for_ref.

## Notes

[2026-09-03T21:03:48Z · sase-w3.1] Implemented core artifact ref row-resolution rules and verified with linked sase-core just check, main repo just install, focused pytest, and just test-scoped (1692 passed, 1 skipped). Main just check was run but remains blocked by unrelated generated home shim drift in ~/.local/share/chezmoi/home provider shims (athena -> kellys_mbp header).

## Dependencies

- **Blocks:** [sase-w3.2](sase-w3.2.md) ✓ · ⧖ 2026-09-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w3.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-w3.1.md) | [sase-w3.1](sase-w3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8c3e7b6`](https://github.com/sase-org/sase/commit/8c3e7b6bffd9f518ec33ce1698f717b69a49a394) | feat: use core artifact row resolution | [sase-w3.1](sase-w3.1.md) | 2026-09-03 17:06:53 EDT |
| sase-core | [`sase-core@30fe0b2`](https://github.com/sase-org/sase-core/commit/30fe0b283820af47514ff1ba2202919888373049) | feat: nonical ref to row resolution rules in sase-core (sase-w3.1) | [sase-w3.1](sase-w3.1.md) | 2026-09-03 17:20:02 EDT |
