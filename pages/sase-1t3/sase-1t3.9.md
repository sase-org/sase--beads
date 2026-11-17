# Bead: sase-1t3.9 — Post-storm GC census and heap-owner attribution

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.9` · **Size:** medium
**Created:** 2026-11-16 07:57:55 EST · **Closed:** 2026-11-17 12:17:42 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

heap-census: soak a separate TUI instance with the GC census at about 10 min and 2 h, then record a ranked list of surviving heap owners with code anchors for the heap-diet phases. Coordinate with sase-1sl.4.

## Notes

[2026-11-17T11:14:33Z · sase-1t3.9] SOAK STARTED: dedicated tmux session sase-1t3-9-census, pid 3987386, app_instance_id a428c9ee, Python 3.14.7, HEAD 694cdec86b (storm-hotfix ancestor), SASE_TUI_GC_CENSUS=1, logs /home/bryan/.sase/perf/sase-1t3.9/gc_census_20261117T111346Z/. Live TUI pid 3161729 left untouched. Census tooling now emits watchlist, shallow bytes, and known_caches. First idle census ~10 min, soak through ~2 h.

[2026-11-17T11:17:40Z · sase-1t3.9] SOAK RELAUNCHED after executor-gauge bind fix: tmux sase-1t3-9-census pid 4050454 instance d5ac2b89 logs /home/bryan/.sase/perf/sase-1t3.9/gc_census_20261117T111640Z/. First heartbeat RSS 1.24 GB, allocated_blocks 7.13M, default_executor 32 workers/16 threads/queue 0/not saturated. Python 3.14.7, HEAD 694cdec86b, census on, live TUI 3161729 untouched. Prior attempt a428c9ee discarded.

[2026-11-17T12:32:39Z · sase-1t3.9] Relaunched post-storm census soak after first instance died at ~46 min. Dead: PID 4050454 instance d5ac2b89 dir gc_census_20261117T111640Z (10 min sample intact: census@683s ArtifactFile 47466 FIFOCache 45933 RSS~2.3GB). New: tmux sase-1t3-9-census PID 2450990 instance 2e14b925 dir /home/bryan/.sase/perf/sase-1t3.9/gc_census_20261117T123124Z started 20261117T123124Z; first heartbeat workers=32 threads=18 queue=0 RSS 1.23GB. Do not kill live TUI restart-service PID 1556497. Need 2h sample from the new instance before close.

[2026-11-17T14:58:02Z · sase-1t3.9--1] SOAK RELAUNCH #3 for true 2h sample. 2e14b925/PID 2450990 died at ~70.5 min with exit_code=0 (last hb 4230s, last census ~65 min, RSS 3.22GB, FIFOCache 91405, ArtifactFile 47555, AgentArtifactRecordWire 0, gen-2 p95 1.87s, workers=32). 10 min sample remains d5ac2b89 census@683s. New: tmux sase-1t3-9-census PID 1706747 instance 39893a35 dir /home/bryan/.sase/perf/sase-1t3.9/gc_census_20261117T145641Z started 20261117T145641Z rev 4adc535e27; first hb workers=32 threads=16 queue=0 RSS 1.42GB. Durability: trap HUP, remain-on-exit, keepalive sleep pane, tmux 200x50, agent env scrubbed. Do not kill live TUI restart-service PID 1556497. Need 2h census from 39893a35 before close.

[2026-11-17T17:17:25Z · sase-1t3.9--2] CENSUS COMPLETE: 10 min + 2 h idle GC census on dedicated soaks. Ranked owners posted on parent sase-1t3. Cross-ref on sase-1sl.4 (status unchanged). DECISIONS honored: hotfix_reinstall=yes, trust_ack_compat=cutover, tui_perf_memory=no (tui_perf.md not edited).

Method: SASE_TUI_GC_CENSUS=1, CENSUS_INTERVAL_S=600, Python 3.14.7, isolated tui_stalls.jsonl. Filter rows by app_instance_id + pid. Live tmux session `sase` window `tui` pane 1553355 was never attached or killed.

Soaks:
- Discarded gauge-miss: a428c9ee PID 3987386 dir gc_census_20261117T111346Z (executor gauge missing; _bind_perf_instance ran before the loop existed).
- 10 min sample (valid): d5ac2b89 PID 4050454 dir /home/bryan/.sase/perf/sase-1t3.9/gc_census_20261117T111640Z. Died ~46 min (tmux session vanished, no OOM). Census index 1 @ 683s / nearest hb 619.8s.
- 70 min mid-soak (supporting, not the 2h mark): 2e14b925 PID 2450990 dir /home/bryan/.sase/perf/sase-1t3.9/gc_census_20261117T123124Z. Died ~70.5 min exit_code=0. Last census ~65 min (index 6, nearest hb 3930.5s).
- 2 h sample: 39893a35 PID 1706747 pane 1706745 keepalive 1706798 tmux sase-1t3-9-census dir /home/bryan/.sase/perf/sase-1t3.9/gc_census_20261117T145641Z started 20261117T145641Z rev 4adc535e27. Durability: trap HUP, remain-on-exit, keepalive sleep pane, tmux 200x50, agent env scrubbed. Alive at collection (elapsed 2h17m). Last hb uptime 8141.2s. 14 censuses, 28 heartbeats. Nearest-2h census index 11 @ 6937s. First census with uptime>=7000s: index 12 @ 7539s. Last census index 13 @ 8141s.

10 min (d5ac2b89 census 1 @ 683s): RSS 2.337 GB, allocated_blocks 8,191,127, survivors 758,359 / 92.03 MB, garbage 243,284 / 42.41 MB. Top: list 267,581; PosixPath 96,071; dict 84,054 / 25.7 MB; DirEntryInfo 72,515; ArtifactFile 47,466; FIFOCache 45,933; NotificationPlusOne 22,368; AgentCatalogLinkFacets 17,832. Watch: ArtifactFile 47,466 (0 at t0); ArtifactReadEvent 0 live / cache 13,566; AgentArtifactRecordWire 0; FIFOCache 9,988→45,933; BeadTouch 7,332; MemoryReadEvent 6,262; Agent 1,808. Executor 32/16/0/false. That soak's gen-2 (n=44 over ~46 min): p50=1.068s p95=1.407s max=1.928s.

70 min (2e14b925 last census ~65 min): RSS 3.220 GB, allocated_blocks 9,008,370, survivors 1,333,033 / 192.26 MB. Top: list 392,664; dict 347,842 / 98.12 MB; PosixPath 141,079; FIFOCache 91,405; DirEntryInfo 77,053; ArtifactFile 47,555; Segment 42,791; AgentCatalogLinkFacets 17,852; NotificationPlusOne 16,212; ArtifactReadEvent 13,584 live. Watch: Agent 2,185; AceRowHandle 2,197; AgentArtifactRecordWire 0; BeadTouch 7,339; MemoryReadEvent 6,277. known_caches: ARTIFACT_SNAPSHOT_CACHE 2/8 records=485; index rows=47,525; artifact_reads 13,584; memory_reads 6,276; bead_touches 0. gen-2 n=65 p50=1.159s p95=1.871s max=2.662s. Executor 32/18/0/false.

2 h (39893a35 census 11 @ 6937s): RSS 3.652 GB, allocated_blocks 13,042,356, survivors 1,748,928 / 271.60 MB, garbage 129,615 / 37.95 MB, census_duration 5.122s. Top: list 684,723 / 78.9 MB; dict 378,739 / 128.3 MB; PosixPath 277,559 / 28.9 MB; DirEntryInfo 85,957 / 5.5 MB; tuple 56,285 / 9.4 MB; ArtifactFile 47,658 / 2.29 MB; NotificationPlusOne 28,547; MemoryReadEvent 23,457; AgentCatalogLinkFacets 17,889; BeadTouch 16,307; SkillUseEvent 11,402; FIFOCache 7,709. Watch: Agent 2,816; AceRowHandle 4,044; ArtifactReadEvent 146 live; AgentArtifactRecordWire (agent_scan_wire) 0; records-module AgentArtifactRecordWire 1,217 in top (transient). known_caches: SNAPSHOT 8/8 records=812; index rows=47,625; artifact_reads 27,587 (sase 27,441 + tailnet 146); memory_reads 23,457; bead_touches 0; glossary 357; skill_uses 11,397. Across soak: RSS 1.416–3.652 GB (last 3.012 GB); blocks 8.087M–15.537M; gen-2 n=131 p50=1.285s p95=2.030s max=2.470s sum=171.55s; executor 32/16/0/false all 28 heartbeats. First heartbeat: RSS 1.416 GB, blocks 8,086,536, workers=32.

Parsed dump: /tmp/sase-1t3.9-census-2h-39893a35.json. Combined 10 min + 70 min dump: /tmp/sase-1t3.9-census-samples.json.

Verification: census tooling already in 4adc535e27. just check ToolRun bc35f3b8febac02bae0373d7c23bfaa8 succeeded (scoped tests 94m); no files changed after that run, so check was not re-run. Tree clean. sase bead epic-symbols sase-1t3.9 returned entries=[]. Dedicated soak session sase-1t3-9-census / PID 1706747 killed after collection. Live TUI pane 1553355 left running.

PROPOSED FOLLOW-UP: CENSUS_WATCHLIST still names sase.core.agent_scan_wire.AgentArtifactRecordWire (always 0 live); gc.get_objects() reports sase.core.agent_scan_wire_records.AgentArtifactRecordWire (transient 0–1,217). Point the watchlist at the defining module.

PROPOSED FOLLOW-UP: Dedicated soaks without keepalive exited cleanly at ~46 min (d5ac2b89) and ~70.5 min (2e14b925), no OOM. 39893a35 reached 2h16m with trap HUP + remain-on-exit + keepalive pane. If another multi-hour census soak is needed, use that durability recipe.

PROPOSED FOLLOW-UP: NotificationPlusOne grows 16k→28k over a 2h idle soak and is outside slim-list-rows / bounded-log-caches as written.

PROPOSED FOLLOW-UP: SkillUseEvent 11.4k live matches _skill_uses_snapshot_cache; same whole-file pattern as memory reads, not named in the sase-1t3.11 phase text.

PROPOSED FOLLOW-UP: BeadTouch 16,307 live while _bead_touches_snapshot_cache.event_total=0 — sase-1t3.11 should find the real owner rather than assuming that cache.

[2026-11-17T17:17:42Z · sase-1t3.9--2] Closed sase-1t3.9 after a dedicated post-storm GC census reached both idle marks. Ranked owners are on parent sase-1t3; sase-1sl.4 got a cross-ref only and stays in_progress. Parent epic sase-1t3 stays open.

10 min (d5ac2b89 PID 4050454, gc_census_20261117T111640Z census@683s, RSS 2.34 GB): ArtifactFile 47,466, FIFOCache 45,933, list 267,581, dict 84,054, PosixPath 96,071, NotificationPlusOne 22,368, AgentCatalogLinkFacets 17,832, ArtifactReadEvent 0 live (cache 13,566), AgentArtifactRecordWire 0.

2 h (39893a35 PID 1706747, gc_census_20261117T145641Z census@6937s nearest 7200s, RSS 3.65 GB; last census 8141s): dict 378,739 / 128 MB, list 684,723 / 79 MB, PosixPath 277,559, ArtifactFile 47,658 (stable = index 47,625), NotificationPlusOne 28,547, MemoryReadEvent 23,457 (= cache), AgentCatalogLinkFacets 17,889, BeadTouch 16,307 (cache empty), SkillUseEvent 11,402, FIFOCache 7,709. RSS 1.42–3.65 GB, allocated_blocks 8.09M–15.54M, gen-2 n=131 p50=1.285s p95=2.030s, executor 32/16/0/false the whole soak. 70 min soak 2e14b925 (FIFOCache 91,405, ArtifactFile 47,555, RSS 3.22 GB) is supporting mid-soak evidence.

sase-1t3.10: slim dict/list/tuple + AgentCatalogLinkFacets, cap ARTIFACT_SNAPSHOT_CACHE at one generation, treat FIFOCache as a growth owner. sase-1t3.11 census order: ArtifactFile index, MemoryReadEvent cache, BeadTouch (find the real materializer), PosixPath/DirEntryInfo walks, ArtifactReadEvent snapshot cache.

Verified: tooling commit 4adc535e27, just check ToolRun bc35f3b8febac02bae0373d7c23bfaa8 (no files changed after; check not re-run). epic-symbols sase-1t3.9 leftovers none. Dedicated tmux sase-1t3-9-census / PID 1706747 killed after collection; live session sase window tui pane 1553355 left running.

## Dependencies

- **Depends on:** [sase-1t3.1](sase-1t3.1.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.10](sase-1t3.10.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.11](sase-1t3.11.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.2](sase-1t3.2.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.3](sase-1t3.3.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.5](sase-1t3.5.md) ✓ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.9.md) | [sase-1t3.9](sase-1t3.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4adc535`](https://github.com/sase-org/sase/commit/4adc535e273922761deddae398eedd2005015145) | feat(tui): attribute post-storm heap owners in the GC census | [sase-1t3.9](sase-1t3.9.md) | 2026-11-17 08:04:32 EST |
