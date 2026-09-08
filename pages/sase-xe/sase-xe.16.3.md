# Bead: sase-xe.16.3 — Target-local \`sase machine bootstrap\` and packaged-command resolution

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.3` · **Size:** medium
**Created:** 2026-09-08 10:21:34 EDT · **Closed:** 2026-09-08 12:37:18 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

## Description

machine-bootstrap-cli: add `sase machine bootstrap [-e|--expires SECONDS] [-j|--json] [-s|--scope SCOPE ...]`, a target-local thin wrapper over the new issue_bootstrap binding that prints an enrollment bundle in exactly the format `MachineService._parse_enrollment_bundle` accepts, using the same OS user and SASE home as the gateway; the secret appears once on stdout and is never logged, echoed to prompts, or accepted as an argv value. Fix packaged command resolution: `resolve_federation_worker_command` (and a sibling resolver for the new `sase_gateway` console script) must also check `Path(sys.executable).parent`, because uv-tool installs put dependency console scripts inside the tool venv without exposing them on PATH. Add a non-deep doctor check that the federation worker command resolves whenever machines are configured (mobile-gateway precedent). Update the pinned machine-parser subcommand-set test.

## Notes

[2026-09-08T16:37:18Z · sase-xe.16.3] Verified: targeted bootstrap/parser/service/resolver/doctor tests passed; prior full-suite failures reran green after linked core install and time-format fix; git diff --check clean; just check passed with scoped lane escalated to full suite; epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-xe.16.1](sase-xe.16.1.md) ✓ · ⧖ 2026-09-08
- **Blocks:** [sase-xe.16.10](sase-xe.16.10.md) ◐ · ⧖ 2026-09-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.3/README.md) | [sase-xe.16.3](sase-xe.16.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`18b0a91`](https://github.com/sase-org/sase/commit/18b0a91a264ddd3e9b55a609c9a62c209b87a06a) | feat(machine): add target bootstrap CLI | [sase-xe.16.3](sase-xe.16.3.md) | 2026-09-08 12:39:32 EDT |
