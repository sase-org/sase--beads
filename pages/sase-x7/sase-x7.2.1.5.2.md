# Bead: sase-x7.2.1.5.2 — Fold the mac results in and publish the four kit-rehearsal artifacts

[Bead Pages](../README.md) / [sase-x7.2.1.5](sase-x7.2.1.5.md) / sase-x7.2.1.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-x7.2.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.2.1.land.md) · **Assignee:** `sase-x7.2.1.5.2` · **Size:** small
**Created:** 2026-09-06 00:20:48 EDT · **Closed:** 2026-09-06 08:07:02 EDT
**Plan:** [202609/mac\_rehearsal\_leg.md](https://github.com/sase-org/sase--plans/blob/main/202609/mac_rehearsal_leg.md)

## Description

publish-evidence: Fold the mac leg into the rehearsal receipt, finish the athena, mac, and apollo per-host operation manifests, and publish all four as artifacts attached to `sase-x7.2.1.4`.

## Notes

[2026-09-06T12:05:20Z · sase-x7.2.1.5.2] PROPOSED FOLLOW-UP: live sase-core-rs on mac and apollo is still 0.32.23, below the kit floor >=0.32.25 — local-state-cutover must raise those live installs before a real apply; do not use sase update against mac's editable checkout mid-window

[2026-09-06T12:05:41Z · sase-x7.2.1.5.2] PROPOSED FOLLOW-UP: sase completion list on mac reports Linux chezmoi paths (/home/bryan/...) as missing even though mac-native completion files exist — live install completion config is chezmoi-templated from Linux; canonical-producers or a chezmoi pass should make deploy-chezmoi mac-aware

[2026-09-06T12:06:01Z · sase-x7.2.1.5.2] Published four kit-rehearsal artifacts attached to closed bead sase-x7.2.1.4 (attach succeeded; did not reopen it). Route taken: --bead sase-x7.2.1.4. Refs: file:explicit:abd69e7c49c9a80e10a7ddc4 athena manifest; file:explicit:7f8d1c21d89f50bbbeb910e0 mac manifest; file:explicit:d994f4801484d01cdf516716 apollo manifest; file:explicit:4448c6edceb528c36af3e04e rehearsal receipt. Receipt has no DRAFT marker and covers Linux+macOS. Every manifest names -s/--secondary ($HOME/cutover-backups/secondary/) and disclaims rehearsal backups. epic-symbols clean. No repo files changed.

[2026-09-06T12:07:02Z · sase-x7.2.1.5.2] Verified four kit-rehearsal artifacts published and attached to sase-x7.2.1.4 (attach to the closed bead succeeded; did not reopen it): file:explicit:abd69e7c49c9a80e10a7ddc4 athena manifest, file:explicit:7f8d1c21d89f50bbbeb910e0 mac manifest, file:explicit:d994f4801484d01cdf516716 apollo manifest, file:explicit:4448c6edceb528c36af3e04e rehearsal receipt. sase artifact list -e discovers them; sase artifact show reports resolution_status=exact on all four. Receipt has no DRAFT marker and records the synthetic matrix on both Linux and macOS (Darwin 71 passed / 1 skip justified: unshare ENOSPC variant). Each manifest names -s/--secondary $HOME/cutover-backups/secondary/ and states rehearsal backups are not cutover backups. Mac F3: code-swap.lock classify_only (absent), code-swap-v2.lock refuse_archive_current_writer. Athena refusals kept as successful outcomes. epic-symbols clean. No repo files changed.

## Dependencies

- **Depends on:** [sase-x7.2.1.5.1](sase-x7.2.1.5.1.md) ✓ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.2.1.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.2.1.5.2/README.md) | [sase-x7.2.1.5.2](sase-x7.2.1.5.2.md) | 0 |
