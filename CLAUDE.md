# Touche Brain — Schema

This folder is the persistent memory for **Touche**. Every Claude session in the code repo loads it at start (the code repo's `CLAUDE.local.md` points here). This file teaches the structure; the other files hold the content.

## Brain vs code repo — what goes where
The code repo is the source of truth for the product and the code: `docs/spec.md` (rules), `docs/status.md` (stages, tasks, known issues), `docs/decisions/` (technical and product decisions), `docs/plans/`. **Do not copy those into the brain** — link to them by repo path.
The brain holds what does not belong in a shareable repo, or is not about code:
- how the owner wants to work (`ethos.md`), people, candid notes;
- to-dos that are not code tasks (legal review, sending files to someone, account setup) and agreed follow-ups;
- traps that cost time (`gotchas/`), non-obvious fixes (`fixes/`);
- accounts and services (`infrastructure/`, never secrets);
- conversations the owner relays (`discussions/`), session summaries (`sessions/`).

## Folder layout
- `core.md` — Master catalog. One-line links to everything. Always read on session start.
- `ethos.md` — The owner's working rules for this project. Always read on session start.
- `roadmap.md` — Now / Next / Later in a few lines; detail stays in the repo's `docs/status.md`.
- `architecture.md` — One Mermaid graph of the system; detail stays in the repo's `CLAUDE.md`.
- `decisions/YYYY-MM-DD-<topic>.md` — Only decisions that are not in the repo (business, pricing, partners, private). Sections: Context, Decision, Why, Consequences.
- `gotchas/<short-name>.md` — Recurring or dangerous traps. Sections: Symptom, Cause, Workaround/fix, Don't.
- `fixes/YYYY-MM-DD-<short-name>.md` — Postmortems for non-trivial fixes only (cause non-obvious, obvious fix would be wrong, could recur). Frontmatter: `type: fix`, `date`, `commit`, `tags`.
- `threads/<name>.md` — Long-lived workstreams. Sections: Goal, Current state, Next steps, Blockers, Files in flight. Read first when resuming; update at session end.
- `plans/<name>.md` — Thin index; body links to the canonical plan in the repo. Frontmatter: `name`, `status` (`active`|`done`|`archived`), `started`, `repo_path`.
- `followups/<short-name>.md` — Pending agreed actions. Frontmatter: `created`, `priority` (`high`|`medium`|`low`), `status` (`pending`|`done`|`cancelled`), `owner`, `source`. Listed in `core.md`.
- `sessions/YYYY-MM-DD-<topic>.md` — End-of-session summaries.
- `domain/<concept>.md` — Business and domain knowledge (store rules, legal rules, market facts).
- `people/<name>.md` — Collaborator profiles. Only real people the owner mentions.
- `infrastructure/<resource>.md` — Services and accounts. Frontmatter: `category` (`service`|`account`|`domain`|`repo`|`server`), `status`, `owner`, `access`. **No plaintext secrets** — say where a secret is kept, never the value.
- `discussions/YYYY-MM-DD-<topic>.md` — Conversations the owner relays. Frontmatter: `date`, `participants`, `topic`. Sections: TL;DR, Decisions, Follow-ups.

## Frontmatter
Every file has YAML frontmatter with a required `type`: `core`, `ethos`, `roadmap`, `architecture`, `decision`, `gotcha`, `fix`, `thread`, `plan`, `followup`, `session`, `domain`, `person`, `infrastructure`, `discussion`.

## Conventions
- `[[name]]` links point inside the brain (`<brain>/<name>.md`). Repo files are written as plain paths (`docs/spec.md`). External URLs use markdown links.
- Link sparingly — only when reading A changes how you read B.
- Dates: ISO `YYYY-MM-DD`. File names: lowercase kebab-case; dated types start with `YYYY-MM-DD-`.
- Language: English for entries; the owner's quotes may stay in Turkish.

## Write triggers — update the brain when
- **Owner states a preference or a rule about how to work** → `ethos.md`.
- **Business/private decision** → `decisions/` + 1 line in `core.md`. (Technical/product decisions → the repo's `docs/decisions/`.)
- **Gotcha hit** → `gotchas/`. If a fix shape recurs twice, move it from `fixes/` to `gotchas/`.
- **Non-trivial fix shipped** → `fixes/`.
- **Owner relays a message, a document or feedback** → `discussions/`.
- **"Remind me" / something agreed but not done / a non-code to-do** → `followups/` + line in `core.md`.
- **Follow-up done** → `status: done`, remove its line from `core.md`.
- **Stage or milestone change** → `roadmap.md` + the active thread.
- **New service, account or domain touched** → `infrastructure/`.
- **Session ends with meaningful work** → `sessions/` entry; bump the thread's `last_touched`.

Ask before writing borderline entries. Keep it noise-free.

## Git
The brain is its own git repo. **Every brain update is committed immediately** from inside the brain folder, message `brain: <verb> <what>`. This is the only repo where Claude commits without asking. Push every brain commit to its private remote (`origin`, set up 2026-11-14) right after committing. Never commit secrets, tokens, or personal data of end users.

## Read discipline
**Tier 1 — at session start, one batched read:** `CLAUDE.md`, `core.md`, `ethos.md`, `roadmap.md`, `architecture.md`, all `gotchas/`, `people/`, `infrastructure/`, `decisions/`, and `threads/` with `status: active`.
**Tier 2 — when the task touches it:** `followups/`, `fixes/`, `domain/`, `plans/`, recent `sessions/`, `discussions/`.
**Tier 3 — on demand:** any `[[link]]` reachable from loaded content.

Use the brain silently; don't recite it back to the owner.

## Session start
After the Tier-1 read, if there is a pending high-priority follow-up or an active thread untouched for more than 14 days, mention the top 1–2 briefly in the first substantive reply. If the first message is a focused task, do the task and mention only directly related items.
