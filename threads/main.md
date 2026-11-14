---
type: thread
name: main
status: active
started: 2026-11-14
last_touched: 2026-11-14
---
# Thread: building Touche to the closed-group launch

## Goal
100 verified members in Istanbul using the app through TestFlight / Play closed testing, all Premium (spec rule 11), with real data only after the KVKK review.

## Current state
Stage 1 (sign-up and onboarding) at 6/8. Task 1.3 verification done (583 pgTAP, 76 Deno, integration 26/26) on `stage1/1.3-verification`, pushed; main still 3dfbc04 — owner's OK pending for the fast-forward. Database side of sign-up is done (members, access codes, Premium ledger, Visitor Pass, profiles, health; ~300 pgTAP tests). Mobile foundation done and boots in the iOS simulator. `main` = `stage1/1.4-mobile-foundation` (fast-forwarded 2026-11-14), backed up to private GitHub `KivancAc/touche`.

## Next steps
1. Owner OK → fast-forward main to `stage1/1.3-verification` and push.
2. Task 1.5 — mobile sign-up screens TR/EN (plan → architect → build); 1.6 — log-in.

## Blockers
None for building. Real users blocked by [[followups/kvkk-legal-review]].

## Files in flight
Repo `docs/plans/stage-1-signup.md`, `docs/status.md`.
