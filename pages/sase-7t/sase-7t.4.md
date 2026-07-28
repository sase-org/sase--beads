# Bead: sase-7t.4 — Telegram kill-selection callback data hardening

[Bead Pages](../README.md) / [sase-7t](README.md) / sase-7t.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-7t.4`
**Created:** 2026-07-19 23:47:09 UTC
**Plan:** [202607/chop\_lifecycle\_fixes\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202607/chop_lifecycle_fixes_v2.md)

## Description

'Telegram kill-selection callback data hardening' section: replace raw agent names in /kill inline-keyboard callback data with short persisted keys so long clan member names cannot exceed Telegram's 64-byte limit, and keep one bad button from crashing the whole tg_inbound cycle.

## Notes

COMMIT: 5f76632
