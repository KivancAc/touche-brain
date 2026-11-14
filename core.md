---
type: core
updated: 2026-11-14
---
# Touche Brain — Core

Entry point. Every session reads this first. One-line links only; detail lives in the linked files.

## Me & how we work
- [[ethos]] — Kivanç's rules: Opus codes / Fable reviews, ask before outward actions, never invent bracketed values, privacy first
- [[CLAUDE]] — how this brain works (brain vs repo: what goes where)
- [[people/kivanc]] — product owner, beginner developer

## Product
- [[roadmap]] — Stage 1 sign-up at 5/8; closed group of 100 in Istanbul next
- [[architecture]] — Expo + Supabase EU + Next.js; rules live in Postgres
- Repo: spec `docs/spec.md` · status + known issues `docs/status.md` · decisions `docs/decisions/` · plans `docs/plans/`

## ⚠️ Pending follow-ups
- 🔴 **high** — [[followups/merge-and-back-up-branches]] — no git remote; `main` 17 commits behind the working branch. Created 2026-11-14.
- 🔴 **high** — [[followups/kvkk-legal-review]] — blocks storing any real user data, incl. the closed group. Created 2026-11-14.
- 🟡 **medium** — [[followups/didit-vetting]] — data location, DPA, Turkish ID support, pricing. Created 2026-11-14.
- 🟡 **medium** — [[followups/send-notification-sounds]] — owner never heard the six samples. Created 2026-11-14.
- 🟡 **medium** — [[followups/open-product-decisions]] — bracketed values, config starting values, AI agents scope, admin screen count. Created 2026-11-14.

## Active threads
- [[threads/main]] — building to the closed-group launch

## Gotchas
- [[gotchas/hosted-supabase-deploy]] — never `config push`, never deploy the seed, never rotate `phone_hash_key`
- [[gotchas/design-handoff-files]] — `.dc.html` needs the design runtime; export's CLAUDE.md → HANDOFF.md

## Infrastructure
- [[infrastructure/services]] — planned services; no hosted environment confirmed yet

## People
- [[people/kivanc]]
