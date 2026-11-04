# Bead: sase-1r5.1.3 — Adopt credential retries in the SDD store clone

[Bead Pages](../README.md) / [sase-1r5.1](sase-1r5.1.md) / sase-1r5.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1r5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r5.md) · **Assignee:** `sase-1r5.1.3` · **Size:** medium
**Created:** 2026-11-04 06:54:53 EST · **Closed:** 2026-11-04 09:27:30 EST
**Plan:** [202611/github\_publickey\_retry.md](https://github.com/sase-org/sase--plans/blob/main/202611/github_publickey_retry.md)

## Description

sdd-clone-adopt: give `clone_sdd_store_to_path` a credential-retry budget separate from its transient schedule, using the launch budget, never holding the clone admission permit while sleeping. Prove it with an SSH-shim fake GitHub remote that denies N times and then serves a real bare repo.

## Notes

[2026-11-04T14:17:19Z · sase-1r5.1.3] Work complete and verified: credential-retry adoption in clone_sdd_store_to_path plus 7 SSH-shim tests; just check run aae4d28fb7bdc6cb2621fb7dd941f6ff EXIT 0 (all lint stages + scoped tests green). Local tree resolves both symbols (CredentialRetry consumed; CredentialRetryBudget row re-keyed to open sase-1r5.1.4). Close is BLOCKED by the leftover-epic-symbols guard: origin/master still carries both sase-1r5.1.3 rows (landed by sase-1r5.1.2) and no local edit can clear them. Land agent (sase-1r5.1.land): land this phase commit first, then close this bead once master no longer has the rows.

[2026-11-04T14:21:37Z · sase-1r5.1.3] LAND-READY: tree re-verified unchanged since green just check (same 3 dirty paths; 7 shim tests re-passed just now; no other references to the removed rows anywhere outside beads history). No local epic-symbol rows keyed to this bead. Ready for the land agent to land, then close this bead once origin/master drops the rows.

[2026-11-04T14:27:30Z · sase-1r5.1.3] Closed by explicit `sase stitch create -B close` after create_commit landed 82742081f9 ("feat(retryability): adopt credential retries in the SDD store clone"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1r5.1.3` if more work remains.

## Dependencies

- **Depends on:** [sase-1r5.1.2](sase-1r5.1.2.md) ✓ · ⧖ 2026-11-04
- **Blocks:** [sase-1r5.1.5](sase-1r5.1.5.md) ✓ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r5.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r5.1.3.md) | [sase-1r5.1.3](sase-1r5.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8274208`](https://github.com/sase-org/sase/commit/82742081f9bdb02a282ebd209b4c2bfa1bd58d0a) | feat(retryability): adopt credential retries in the SDD store clone | [sase-1r5.1.3](sase-1r5.1.3.md) | 2026-11-04 09:26:41 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1r5.1.2--1][1] | Need the next phase status and scope before assigning temporary symbol ownership | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r5.1.2.md

<!-- sase:referenced-by:end -->
