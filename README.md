# rhino-write

A [Claude Code](https://claude.com/claude-code) Agent Skill that writes documents — PRDs, wiki/research
pages, competitive-synthesis docs, strategic-thesis pitches, MVP status briefs — in **Tushar
Bijalwan's own structure, tone, and formatting**, instead of a generic PM template.

It was built by extracting real patterns (skeletons, headings, bullet conventions, tables,
vocabulary, tone) from a corpus of documents Tushar actually wrote, so that future drafts don't
require re-explaining format every time.

## What's in this repo

| File | Purpose |
|---|---|
| `SKILL.md` | The skill definition Claude Code loads — when to trigger, how to pick a document skeleton, and the drafting checklist. |
| `references/style-profile.md` | The full extracted style profile: document skeletons, heading/bullet/table conventions, recurring vocabulary, tone markers, and formatting mechanics (including the default font/color for rendered docs). |

## How it works

1. You ask Claude to draft/write up/turn notes into a document (a PRD, wiki page, research
   synthesis, status brief, etc.).
2. The skill picks the matching skeleton from `references/style-profile.md` §1 based on the doc's
   actual purpose (a logic/config spec reads differently from a narrative pitch).
3. It applies the mechanics — heading style, bold lead-in bullets, tables over prose where
   comparative, arrow chains for causal/sequential logic, the right register for the audience.
4. It never fabricates evidence — every stat or quote is sourced or left as an explicit
   `[NEEDS: ...]` placeholder.

See `SKILL.md` for the full rules.

## Setup guide

### Option 1 — personal skill (available in every project)

```bash
git clone https://github.com/tusharbijalwan-beep/rhino-write.git ~/.claude/skills/rhino-write
```

Claude Code auto-discovers skills under `~/.claude/skills/<name>/SKILL.md`. No restart needed if
Claude Code is already running — it picks up new skills on the next turn.

### Option 2 — project-scoped skill (only available inside one repo)

```bash
git clone https://github.com/tusharbijalwan-beep/rhino-write.git <your-project>/.claude/skills/rhino-write
```

Use this when you want the skill to travel with a specific project instead of being available
everywhere.

### Using it

Just ask naturally — no need to invoke it by name:

> "Write this up as a PRD"
> "Turn these notes into a wiki page"
> "Draft a competitive synthesis on X"

Claude Code's skill matcher triggers `rhino-write` automatically based on `SKILL.md`'s
description. You can also invoke it explicitly as `/rhino-write` if your setup exposes it as a
slash command.

## A note on content

The style profile is built from real documents, but anything business-specific (real metrics,
product names, formulas, weights, thresholds) that isn't needed to illustrate a *structural* or
*tone* pattern has been generalized or redacted before being added here. This repo captures *how*
the writing is structured — not the underlying business content.

## Growing this skill

This skill is meant to keep accumulating patterns as more documents are written. If you're
extending it: add new patterns to `references/style-profile.md` rather than replacing it, and
strip business specifics the same way before committing anything here, since this repo is public.
