---
name: rhino-write
description: Writes documents (PRDs, wiki/research dossiers, competitive-synthesis docs, strategic-thesis pitches, MVP status briefs) in Tushar Bijalwan's own structure, tone, and formatting — built from a corpus of his real PRDs and research docs. Use whenever Tushar asks to draft, write up, or turn notes into a document, PRD, wiki page, or research synthesis, without him having to re-specify format each time.
---

# Tushar's Document Style

Reproduces how Tushar actually writes — not a generic PM template. Built from eight real
documents he authored: four PRDs, one internal research wiki, one competitive-synthesis doc,
plus two Google Docs (a strategic thesis doc and an MVP status brief) pulled from links he shared
in Slack DMs/group DMs. The full extracted profile (verbatim quoted patterns) is in
`references/style-profile.md` — read it before drafting anything non-trivial. Note: the fourth
PRD (a parallel-entity research-page spec) had business-specific weights/thresholds/formulas
stripped to generic placeholders before being added — only the structural/labeling patterns were
kept, see the profile's intro note.

## How to use this

1. **Identify the doc's purpose**, then pick the matching skeleton from
   `references/style-profile.md` §1:
   - Spec that defines system/config logic (ranking rules, edge cases, acceptance criteria) →
     **logic/config-spec PRD** skeleton.
   - Pitch for a new feature/flow driven by user pain → **narrative-funnel PRD** skeleton
     (Voice of the User → Data → Hypothesis → Solution → Metrics → Rollout).
   - "Here's what's broken today, here's the fix" → **diagnosis-then-solution PRD** skeleton.
   - Ongoing knowledge base entry / market or user research → **research-dossier wiki** skeleton
     (Business Question → Executive Summary → Observation → Analysis → Business Implication →
     Key Takeaways, repeated per topic).
   - Competitor/market landscape write-up → **competitive-synthesis** skeleton (per-competitor
     table → Crux of Market → What this means for X → Conclusion).
   - Leadership pitch / strategic thesis for a new initiative → **strategic thesis** skeleton
     (Executive Summary and Core Thesis → Structural Problem → Opportunity and Why Now →
     Product Strategy [with a `Core rule:` line] → Product Roadmap → Technical Architecture and
     Risk Controls), numbered top-level sections building an argument step by step.
   - Fast-skim project status update → **MVP status brief** skeleton (bold ALL-CAPS section
     labels like `OPERATING PRINCIPLE`, `WHAT WE'RE PROPOSING TO BUILD` → bold-lead-in bullets
     with bracketed status asides → a `Done | Blocked/Open` two-column table).
   - If the ask doesn't cleanly match one of these, say so and ask which shape fits, or propose
     the closest one rather than defaulting to a generic PRD template.

2. **Apply the mechanics**, not just the skeleton — pull from §2–§8 of the style profile:
   - Numbered headings for sequential/logic docs, unnumbered for narrative docs.
   - Bold lead-in bullets (`**Claim:** support.`) as the default synthesis unit.
   - Tables over prose for anything comparative, scored, or point-by-point — see the table
     archetypes in §5 and reuse the matching column headers.
   - Arrow chains (→) for causal/sequential logic, in headers and inline in sentences.
   - Reuse his fixed section labels where they fit: `Why Now`, `Rationale:`, `North Star Metric`,
     `Business Implication`, `Key Takeaways`, `Supported VOCs:`, `Out of Scope`, `Open Tasks and
     Questions`.
   - Bold only the single load-bearing clause in a paragraph — never whole sentences.
   - No italics/underline; emoji only at title level if the doc type calls for it (wiki modules).
   - When actually rendering a file (docx/Google Doc, not a chat reply): **IBM Plex Sans Light**,
     **black** font color throughout — see style-profile §8.

3. **Never fabricate evidence.** His style tags every number and quote with a source
   (`[internal_data]`, `Citation: [n]`, or a named attribution). If Tushar hasn't given you the
   underlying data/quotes for a section that calls for them, either ask for them or leave an
   explicit placeholder (e.g. `[NEEDS: internal funnel data]`, `[NEEDS: VOC quote]`) instead of
   inventing a number, a quote, or an attribution. This matches how he actually sources claims —
   don't break the pattern by making evidence up. See also
   [[seo-charter-caution-hypothetical-data]] and [[feedback-voc-note-writeups-not-fabricated]] in
   memory: real quotes/notes get written up faithfully, but nothing gets invented wholesale.

4. **Match register to audience.** Internal working docs (wiki entries, draft PRDs) can keep his
   authentic minor looseness (dropped articles, inconsistent caps) — that's part of the real
   voice, not a typo to fix. Anything external-facing or going up the chain should have clean
   grammar but keep the short-sentence rhythm, bold lead-ins, and arrow-chain logic — polish
   the surface, not the structure or tone.

5. **Before finalizing, check against [[feedback-illustrative-vs-literal-spec]]**: if Tushar gave
   you a rough dump/example to explain the *content*, don't over-literalize it into rigid spec
   language he didn't intend — match his tone, don't over-correct his intent.

6. **Growing this skill**: this was built from seven documents (five local files + two Google
   Docs found via Slack links). Note: Tushar rarely uploads native files to Slack — he shares
   Google Doc/Sheet links in messages instead, so a "pull from Slack" pass means searching
   `slack_search_public_and_private` for `from:me` messages containing doc/sheet links, then
   reading those via Google Drive, not searching Slack's file content type (which came up empty).
   If Tushar shares more of his writing later (a new PRD, a Slack update, a doc type not yet
   covered here — e.g. a status update or email), extend `references/style-profile.md` with the
   new patterns rather than replacing it, the same way other project skills accumulate an ongoing
   ledger.

## Quick checklist before handing back a draft

- [ ] Skeleton matches the doc's actual purpose (not defaulted to a generic PRD shape)
- [ ] Headings numbered only if the doc is sequential/logical
- [ ] Bold lead-in bullets used for synthesis points, not plain bullets
- [ ] Tables used wherever the content is comparative/scored/point-by-point
- [ ] Every stat or quote is sourced or flagged as `[NEEDS: ...]` — nothing invented
- [ ] Arrow chains used for causal/sequential logic where natural
- [ ] Bold reserved for single load-bearing clauses/labels, not full sentences
- [ ] Register (internal vs. external) matches audience
