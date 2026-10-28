# Bead: sase-1ou.5.1.2 — Prepare and test the three-host maintenance procedure

[Bead Pages](../README.md) / [sase-1ou.5.1](sase-1ou.5.1.md) / sase-1ou.5.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ou.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.5.md) · **Assignee:** `sase-1ou.5.1.2` · **Size:** medium
**Created:** 2026-10-27 09:36:44 EDT · **Closed:** 2026-10-27 09:54:58 EDT
**Plan:** [202610/agents\_history\_remediation.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_history_remediation.md)

## Description

fleet-protocol: inventory every agents-sidecar writer and clone on athena, apollo and mac, implement a private command bundle for quiescence and clone recovery, and verify it on disposable fixtures without production mutations.

## Notes

[2026-10-27T13:53:59Z · sase-1ou.5.1.2] Private fleet-protocol deliverables: inventory, runbook, executable fixture bundle, test evidence.

🔒 fleet-inventory.md
🔒 maintenance-runbook.md
🔒 test-evidence.txt
🔒 sase-1ou.5.1.2-fleet-protocol.tar.gz

[2026-10-27T13:54:42Z · sase-1ou.5.1.2] Private attachments: fleet-inventory.md sha256:02423da546480d04deaaf14380870aaff05f0ac586b5224675205cff0c6f97cf; maintenance-runbook.md sha256:60f5202188ed0a66af32bc9b6bd7041c8f33d4bc887d224bae71a9578566bba9; sase-1ou.5.1.2-fleet-protocol.tar.gz sha256:70cd3ea90a7f3f9109b2a2ace9db79400a3118048fe4422e95270e742ff13c28; test-evidence.txt sha256:896b5b8bbbb7459578ef46ed309195d1285e1dd2e1045dd5dcb085892007aca4. Fixture tests: 20 passed. No production services or clones mutated. All three hosts reachable this snapshot. Apollo has 1 local-only agents commit to preserve. Mac sase 0.18.0+83 vs athena/apollo 0.18.1+52.

PROPOSED FOLLOW-UP: Mac sase/core is behind athena/apollo (0.18.0+83 / 0.42.1 vs 0.18.1+52 / 0.42.7; outbox schema v5 vs v7; no protection ledger) — update or treat as version-skew before relying on sase-1oh.5.1 protection during execution.

[2026-10-27T13:54:58Z · sase-1ou.5.1.2] Verified fleet-protocol on disposable fixtures only (20 pytest passed). Read-only inventory of athena, apollo, and mac: all reachable this snapshot; shared sase--agents clones identified via sase repo list; writer catalog covers commit drain, full sync, prompt publish, migration (excluded, sase-1os), referenced-by, workspace prep, rescue, repairs; scheduler is not an agents writer. Quiesce/recover/canary bundle attached privately. No production services or clones mutated. Apollo local-only commit recorded for preserve. Mac version skew recorded as proposed follow-up. epic-symbols clear.

## Attachments

- 🔒 fleet-inventory.md · text/markdown · 6.66504 KiB (private attachment)
- 🔒 maintenance-runbook.md · text/markdown · 5.26172 KiB (private attachment)
- 🔒 sase-1ou.5.1.2-fleet-protocol.tar.gz · application/gzip · 22.6641 KiB (private attachment)
- 🔒 test-evidence.txt · text/plain · 2.12109 KiB (private attachment)

## Dependencies

- **Blocks:** [sase-1ou.5.1.3](sase-1ou.5.1.3.md) ✓ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.5.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.5.1.2/README.md) | [sase-1ou.5.1.2](sase-1ou.5.1.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ou.5.1.land][1] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.5.1.land/README.md

<!-- sase:referenced-by:end -->
