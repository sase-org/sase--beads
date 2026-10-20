# Bead: sase-1n8.5 — sase-core: honor the low-free-space pressure age for unheld entries

[Bead Pages](../README.md) / [sase-1n8](README.md) / sase-1n8.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.96` · **Assignee:** `sase-1n8.5` · **Size:** small
**Created:** 2026-10-20 06:53:00 EDT · **Closed:** 2026-10-20 07:35:22 EDT
**Plan:** [202610/host\_completion\_loop\_and\_disk\_churn.md](https://github.com/sase-org/sase--plans/blob/main/202610/host_completion_loop_and_disk_churn.md)

## Description

core-pressure-emergency-age: let observed-unheld pressure candidates use the shorter of the dead-launch grace and the emergency min age.

## Notes

[2026-10-20T11:35:05Z · sase-1n8.5] PROPOSED FOLLOW-UP: Give federation_worker::imp::tests::ipc::listener_creates_private_socket_and_rejects_symlink a unique temporary socket path; the full core check hit a parallel shared-socket collision, while the isolated test passed.

[2026-10-20T11:35:22Z · sase-1n8.5] Implemented the observed-unheld cutoff as the shorter of the dead-launch grace and effective pressure age; added and passed low_free_space_age_applies_to_observed_unheld_pressure_entries. just fmt and diff check passed. sase tool run check compiled and ran the suites but exited 101 on the unrelated gateway shared-socket test; that test passed in isolation. Recorded its test-isolation follow-up. epic-symbols had no leftovers.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n8.5/README.md) | [sase-1n8.5](sase-1n8.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@2f43385`](https://github.com/sase-org/sase-core/commit/2f4338511dbb8230d2254bee7da52798d6a65aca) | fix(managed-tmp): honor emergency pressure age | [sase-1n8.5](sase-1n8.5.md) | 2026-10-20 07:35:57 EDT |
