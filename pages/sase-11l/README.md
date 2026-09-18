# Bead: sase-11l — %hold: a reverse-%wait admission barrier

[Bead Pages](../README.md) / sase-11l

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ls](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ls.md) · **Assignee:** `sase-11l.land`
**Created:** 2026-09-15 22:45:58 EDT
**Plan:** [202609/hold\_directive.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_directive.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/hold_directive.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/hold_directive.md

<!-- sase:links:end -->

## Description

A launch (agent or stand-alone proc) can arm a durable, TTL-bounded, fail-open hold that makes selected WAITING/QUEUED agents and un-dispatched procs wait for it to settle — never touching running work — with a first-class CLI, a %hold prompt directive, ACE/LSP completion, and TUI visibility.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-11l.1](sase-11l.1.md) | Allow %queue capacity on proc units | ✓ closed | large | 2026-09-15 | 1 | 2 |
| [sase-11l.10](sase-11l.10.md) | Remove the agent\_holds flag and close out | ◐ in_progress | small | 2026-09-15 | 1 | 0 |
| [sase-11l.2](sase-11l.2.md) | Rust hold-record store and bindings | ✓ closed | large | 2026-09-15 | 1 | 2 |
| [sase-11l.3](sase-11l.3.md) | hold-barrier blocker at runner-slot admission | ✓ closed | large | 2026-09-15 | 1 | 2 |
| [sase-11l.4](sase-11l.4.md) | sase agent hold command group | ✓ closed | large | 2026-09-15 | 1 | 1 |
| [sase-11l.5](sase-11l.5.md) | The %hold prompt directive | ✓ closed | large | 2026-09-15 | 1 | 0 |
| [sase-11l.6](sase-11l.6.md) | Completion and LSP for %hold | ✓ closed | medium | 2026-09-15 | 1 | 2 |
| [sase-11l.7](sase-11l.7.md) | Hold un-dispatched proc units | ✓ closed | medium | 2026-09-15 | 1 | 2 |
| [sase-11l.8](sase-11l.8.md) | TUI, doctor, and deadlock visibility | ✓ closed | medium | 2026-09-15 | 1 | 1 |
| [sase-11l.9](sase-11l.9.md) | Hood selector for %wait | ✓ closed | medium | 2026-09-15 | 1 | 2 |

## Lineage

```mermaid
flowchart TD
    n0["sase-11l: %hold: a reverse-%wait admission barrier [in_progress]"]
    n1["sase-11l.1: Allow %queue capacity on proc units [closed]"]
    n2["sase-11l.10: Remove the agent_holds flag and close out [in_progress]"]
    n3["sase-11l.2: Rust hold-record store and bindings [closed]"]
    n4["sase-11l.3: hold-barrier blocker at runner-slot admission [closed]"]
    n5["sase-11l.4: sase agent hold command group [closed]"]
    n6["sase-11l.5: The %hold prompt directive [closed]"]
    n7["sase-11l.5.1: The %hold prompt directive [closed]"]
    n8["sase-11l.5.1.1: Parse %hold everywhere behind agent_holds [closed]"]
    n9["sase-11l.5.1.2: Arm holds at launch submission [closed]"]
    n10["sase-11l.5.1.2.1: Arm %hold at launch submission [closed]"]
    n11["sase-11l.5.1.2.1.1: Rust hold store, launch armer, and wire support [closed]"]
    n12["sase-11l.5.1.2.1.2: Python hold facade and launch-hold primitives [closed]"]
    n13["sase-11l.5.1.2.1.3: Pre-arm typed plans and follow units to dispatch [closed]"]
    n14["sase-11l.5.1.2.1.4: Arm or rebind in the agent runner bootstrap [closed]"]
    n15["sase-11l.5.1.3: Preview captures and confirm broad holds [closed]"]
    n16["sase-11l.6: Completion and LSP for %hold [closed]"]
    n17["sase-11l.7: Hold un-dispatched proc units [closed]"]
    n18["sase-11l.8: TUI, doctor, and deadlock visibility [closed]"]
    n19["sase-11l.9: Hood selector for %wait [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n6 --> n7
    n7 --> n8
    n7 --> n9
    n9 --> n10
    n10 --> n11
    n10 --> n12
    n10 --> n13
    n10 --> n14
    n7 --> n15
    n0 --> n16
    n0 --> n17
    n0 --> n18
    n0 --> n19
    n1 -.-> n6
    n3 -.-> n4
    n4 -.-> n5
    n5 -.-> n6
    n5 -.-> n17
    n5 -.-> n18
    n6 -.-> n2
    n6 -.-> n16
    n8 -.-> n9
    n8 -.-> n15
    n11 -.-> n12
    n12 -.-> n13
    n12 -.-> n14
    n16 -.-> n2
    n16 -.-> n19
    n17 -.-> n2
    n18 -.-> n2
    n19 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.1.md) | [sase-11l.1](sase-11l.1.md) | 2 |
| [bbugyi200.athena.sase-11l.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.10/README.md) | [sase-11l.10](sase-11l.10.md) | 0 |
| [bbugyi200.athena.sase-11l.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.2/README.md) | [sase-11l.2](sase-11l.2.md) | 2 |
| [bbugyi200.athena.sase-11l.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.3.md) | [sase-11l.3](sase-11l.3.md) | 2 |
| [bbugyi200.athena.sase-11l.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.4.md) | [sase-11l.4](sase-11l.4.md) | 1 |
| [bbugyi200.athena.sase-11l.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.md) | [sase-11l.5](sase-11l.5.md) | 0 |
| [bbugyi200.athena.sase-11l.5.1.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.1.1.md) | [sase-11l.5.1.1](sase-11l.5.1.1.md) | 2 |
| [bbugyi200.athena.sase-11l.5.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.1.2.md) | [sase-11l.5.1.2](sase-11l.5.1.2.md) | 0 |
| [bbugyi200.athena.sase-11l.5.1.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.5.1.2.1.1/README.md) | [sase-11l.5.1.2.1.1](sase-11l.5.1.2.1.1.md) | 1 |
| [bbugyi200.athena.sase-11l.5.1.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.5.1.2.1.2/README.md) | [sase-11l.5.1.2.1.2](sase-11l.5.1.2.1.2.md) | 1 |
| [bbugyi200.athena.sase-11l.5.1.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.5.1.2.1.3/README.md) | [sase-11l.5.1.2.1.3](sase-11l.5.1.2.1.3.md) | 0 |
| [bbugyi200.athena.sase-11l.5.1.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.5.1.2.1.4/README.md) | [sase-11l.5.1.2.1.4](sase-11l.5.1.2.1.4.md) | 1 |
| [bbugyi200.athena.sase-11l.5.1.2.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.1.2.1.land.md) | [sase-11l.5.1.2.1](sase-11l.5.1.2.1.md) | 1 |
| [bbugyi200.athena.sase-11l.5.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.1.3.md) | [sase-11l.5.1.3](sase-11l.5.1.3.md) | 1 |
| [bbugyi200.athena.sase-11l.5.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.1.land.md) | [sase-11l.5.1](sase-11l.5.1.md) | 0 |
| [bbugyi200.athena.sase-11l.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.6/README.md) | [sase-11l.6](sase-11l.6.md) | 2 |
| [bbugyi200.athena.sase-11l.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.7/README.md) | [sase-11l.7](sase-11l.7.md) | 2 |
| [bbugyi200.athena.sase-11l.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.8/README.md) | [sase-11l.8](sase-11l.8.md) | 1 |
| [bbugyi200.athena.sase-11l.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.9/README.md) | [sase-11l.9](sase-11l.9.md) | 2 |
| [bbugyi200.athena.sase-11l.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.land/README.md) | [sase-11l](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4ef449d`](https://github.com/sase-org/sase-core/commit/4ef449de9fc232402fc1eee72dbd5b6199438bf7) | feat(agent-hold): add durable hold store | [sase-11l.2](sase-11l.2.md) | 2026-09-15 23:17:28 EDT |
| sase | [`b6b11f2`](https://github.com/sase-org/sase/commit/b6b11f21556bccae2efcd8c32a161d4171614528) | feat(agent-launch): admit queued proc units | [sase-11l.1](sase-11l.1.md) | 2026-09-15 23:58:04 EDT |
| sase-core | [`sase-core@20f1dce`](https://github.com/sase-org/sase-core/commit/20f1dce477880f97995eb8ea87fcd48aa0515fc4) | feat(agent-launch): parse proc queue directives | [sase-11l.1](sase-11l.1.md) | 2026-09-16 00:01:16 EDT |
| sase-core | [`sase-core@a7d5882`](https://github.com/sase-org/sase-core/commit/a7d588263e5a1c69f49dddbb2f72a138382b53a5) | fix(agent-hold): enforce hold boundary semantics | [sase-11l.2](sase-11l.2.md) | 2026-09-16 00:24:24 EDT |
| sase | [`c174144`](https://github.com/sase-org/sase/commit/c1741443d96c51dc8144a2209e1f1f6c457db45e) | feat(agent-hold): enforce hold barriers in runner admission | [sase-11l.3](sase-11l.3.md) | 2026-09-16 10:30:27 EDT |
| sase-core | [`sase-core@67dc596`](https://github.com/sase-org/sase-core/commit/67dc596d1edb974b4f6b45625f2fc76f950f62b3) | feat(runner-capacity): apply agent hold barriers | [sase-11l.3](sase-11l.3.md) | 2026-09-16 10:33:32 EDT |
| sase | [`520c7db`](https://github.com/sase-org/sase/commit/520c7dbf419d3847f941c0a1cb47e384b4f0cf6d) | feat(agent-hold): add the sase agent hold command group | [sase-11l.4](sase-11l.4.md) | 2026-09-16 13:02:32 EDT |
| sase | [`b5f51b1`](https://github.com/sase-org/sase/commit/b5f51b192e5995a55d6a0571cf1aad7f6c394906) | feat(agent): hold undispatched procs before dispatch | [sase-11l.7](sase-11l.7.md) | 2026-09-16 15:08:03 EDT |
| sase-core | [`sase-core@4ec5fca`](https://github.com/sase-org/sase-core/commit/4ec5fca725227c0e8a060189a40b42afa42d5e51) | feat(agent): expose proc hold admission facts | [sase-11l.7](sase-11l.7.md) | 2026-09-16 15:11:59 EDT |
| sase | [`82a37b0`](https://github.com/sase-org/sase/commit/82a37b0c02100a37083217c21a6a4ee4a30eb2dc) | feat(xprompt): add hold directive surface | [sase-11l.5.1.1](sase-11l.5.1.1.md) | 2026-09-16 15:26:25 EDT |
| sase | [`09cb008`](https://github.com/sase-org/sase/commit/09cb008b22ea90adbf87cdae583fd31491e6ee67) | feat(agent-hold): surface hold visibility in the TUI, doctor, and admission notifications | [sase-11l.8](sase-11l.8.md) | 2026-09-16 15:32:33 EDT |
| sase-core | [`sase-core@a685c07`](https://github.com/sase-org/sase-core/commit/a685c0725fba4b6391bfb8541a06f935480253d4) | feat(core): add hold directive contracts | [sase-11l.5.1.1](sase-11l.5.1.1.md) | 2026-09-16 15:40:45 EDT |
| sase-core | [`sase-core@f93ed13`](https://github.com/sase-org/sase-core/commit/f93ed139f4b1295d7c508a90cf822be9f229e75c) | feat(agent-hold): add launch armer core support | [sase-11l.5.1.2.1.1](sase-11l.5.1.2.1.1.md) | 2026-09-16 17:09:25 EDT |
| sase | [`43c8721`](https://github.com/sase-org/sase/commit/43c87210f5821663c21d9198865f52f02473d009) | feat(agent-hold): preview pending %hold captures and confirm broad holds | [sase-11l.5.1.3](sase-11l.5.1.3.md) | 2026-09-16 18:38:38 EDT |
| sase | [`02f0fd3`](https://github.com/sase-org/sase/commit/02f0fd3893f57267a0bef8f6f69fc23adc89c675) | feat(agent-hold): add launch-hold facade primitives and launch armer kind | [sase-11l.5.1.2.1.2](sase-11l.5.1.2.1.2.md) | 2026-09-17 07:28:41 EDT |
| sase | [`88175f3`](https://github.com/sase-org/sase/commit/88175f34fc8b9431bb3e3a89ac56a620137b8a2a) | feat(agent-hold): arm bootstrap holds | [sase-11l.5.1.2.1.4](sase-11l.5.1.2.1.4.md) | 2026-09-17 08:36:56 EDT |
| sase | [`ff08843`](https://github.com/sase-org/sase/commit/ff088437985ffa0f679ae59406280202f58b9279) | feat(agent): pre-arm typed launch holds | [sase-11l.5.1.2.1](sase-11l.5.1.2.1.md) | 2026-09-17 14:53:35 EDT |
| sase | [`f852cdc`](https://github.com/sase-org/sase/commit/f852cdcbba7a5901c386ec12bd8190d621a9f3cf) | feat(ace): complete hold directive completions | [sase-11l.6](sase-11l.6.md) | 2026-09-18 07:52:28 EDT |
| sase-core | [`sase-core@0b4beed`](https://github.com/sase-org/sase-core/commit/0b4beedb42061eb9ba5fafaafee7fcc05decc279) | feat(editor): support hold completion roles | [sase-11l.6](sase-11l.6.md) | 2026-09-18 08:13:39 EDT |
| sase | [`c8c842f`](https://github.com/sase-org/sase/commit/c8c842fb3e8f7e042e4e1543341f2be95ee77169) | feat(wait): support hood selectors | [sase-11l.9](sase-11l.9.md) | 2026-09-18 10:05:11 EDT |
| sase-core | [`sase-core@549b168`](https://github.com/sase-org/sase-core/commit/549b168603d0700cdee71d068905dc70987cf7c3) | feat(wait): add hood directive contract | [sase-11l.9](sase-11l.9.md) | 2026-09-18 10:09:02 EDT |
