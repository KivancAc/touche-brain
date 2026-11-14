---
type: ethos
---
# Ethos — Touche

Rules Claude follows in this project. Add a rule whenever the owner states one, with the date and why.

## Owner
[[people/kivanc]] — product owner. Not an experienced developer: Claude is the safety net. Talk in Turkish, explain in plain words; repo docs and brain entries are in English.

## Working rules
- **Models (2026-11-14):** the main session codes on Opus 5.5; design, code and security review go to the Fable 5.2 agents (`architect`, `code-reviewer`, `security`). Never review your own code inline and call it reviewed.
- **Branch → test → merge.** One branch per change; "done" means built, tested and seen working. Merge to `main` only when sure.
- **Ask first** before anything hard to undo or outward-facing: push, deploy, hosted Supabase changes, migrations on real data, messages or e-mails to anyone, paid services.
- **Never invent business values.** Bracketed values in `docs/spec.md` (`[FİYAT]`, `[SMS SAĞLAYICI]` …) stay bracketed until the owner decides; record the answer in the spec with "(product owner, date)".
- **Engineering defaults are marked.** When Claude fills a gap the owner did not decide, the spec says *(engineering default)* so the owner can overrule it.
- **Privacy first.** Touche handles sexual orientation (Rainbow/Straight mode) and health data — special-category data under KVKK/GDPR. Warn proactively about anything that could leak it (logs, analytics, push, third parties, deep links).
- **Warn proactively** about legal, cost and security risk, and anything that affects real users.
- **Fix what was asked.** No scope creep; read the whole flow before proposing a fix.
