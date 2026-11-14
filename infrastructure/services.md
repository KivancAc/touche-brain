---
type: infrastructure
category: service
status: planned
owner: kivanc
access: TODO
---
# Services (Touche)

From the stack decision (repo `docs/decisions/2026-11-14-stack.md`). As of 2026-11-14 everything runs locally (`pnpm db:start`); **no hosted environment has been confirmed in the brain yet.** When an account is created, split it into its own file here: who owns it, region, where the keys are kept (never the keys).

| Service | Use | Account status |
|---|---|---|
| Supabase (EU region) | Database, auth, storage, Edge Functions | unknown — ask Kivanç |
| Vercel | Website + admin panel | unknown |
| Expo / EAS | Mobile builds, submit, OTA updates | unknown |
| Apple Developer + App Store Connect | iOS, TestFlight, in-app purchase | unknown |
| Google Play Console | Android, closed testing, billing | unknown |
| RevenueCat | In-app purchase handling | unknown |
| Didit | ID / selfie verification (closed group) | unknown — vetting pending ([[followups/didit-vetting]]) |
| Sentry | Error monitoring | unknown |
| SMS provider | OTP + install SMS | not chosen (`[SMS SAĞLAYICI]`) |
| E-mail provider | E-mail invites (flag off) | not chosen (`[E-POSTA SAĞLAYICI]`) |
| Domain | `touche.com`? | not confirmed (spec open decision 4) |

Hosted Supabase: follow repo `docs/deploy-checklist.md`; see [[gotchas/hosted-supabase-deploy]].
