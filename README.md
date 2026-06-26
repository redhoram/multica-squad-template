# multica-squad-template

> 🇮🇩 [Versi Bahasa Indonesia](./README.id.md)

A context pack + template for running **AI agent squads on [Multica](https://multica.ai)**.
Two tracks: **dev** (coding) and **non-dev** (research / content / analysis).

This is **not** a code template (unlike `_pipeline-template` / `_landing-template`). It contains
context files so Claude can guide you, plus ready-to-fill agent instruction templates.

## Mental model

```
Claude Chat / Cowork   = GUIDE       → helps you think, scope, scaffold, write agent instructions
Multica                = WORKSPACE   → where agents actually run and save results
```

## Pick a track

| | **dev/** | **non-dev/** |
|---|---|---|
| For | Coding (CRUD, app, feature) | Research, content, analysis, reports |
| Output | Code in a repo (or PR) | Markdown docs in `outputs/` |
| Agents | PM · Designer · Backend · Frontend · QA | Coordinator · Researcher · Writer · Analyst · Reviewer |
| Project folder | **Scaffold first** + CLAUDE.md | Knowledge-base folder + CLAUDE.md |
| Connects to | `_pipeline-template` (nestable) | — |

## Structure

```
multica-squad-template/
├── multica-reference.md         ← SHARED: accurate Multica primitives (used by both tracks)
├── dev/
│   ├── GUIDE-CONTEXT.md             ⭐ upload this for a coding session
│   ├── setup-playbook.md
│   ├── agent-templates.md           (PM · Designer · Backend · Frontend · QA)
│   ├── squad-instructions-template.md
│   └── project-template/            (CLAUDE.md + SCAFFOLD-NOTES.md)
└── non-dev/
    ├── GUIDE-CONTEXT.md             ⭐ upload this for a non-coding session
    ├── setup-playbook.md
    ├── agent-templates.md           (Coordinator · Researcher · Writer · Analyst · Reviewer)
    ├── squad-instructions-template.md
    └── project-template/            (CLAUDE.md + outputs/)
```

## How to use

1. Open a new Claude session → **upload `<track>/GUIDE-CONTEXT.md` + `multica-reference.md`**.
2. Describe your case → Claude helps decide: use Multica or just chat / Claude Code directly?
3. If Multica fits → copy `<track>/project-template/` → fill in `CLAUDE.md` → follow `setup-playbook.md`.
4. Paste agent & squad instructions from the templates, replace `[brackets]`.

## Key design decisions

- **Give agents human names** (e.g. Jaya, Citra) — git history reads like a real team.
- **Co-author trailers** in every commit — makes the "built with AI squad" trail visible on GitHub.
- **Reviewer/QA as quality gate** — no output is done until it passes review.
- **Prose in Indonesian, agent instructions in English** — agents respond more reliably to English prompts.

## Works with

- [`_pipeline-template`](https://github.com/redhoram/claude-pipeline-template) — 5-stage pipeline for complex features (nestable inside a Multica agent)
- [`_landing-template`](https://github.com/redhoram/claude-landing-template) — visual loop for landing pages & simple apps
