---
type: architecture
updated: 2026-11-14
---
# Architecture — Touche

Rules and detail: repo `CLAUDE.md` (Stack, Architecture) and `docs/decisions/2026-11-14-stack.md`.

```mermaid
graph LR
  M[apps/mobile<br/>Expo iOS + Android] --> DB[(Supabase EU<br/>Postgres + PostGIS<br/>RLS + RPCs)]
  A[apps/admin<br/>Next.js on Vercel] -->|admin_* functions + audit log| DB
  W[apps/web<br/>Next.js on Vercel<br/>installs only] -->|install SMS| EF
  EF[Edge Functions] --> DB
  RC[RevenueCat] -->|webhook| EF
  DI[Didit<br/>ID / selfie] -->|webhook| EF
  EF -->|send| SMS["[SMS SAĞLAYICI]"]
  S[packages/shared<br/>types, Zod, i18n, tokens] -.-> M & A & W
```

Business rules are enforced in Postgres (radius, mode separation, quota, Premium from the `premium_grants` ledger); clients only display results.
