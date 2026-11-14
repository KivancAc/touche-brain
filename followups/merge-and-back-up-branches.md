---
type: followup
created: 2026-11-14
priority: high
status: done
owner: kivanc + claude
source: brain setup review 2026-11-14
---
# Merge the branch stack and add a private remote

The repo has **no remote**: all Touche code exists only on this laptop. `main` is 17 commits behind the working branch `stage1/1.4-mobile-foundation`; tasks 1.1a–1.4 sit on stacked, unmerged branches (`stage0/*`, `spec/owner-answers-2`, `stage1/*`).

Next: (1) Kivanç creates a **private** GitHub repo (and one for this brain); (2) Claude merges the reviewed stack into `main` in order, running typecheck/lint/tests/pgTAP after each; (3) push only with Kivanç's OK.

## Done 2026-11-14
Kivanç created private repos `KivancAc/touche` and `KivancAc/touche-brain`. Every branch was already contained in `stage1/1.4-mobile-foundation`, so `main` was fast-forwarded to it (3dfbc04) — no merge commits. Before pushing: typecheck, lint, unit tests (shared 18, mobile 46) and pgTAP (297) passed; secret scan of all history clean. All 11 branches pushed with upstream tracking; brain pushed.
