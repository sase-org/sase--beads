# Bead: sase-uk.10 — Four pagers become one

[Bead Pages](../README.md) / [sase-uk](README.md) / sase-uk.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ej](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ej.md) · **Assignee:** `sase-uk.10` · **Size:** medium
**Created:** 2026-08-26 17:44:41 EDT · **Closed:** 2026-08-27 09:20:08 EDT
**Plan:** [202608/link\_traversing\_pager.md](https://github.com/sase-org/sase--plans/blob/main/202608/link_traversing_pager.md)

## Description

land: delete `_print_or_page`, `_view_files_with_pager`, and the `less` back end of `page_or_print`, point the text mode of the artifact viewer at the pager, remove the flag, and close the flag bead — as a net deletion.

## Notes

[2026-08-27T13:20:08Z · sase-uk.10] Removed the legacy pager paths and link_pager flag, routed CLI/ACE/artifact text viewing through SasePager, closed the retired flag bead, confirmed no leftover epic symbols, and verified focused pager/viewer tests plus just check.

## Dependencies

- **Depends on:** [sase-uk.9](sase-uk.9.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-uk.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-uk.10/README.md) | [sase-uk.10](sase-uk.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`259f399`](https://github.com/sase-org/sase/commit/259f399012febb6778e7ca1bfb94e7251d642b94) | feat(pager): retire legacy text paging paths | [sase-uk.10](sase-uk.10.md) | 2026-08-27 09:21:55 EDT |
