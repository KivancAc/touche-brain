---
type: ethos
---
# Ethos — Touche

Rules Claude follows in this project. Add a rule whenever the owner states one, with the date and why.

## Owner
Kivanç (KA Ventures) — product owner. Not an experienced developer: Claude is the safety net. Explain in plain words; talk in Turkish unless asked otherwise.

## Working rules
- **Models:** the main session codes on Opus 5.5; design, code and security review go to the Fable 5.2 agents (`architect`, `code-reviewer`, `security`). Never review your own code inline and call it reviewed.
- **Branch → test → merge.** One branch per change; "done" means built, tested and seen working. Merge to `main` only when sure.
- **Ask first** before anything hard to undo or outward-facing: push, deploy, migrations on real data, messages or e-mails to anyone, paid services.
- **Never invent business values** (prices, limits, company names, providers). If it is not decided, ask and record the answer in the repo's `docs/spec.md`.
- **Warn proactively** about risk: legal/privacy, cost, security, anything that affects real users.
- **Fix what was asked.** No scope creep; read the whole flow before proposing a fix.
