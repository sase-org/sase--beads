# Bead: sase-1tz.4.1.5 — Resolve sidecar payloads in every reader, then externalize payloads over 8 KB

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.5` · **Size:** medium
**Created:** 2026-11-20 14:00:22 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

blob_adopt: the TUI, Telegram, and mobile readers that need full action_data or note text resolve sidecar references. Then the Python store wrapper externalizes payloads over 8 KB by default, and live oversize rows migrate once.

## Notes

[2026-11-20T23:53:04Z · sase-1tz.4.1.5] blob_adopt pre-install baseline (read-only, 2026-11-20). Payload-byte counts are the sum of compact UTF-8 JSON encodings for each row's action_data and notes; rows_over_8k counts rows whose combined values exceed 8,192 bytes; broken_files counts files entries that no longer exist.

- athena: live_store_bytes=5,123,812; rows=2,252; action_data_and_notes_bytes=3,358,579; rows_over_8k=76; broken_files=452.
- apollo: live_store_bytes=4,187,514; rows=1,709; action_data_and_notes_bytes=3,216,430; rows_over_8k=69; broken_files=352.

After-install repeat command (run on both hosts after deploying the wrapper):

\```sh
for host in athena apollo; do
  ssh "$host" 'python3 -c "import json,pathlib; p=pathlib.Path.home()/\".sase/notifications/notifications.jsonl\"; rows=[json.loads(line) for line in p.read_text(encoding=\"utf-8\").splitlines() if line.strip()]; sizes=[len(json.dumps(row.get(\"action_data\") or {},ensure_ascii=False,separators=(\",\",\":\")).encode())+len(json.dumps(row.get(\"notes\") or [],ensure_ascii=False,separators=(\",\",\":\")).encode()) for row in rows]; print(json.dumps({\"live_store_bytes\":p.stat().st_size,\"rows\":len(rows),\"action_data_and_notes_bytes\":sum(sizes),\"rows_over_8k\":sum(size>8192 for size in sizes),\"broken_files\":sum(1 for row in rows for file in row.get(\"files\",[]) if not pathlib.Path(file).expanduser().exists())}))"'
done
\```

## Dependencies

- **Depends on:** [sase-1tz.4.1.4](sase-1tz.4.1.4.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.5/README.md) | [sase-1tz.4.1.5](sase-1tz.4.1.5.md) | 0 |
