# Bead: sase-1ig.10 — Retire the chezmoi installers into install-dev

[Bead Pages](../README.md) / [sase-1ig](README.md) / sase-1ig.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ym](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md) · **Assignee:** `sase-1ig.10` · **Size:** small
**Created:** 2026-10-08 18:23:32 EDT · **Closed:** 2026-10-09 01:11:57 EDT
**Plan:** [202610/just\_install\_pypi\_dev\_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)

## Description

chezmoi-acei: point `acei`/`aceii` at `just install-dev --sync -y` on the durable sase checkout and delete the drifted install_sase_github/install_sase_google scripts and their bash test.

## Notes

[2026-10-09T05:11:57Z · sase-1ig.10] Retired chezmoi installers: acei/aceii in home/dot_config/aliases.sh now run just install-dev --sync -y on the durable sase checkout (aceii adds --with sase-google --with sase-gchat), dropped the tui --restart-axe suffix, and deleted executable_install_sase_github, executable_install_sase_google, and tests/bash/install_sase_github_test.sh. Verified: repo-wide grep shows zero remaining install_sase_github/google references, bash -n and function definitions parse, shellcheck reports no new warnings on the edited lines, install-dev --sync -y flags confirmed live in tools/sase_install, and epic-symbols is clean. Did not run chezmoi apply per plan.

## Dependencies

- **Depends on:** [sase-1ig.8](sase-1ig.8.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ig.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.10/README.md) | [sase-1ig.10](sase-1ig.10.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ig.10][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.10/README.md

<!-- sase:referenced-by:end -->
