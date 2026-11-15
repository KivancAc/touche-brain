---
type: thread
name: main
status: active
started: 2026-11-14
last_touched: 2026-11-15
---
# Thread: building Touche to the closed-group launch

## Goal
100 verified members in Istanbul using the app through TestFlight / Play closed testing, all Premium (spec rule 11), with real data only after the KVKK review.

## Current state
Stage 1 (sign-up and onboarding) at 6/8. Task 1.3 verification done (583 pgTAP, 76 Deno, integration 26/26) on `stage1/1.3-verification`, pushed; main still 3dfbc04 — owner's OK pending for the fast-forward. Database side of sign-up is done (members, access codes, Premium ledger, Visitor Pass, profiles, health; ~300 pgTAP tests). Mobile foundation done and boots in the iOS simulator. `main` = `stage1/1.4-mobile-foundation` (fast-forwarded 2026-11-14), backed up to private GitHub `KivancAc/touche`.

## Next steps
1. Arda (project manager from 2026-11-15, [[people/arda]]) answers [[followups/questions-for-arda]]: e2e method, Android, main merge, defaults.
2. Task 1.6 (log-in) — built while waiting for Arda: reviewed (architect, code-reviewer, security, test-writer), 290 mobile / 652 pgTAP / both smoke scripts green; branch `stage1/1.6-login` (28d0773) LOCAL ONLY, based on the unmerged 1.5 branch. Remaining: simulator check (needs A2) and Android (A3). Push when the owner says so.
3. Task 1.5 — built, reviewed, tested (247 mobile / 106 shared), status updated; branch `stage1/1.5-signup-screens` pushed (8356d94). Remaining: member-screen e2e (Maestro or owner's manual list; computer use isn't available in the VS Code session) and Android check.

## Blockers
None for building. Real users blocked by [[followups/kvkk-legal-review]].

## Files in flight
Repo `docs/plans/task-1.5-signup-screens.md`, `docs/status.md`, `apps/mobile/src/`.
