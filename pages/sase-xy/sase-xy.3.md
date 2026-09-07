# Bead: sase-xy.3 — Scanned spans carry line suffixes and shed trailing dots

[Bead Pages](../README.md) / [sase-xy](README.md) / sase-xy.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01q](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01q.md) · **Assignee:** `sase-xy.3` · **Size:** small
**Created:** 2026-09-07 10:02:21 EDT · **Closed:** 2026-09-07 11:07:27 EDT
**Plan:** [202609/pager\_link\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_link_reliability.md)

## Description

span-fidelity: add an opt-in shared matcher variant that extends file-path spans over :LINE/:LINE:COL suffixes and drops sentence-ending dots, adopt it only in the pager's link scanner, and pin the old matcher's behavior for ACE hint callers.

## Notes

[2026-09-07T15:07:27Z · sase-xy.3] Pager scan_links/scan_bounded_links now use iter_pager_file_path_matches: spans include :12 and :12:5, drop sentence-ending dots on absolute/dot-prefix paths, and still skip paths inside URLs. ACE iter_file_path_matches stays byte-identical on the same fixture. just check passed; pager PNG snapshots (tests/pager/visual) passed with no golden updates. No --epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-xy.1](sase-xy.1.md) ✓ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xy.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.3/README.md) | [sase-xy.3](sase-xy.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f6501e3`](https://github.com/sase-org/sase/commit/f6501e308fbf83d544501c724e201c54762361b6) | feat(pager): include :line suffixes in scanned file-path spans | [sase-xy.3](sase-xy.3.md) | 2026-09-07 11:08:47 EDT |
