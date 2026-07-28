# Bead: sase-27.5 — Phase 5: Android Typed-Colon Cursor Detector

[Bead Pages](../README.md) / [sase-27](README.md) / sase-27.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-27.5`
**Created:** 2026-05-07 01:49:01 UTC
**Plan:** [202605/mobile\_xprompt\_argument\_hints.md](https://github.com/sase-org/sase--plans/blob/main/202605/mobile_xprompt_argument_hints.md)

## Notes

Implemented Android typed-colon xprompt hint detector in ../sase-android. Added pure Kotlin parsing for exact cursor-colon references (#foo:, #!foo:, namespaced slash/__ aliases, !!/?? suffixes) and wired LaunchScreen prompt edits to show hints only for known required-input entries. Covered invalid contexts, unknown refs, plus refs, completed tokens, and non-collapsed selections in XpromptArgHintsTest. Verified with ANDROID_HOME=/home/bryan/Android/Sdk ./gradlew testDebugUnitTest --tests 'org.sase.mobile.ui.launch.*' and ANDROID_HOME=/home/bryan/Android/Sdk ./gradlew testDebugUnitTest.

## Dependencies

- **Depends on:** [sase-27.4](sase-27.4.md) ✓
- **Blocks:** [sase-27.6](sase-27.6.md) ✓
