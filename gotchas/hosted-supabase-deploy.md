---
type: gotcha
---
# Hosted Supabase deploy

**Symptom (would be):** production gets the seed's known test keys, or Visitor Pass / phone-reuse checks silently break.
**Cause:** the local seed contains known HMAC keys; `supabase config push` would overwrite hosted settings; phone numbers are stored as hashes keyed by Vault `phone_hash_key`.
**Fix:** follow repo `docs/deploy-checklist.md` — create Vault `phone_hash_key` and `access_code_key` on the hosted project, create access codes as the checklist says.
**Don't:** run `config push`, deploy `seed.sql`, or rotate `phone_hash_key` without re-hashing stored phone hashes.
