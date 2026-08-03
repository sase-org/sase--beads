# Bead: sase-ej.1 — Bound the agent-name registry source scan

[Bead Pages](../README.md) / [sase-ej](README.md) / sase-ej.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sh/README.md) · **Assignee:** `sase-ej.1` · **Size:** medium
**Created:** 2026-08-03 10:19:49 UTC · **Closed:** 2026-08-03 12:38:31 UTC
**Plan:** [202608/async\_sidecar\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/async_sidecar_publication.md)

## Description

scanfix: eliminate the per-lookup rescan of ~17k dismissed bundles and every agent artifact directory that makes plan-association resolution CPU-bound, which is the concrete stall reported by sase-cl.

## Notes

[2026-08-03T11:29:53Z · sase-ej.1] PROPOSED FOLLOW-UP: Harden load-sensitive full-suite tests under concurrent workspace checks — competing runs caused metadata-search timing failure, bead-lock timeout, and suite-gate child timeout while focused reruns passed.

[2026-08-03T12:38:31Z · sase-ej.1] Verified one best-effort registry snapshot across 200 plan-agent associations, one source enumeration per registry-load session, mtime-keyed dismissed-bundle and artifact-walk caches with add/remove/rewrite staleness, and the existing 1k-bundle save path at 0.79s. Ruff, mypy, git diff checks, and 41 focused xdist tests pass; full just check static/validation stages pass, while unrelated host-load timing failures were recorded as a PROPOSED FOLLOW-UP.

[2026-08-03T12:39:51Z · sase-ej.1] Verified one best-effort registry snapshot across 200 plan-agent associations, one source enumeration per registry-load session, mtime-keyed dismissed-bundle and artifact-walk caches with add/remove/rewrite staleness, Ruff, mypy, and 41 focused xdist tests.

## Dependencies

- **Blocks:** [sase-ej.6](sase-ej.6.md) ◐
