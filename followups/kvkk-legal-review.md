---
type: followup
created: 2026-11-14
priority: high
status: pending
owner: kivanc (lawyer)
source: repo docs/status.md Known issues 3, 13, 18
---
# KVKK / GDPR legal review — blocks real user data

Must be cleared **before storing any real user data, including the 100-person closed group**:
- Turkish representative, VERBIS registration, legal basis for cross-border transfer to every processor (Supabase EU, Vercel, Sentry, RevenueCat, Expo push, Didit) — Known issue 3.
- Does orientation/position need a separate explicit consent? — Known issue 13.
- Server-sent e-mail invites under law 6563 / İYS — Known issue 18 (feature flag stays off until then).
- Legal pages are drafts (spec open decision 4).
- Biometric consent text for ID/selfie verification (Didit: 1:1 face match, liveness, 1:N duplicate search, retention): engineering writes a draft, the final text comes from this review (owner agreed 2026-11-14). Also: both routes are biometric — is consent "freely given" without a non-biometric alternative? Visitor identity-key hashes need a privacy-notice line and a retention period.
