---
type: gotcha
---
# Edge Functions can't see `packages/shared` without the import map

**Symptom:** `functions serve` → `BOOT_ERROR`, "Module not found …/packages/shared/src/index.ts".
**Cause:** the local edge runtime mounts only `supabase/functions` unless an import map points outside it.
**Fix:** every function has `import_map = "./functions/deno.json"` under `[functions.<name>]` in `supabase/config.toml`; run with `pnpm functions:serve` (also loads `supabase/functions/local.env`). Hosted bundling through the same map is still unconfirmed (repo Known issue 23).
**Don't:** copy shared code into `supabase/functions`; don't run a bare `supabase functions deploy` (it would ship `verification-mock`) — use `pnpm functions:deploy`.
