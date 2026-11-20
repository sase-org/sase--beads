# Bead: sase-1tz.3.1.8 — Run the Telegram outbound routine only on the sending machine

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.8` · **Size:** small
**Created:** 2026-11-20 09:19:07 EST · **Closed:** 2026-11-20 09:30:44 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

tg_scope: move the axe.routines.telegram routine from the shared chezmoi sase.yml into sase_athena.yml next to the telegram_receiver proc. Confirm the machine overlay loads it on athena and leaves apollo and mac without it.

## Notes

[2026-11-20T14:30:19Z · sase-1tz.3.1.8] tg_scope done: moved axe.routines.telegram (interval/env/tg_outbound, byte-identical) from shared sase.yml into sase_athena.yml next to telegram_receiver; apollo overlay comment updated; receiver mirror comments now point inside sase_athena.yml. No commit/apply (human-only); land agent: needs chezmoi apply on each host.

[2026-11-20T14:30:26Z · sase-1tz.3.1.8] BEFORE (read-only, 2026-11-20 ~09:30 EST): athena telegram routine running (pid 1355647, 8.323/min, 923 cycles); apollo telegram routine running (pid 722495, 12.699/min, 1071 cycles, wasted ticks); mac telegram lumberjack dir present. AFTER-INSTALL REPEAT: on each host run chezmoi apply (human), then confirm: apollo/mac have no telegram routine (ls ~/.sase/axe/lumberjacks/ shows no telegram; sase config show has no axe.routines.telegram) and athena still runs tg_outbound.

[2026-11-20T14:30:44Z · sase-1tz.3.1.8] Moved axe.routines.telegram from shared chezmoi sase.yml to sase_athena.yml (apollo comment updated). Verified with real Rust-backed compose_axe_config: telegram+tg_outbound present on athena (declared by athena overlay, env/interval intact, zero diagnostics), absent on apollo/mac. Before-numbers recorded on bead; live apply is human-run.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.8/README.md) | [sase-1tz.3.1.8](sase-1tz.3.1.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| chezmoi | [`chezmoi@3623450`](https://github.com/bbugyi200/dotfiles/commit/3623450f650acd403f9a2e35c4ac752b5d77e316) | fix(sase): run telegram outbound routine only on athena | [sase-1tz.3.1.8](sase-1tz.3.1.8.md) | 2026-11-20 09:31:54 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.3.1.8][1] | Need phase scope and design file | 2 |
| read-by | [agent:sase-1tz.3.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.8/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.land/README.md

<!-- sase:referenced-by:end -->
