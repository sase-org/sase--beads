# Bead: sase-1rs.7 — Login-expiry watcher, reminders, and phone renewal

[Bead Pages](../README.md) / [sase-1rs](README.md) / sase-1rs.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.19n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.19n.md) · **Assignee:** `sase-1rs.7` · **Size:** small
**Created:** 2026-11-07 10:56:01 EST · **Closed:** 2026-11-07 14:16:53 EST
**Plan:** [202611/spotify\_agent\_access.md](https://github.com/sase-org/sase--plans/blob/main/202611/spotify_agent_access.md)

## Description

lifecycle: add the scheduler job that watches login expiry and the needs-reauth state, sends deduplicated reminders, and raises the phone renewal gate.

## Notes

[2026-11-07T19:16:41Z · sase-1rs.7] Cross-phase edits (minimal, per parallel-phase rules): tests/fakes/sase_cli.py (scaffold) now honors a request_id on gate create idempotently, reports status in gate show, and adds FakeSase.settle_gate (matching real sase behavior verified on athena); tests/test_cli.py drops the two lifecycle stub leaves; tests/test_entry_points.py asserts the shipped routine and replaces the auth_watch stub test; cli/auth.py (auth, co-owned by lifecycle) logout now cancels a live renewal gate first and treats lifecycle.lock as a lock, not other state. The routine ships via sase_config default_config.yml (plugin layers deep-merge; map-form jobs so a user layer can set enabled: false), so rollout does not need the chezmoi routine option. Renewal is always on (decision phone_renewal=yes); reads can detect a live request via sase_spotify.jobs.renewal.load_state().reminder (kind gate, live).

[2026-11-07T19:16:53Z · sase-1rs.7] Lifecycle landed in sase-spotify: jobs/auth_watch.py (sase_job_spotify_auth, axe script-job contract: --context, dry_run, compact summary, schema-v1 result file; agents refused exit 7), jobs/renewal.py (d14/d3/expired/reauth stages, exactly one live renewal gate with later stages superseding, intent recorded before gate create with deterministic request_id so crashes replay idempotently, notice-row fallback with dedup/supersede), auth renew (human or job) and hidden auth complete (gate only; renewed | retry with one fresh gate | closed; later), default_config.yml spotify routine every 30 min, docs (getting-started renewal section, troubleshooting). Verified: sase tool run check green (ruff, format, mypy --strict, codespell, 791 tests, coverage 98%); 97 new lifecycle tests incl. threshold math, dedup/supersede via fake bridge, dry_run, agent markers absent/present, renewal round trip vs fake accounts (state mismatch, retry path, secret never echoed) and the generated gate wrapper run as a real subprocess; contract test against real sase under temp SASE_HOME passed (gate accepted, idempotent replay, sase gate answer ran later and renew->retry with a fresh pending gate, secret absent from answer); default_config routine validated against the sase config schema, including a merged user override setting enabled: false; job result files validated with sase validate_chop_result.

## Dependencies

- **Blocks:** [sase-1rs.10](sase-1rs.10.md) ◐ · ⧖ 2026-11-07
- **Depends on:** [sase-1rs.3](sase-1rs.3.md) ✓ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rs.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.7/README.md) | [sase-1rs.7](sase-1rs.7.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rs.7][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.7/README.md

<!-- sase:referenced-by:end -->
