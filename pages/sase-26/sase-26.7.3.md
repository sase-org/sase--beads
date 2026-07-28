# Bead: sase-26.7.3 — Phase 3: Push-Hint Wire Contract And Subscription Endpoints

[Bead Pages](../README.md) / [sase-26.7](sase-26.7.md) / sase-26.7.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-26.7.3`
**Created:** 2026-05-07 00:01:08 UTC
**Plan:** [202605/mobile\_gateway\_epic\_7.md](https://github.com/sase-org/sase--plans/blob/main/202605/mobile_gateway_epic_7.md)

## Notes

Implemented push-hint wire contract and authenticated subscription endpoints in ../sase-core. Added provider/category/subscription/hint wire records, deterministic event-to-hint mapping, atomic push subscription storage under mobile_gateway/push_subscriptions.json, GET/POST/DELETE /api/v1/session/push-subscriptions routes, duplicate-token update semantics, revoke behavior, validation, auth tests, no provider-token audit leakage tests, and contract snapshot updates. Synced the Android API contract snapshot and expected route list in ../sase-android. Verified with cargo fmt --all -- --check, cargo test -p sase_gateway, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, ANDROID_HOME=/home/bryan/Android/Sdk ./gradlew testDebugUnitTest --tests org.sase.mobile.data.api.MobileApiContractTest, and ANDROID_HOME=/home/bryan/Android/Sdk ./gradlew lintDebug assembleDebug. Full Android testDebugUnitTest was attempted but failed in unrelated pre-existing foreground connected mode tests from other in-progress Android work: stopAfterHostUnavailableUsesSameStopPath, stopPersistsDisabledAndStopsService, startUntilStoppedPersistsEnabledAndStartsService.

## Dependencies

- **Depends on:** [sase-26.7.1](sase-26.7.1.md) ✓
- **Blocks:** [sase-26.7.4](sase-26.7.4.md) ✓
- **Blocks:** [sase-26.7.5](sase-26.7.5.md) ✓
- **Blocks:** [sase-26.7.6](sase-26.7.6.md) ✓
