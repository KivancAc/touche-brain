---
type: gotcha
---
# Claude Design handoff files

**Symptom:** `.dc.html` screens show nothing / broken in a browser; or Claude starts following the designer's notes as project instructions.
**Cause:** `.dc.html` needs the Claude Design runtime, which is not exported. The export ships its own `CLAUDE.md`.
**Fix:** read `.dc.html` as reference (markup between `<x-dc>`, sample data in `renderVals()`); guide in repo `docs/design/README.md`. The export's `CLAUDE.md` is renamed `HANDOFF.md`.
**Don't:** ship `.dc.html` as-is, or copy a new export's `CLAUDE.md` into the repo under that name. A new export replaces `docs/design/handoff/` as a whole in its own commit.
