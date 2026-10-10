# Tushar Bijalwan — Writing Style Profile

Source corpus: "AI in Trading" (competitive research synthesis), PRD — Expert Picks Blue-Chip
Prioritization Phase 1, PRD — Direct Order Flow (Expert Picks), CoinDCX SEO Attribution PRD,
Algo Trading Wiki, plus two Google Docs he authored and linked in Slack DMs/group DMs —
"AlgoTrading at CoinDCX" (strategic thesis doc) and "Algo Trading — MVP Build" (status brief);
plus a second logic/config-spec PRD for a research page spanning two related-but-distinct asset
types. Extracted verbatim where possible so the patterns stay concrete, not generic — except the
asset-page PRD, where the actual ranking weights/thresholds/formulas are business-specific and are
generalized below rather than quoted.

## 1. Document skeletons (pick the one matching the doc's purpose — he does not use one fixed template)

**Logic/config-spec PRD** (e.g. Blue-Chip Prioritization):
Title → `1. Problem` (→ `Background` → `User Problem`) → `2. Hypothesis` → `3. Implementation`
(→ `Configuration` [raw YAML block] → `Ranking Logic` → `Collision Handling` → `Assumptions` →
`Examples` [worked scenarios as tables] → `Edge Case` [table] → `Acceptance Criteria` [flat
bullets] → `Evaluation Criteria` [numbered, each with "Measured by" sub-bullets]) →
`Future Evolution (Phase 2)` → `Long-term Vision`.

**Logic/config-spec PRD — parallel-entity variant** (a research page spanning two related but
distinct entity types, e.g. "Type A" vs "Type B"): `Why We Are Building X` → `Core Product Thesis`
[a chain of progressively escalating questions that acts as the *whole doc's* backbone, not just a
section opener — "What am I looking at? → What is happening to it? → How has it behaved? → What
explains its value/performance? → What should I investigate next?"] → `The Research Experience We
Need to Build` (→ the same question restated per entity type as `Type A → "quoted question"` /
`Type B → "quoted question"`, surfacing how the same intent forks into different sub-questions) →
`User Stories` (`N. User Problem` → needs bulleted separately per entity type) → `Product
Principles` (each principle a short bold label, one line of justification) → `What X Owns` (a
one-line ownership claim, then the minimum building blocks as an arrow chain per entity type) →
`Structure` (the user's progression through the page as one arrow chain) → per-entity-type
`Research Baseline` (arrow chain of modules, then each module restated as a question with one
supporting line) → `Ranking Logic` (`Core Ranking Principles` as imperative rules — always
including an explicit "missing data is excluded, never treated as zero" rule — then one subsection
per module: `Ranking metric:` → `Formula:` [normalize every factor before combining; never combine
a raw count with a percentage] → `Why weighted ranking?` [defends the chosen weighting by ruling
out each single-factor alternative by name] → `Display:` row spec → a `Future Scope: X` subsection
closing on a `V2 decision:` line that explicitly defers the unresolved specifics instead of
guessing them) → `Derived Insights Rules Logic` (turns raw metrics into single templated
sentences; any numeric threshold is stated once and immediately flagged "centrally configurable
for future calibration" rather than hardcoded-and-forgotten; `Edge Cases` as bullets phrased
`If <condition>, <fallback>`) → `Requirements` (`Functional` / `Non-Functional`, grouped under the
same module names already used earlier in the doc) → `Analytics & Tracking` (the funnel described
in two prose paragraphs, not a table, then a pointer to the full schema in an external sheet
rather than inlining it: `Reference: <sheet name>`).

**Narrative-funnel PRD** (e.g. Direct Order Flow):
Title → `Executive Summary` → `Voice of the User` [verbatim Hinglish quotes, named attribution]
→ `What Data Tells Us` [funnel table] → `Problem/Opportunity` (→ `Opportunity` → `Hypothesis`
as a single "If we... then we..., because..." sentence) → `Product Thesis` → `Proposed Solution`
(sub-cases as `Case 1/2/3/4:` → `Requirement` → `Rationale`) → `Success Metrics`
(`North Star Metric` + `Leading Metrics`, each with a one-line `Why:`) →
`Instrumentation & Analytics` (`Events to Track`) → `Rollout Strategy`
(`Target Cohort` → `Rollout`: Phase 1/2/3).

**Diagnosis-then-solution PRD** (e.g. SEO Attribution PRD):
Title → `Why Now` (→ `The Impact`) → `Current User Journey — As Observed Today`
(→ `The pattern, stage by stage` → `What this reveals about the real gap`) → `Problem Statement`
(labeled `A1 —`, `A2 —`) → `User Journey — Current vs. Target Funnel` (`Case 1 <> ...` style) →
`The Target State` → `Solution Implementation` [capability table] → `Data Capture Requirement`
(numbered, each a table + one-line `Purpose:`) → `User Journeys` (numbered, arrow-chain flow +
`Expected outcome:`) → summary tables.

**Research-dossier wiki** (e.g. Algo Trading Wiki) — the same skeleton repeats verbatim per topic:
`[TOPIC LABEL] / [punchy thesis-as-title]` → `BUSINESS QUESTION` → `EXECUTIVE SUMMARY` →
`OBSERVATION` → `ANALYSIS` → `BUSINESS IMPLICATION` → `KEY TAKEAWAYS`. Then a `Proposal` mode
(Executive Summary → Structural Problem → Opportunity/Why Now → Product Strategy → Roadmap →
Technical Architecture), and a vendor-evaluation mode (Must-Have pass/fail table → capability
scoring matrix → "Why X" doc with numbered reasons).

**Competitive-synthesis doc** (e.g. AI in Trading): grouped by category → one
Use Case/Feature/What-It's-Solving/Specs table per competitor → a named "Crux of Market"
section → "What this means for X" section → Supported VOCs → Conclusion with a single bolded
directive sentence.

**Strategic thesis / pitch doc** (e.g. "AlgoTrading at CoinDCX", shared as a Google Doc link in
Slack): `1. Executive Summary and Core Thesis` → `2. The Structural Problem` [segment/failure
table] → `3. The Opportunity and Why Now` [competitive capability matrix] → `4. Product Strategy`
(→ linked `ICP:` term → `Phase 1: <name>` with a bolded `Vision:` line and a `Core rule:` line →
phase table `Phase | User Question | MVP Deliverable`) → `5. Product Roadmap` [ladder table
`Phase | Work item | Objective | User Value | Business Value`] → `6. Technical Architecture and
Risk Controls` [bullets]. Numbered top-level sections throughout — this doc type is closer to a
leadership pitch than a build spec, but still numbered because it's building an argument
step by step.

**MVP status brief** (e.g. "Algo Trading — MVP Build"): `OPERATING PRINCIPLE` [bold all-caps
label, one paragraph] → `SYSTEM / INTEGRATION MODEL` → `WHAT WE'RE PROPOSING TO BUILD (MVP
COMPONENTS)` [bold-lead-in bullets, each with a bracketed inline status aside] →
`CAPACITY / THROUGHPUT (ALREADY MODELLED)` [one-paragraph number-dense summary, linked to the
underlying sheet] → `Where We Stand — Done vs. Blocked` [two-column table, DONE / BLOCKED-OPEN,
each cell a bold-lead-in list]. This type uses bold ALL-CAPS section labels instead of heading
styles — reads like a status update meant to be skimmed top-to-bottom fast.

## 2. Heading style

- Title used once per doc/module, sometimes emoji-prefixed in wiki docs (`🔍 Product Discovery`,
  `✅ Proposal`, `🕵️ Competitor analysis`, `📐 Vendor Evaluation`) — never emoji inline in body text.
- Numbering is inconsistent **by design**: sequential/logical docs get `1.`, `2.`, `3.`; narrative
  docs skip numbers entirely. Match numbering to whether the doc reads as steps or as a story.
- Sub-headers are short, Title Case noun phrases with no trailing colon: `Ranking Logic`,
  `Collision Handling`, `Rationale`, `Requirement`.
- Heading depth follows real logical nesting (goes as deep as H6 for edge cases) — never nest
  just to look thorough.
- Case/scenario headers: `Case 1: <short description>` or `Case 1 <> <short description>`.

## 3. Sentence and paragraph style

- Short, declarative, often clipped: "Today, the experience breaks this promise at the final
  step." One-line paragraphs used for emphasis — a single sentence standing alone.
- Em/en-dash as a pause substitute for a comma or "which": "Participation exploded to 210M+ demat
  accounts... But one workflow was never democratized: the ability to trade systematically — and
  the market's own numbers show what that ability actually is."
- Rhetorical why/what framing as section openers, often literally the section's own
  `BUSINESS QUESTION`: "Why can't features fix these?", "What has fundamentally changed in
  retail trading?"
- First person used sparingly, signals his own research/synthesis: "I have studied the places
  traders speak honestly." System/product logic stays third person or passive: "The order flow
  must preserve..."
- Arrow chains (→) as a sentence-construction device, not just a diagram: "Discover → Evaluate →
  Show Intent → Quick Trade → Execute."
- Conclusions are blunt, sometimes contrarian: "The problem at first place therefore is less on
  recommendation quality. The problem is initial trust during discovery."
- Minor grammatical looseness (dropped articles, inconsistent capitalization) shows up in his
  internal/working docs and is part of the authentic voice there — don't over-polish internal
  working docs into corporate-clean prose. For anything external-facing or being sent up/out,
  clean the grammar but keep the sentence rhythm and directness.

## 4. Bullet and list conventions

- Bullets, not numbers, unless sequence/priority literally matters (rollout phases, roadmap
  phases get numbers; everything else is a bullet).
- Bold lead-in bullets are the default synthesis pattern: **Bold short claim, colon, then one or
  two sentences of support.** e.g. "**Prioritize maturity over market presence:** Only a handful
  of platforms have..."
- Bullets often compress causal chains with arrows instead of prose: "Higher familiarity →
  Higher trust → Higher chance to FNAP → Higher repeat trade."
- Shallow nesting — prefers flat bullets broken into more named sub-sections over deep nested
  bullets.
- Fallback/exception logic always gets its own explicit bullet: "Fall back: If market cap data is
  not available [NULL], append the active Global calls as-is."

## 5. Tables — recurring archetypes

- **Use Case / Feature / What It's Solving / Specs** — one table per competitor/option in
  competitive teardowns.
- **Funnel/conversion**: `Funnel Stage | Conversion[3MTD]` with drop-off % and absolute counts in
  parentheses.
- **Scenario/worked-example**: `Pos | Instrument | Reasoning` — makes abstract logic concrete via
  simulated inputs.
- **Data-point/requirement**: `Data Point | Requirement` — instrumentation/tracking specs.
- **Scoring/comparison matrix**: `Segment | Pain | Frequency | Capital | Willingness | Total`, or
  `Criteria | Vendor A | Vendor B | Vendor C` with 1–5 scores and a computed weighted total row.
- **Pass/Fail gate**: `Criteria | Vendor1 | Vendor2 | Vendor3` with cells literally `PASS` /
  `FAIL` / `CONDITIONAL` / `PARTIAL`.
- He tables even simple two-column definition lists (`Objective | ...`, `Screen | ...`) that could
  be prose — scanability over paragraph form is a deliberate choice.
- **Status table**: `DONE | BLOCKED / OPEN` — a two-column table where each cell is itself a
  bold-lead-in list, used specifically for progress/status updates ("Where We Stand").
- **Competitive capability matrix**: rows of competitors/alternatives, columns of binary/partial
  capabilities (`Yes` / `No` / `Partial`), own product's row bolded, e.g.
  `Market | Automation | Custody & Trust | India-Native (FIU/Tax) | Serves Non-Experts`.
- Column headers: short, Title Case, sometimes bracket-qualified (`Conversion[3MTD]`,
  `Weighted total`).

## 6. Recurring vocabulary and labeled sections

Reuse these verbatim as section labels/phrases when they fit the doc type:
- "What this means for X" (a synthesis section header)
- "Crux of Market:" (label for the single sharpest finding)
- "Supported VOCs:" (labeled section, verbatim user quotes only)
- "North Star Metric:" / "Leading Metrics" (fixed metric-hierarchy labels)
- "Business Question" / "Business Implication" / "Key Takeaways" (fixed wiki-template labels)
- "Why Now" (section header for diagnosis/urgency docs)
- "Rationale:" (standalone label before justification bullets)
- "Out of Scope" / "MVP Scope Boundaries" (always its own explicit section)
- "internal_data" tagged inline next to a stat: "[X]% [internal_data]"
- "Citation: [1,2]" — bracketed numeric citation markers
- "debatable" appended inline to flag a contested requirement instead of deleting it
- "Open Tasks and Questions" (collects TBDs at the end)
- A recurring product-philosophy formula, restated across docs in slightly different phrasing:
  "Remove the decision before removing the effort" / "Automate discipline before adding
  capability" — this is a personal maxim, reuse the *pattern* (a two-clause imperative
  contrasting what to remove/add first), not the literal words, when a new doc calls for a
  similar principle. Confirmed again in the Slack-linked thesis doc as "Core rule: Remove the
  decision before removing the effort", followed immediately by reducing a whole strategy to
  the two questions that actually matter: "Whom to trust? / How much to risk?" — a broader
  pattern of collapsing a complex problem into 2 blunt questions.
- "OPERATING PRINCIPLE" and other bold ALL-CAPS section labels (`SYSTEM / INTEGRATION MODEL`,
  `WHAT WE'RE PROPOSING TO BUILD`, `CAPACITY / THROUGHPUT (ALREADY MODELLED)`) — used specifically
  in fast-skim status/brief docs, not in PRDs or wiki entries (which use normal heading styles).
- Bracketed inline status/clarification asides directly inside a bold-lead-in bullet:
  "Sub-account setup [exist already] —", "Access restriction guardrails — To be Identified by
  Engineering and still to be scoped", "[In talks with vendor]", "[First draft reviewed by Ravi
  in progress to finalize]" — a compact way of flagging owner/status without a separate column.
- "Core Ranking Principles" (fixed label introducing the imperative rules that govern every
  ranking/scoring module in a doc, stated once up front rather than repeated per module).
- "Why weighted ranking?" (a "Why not X" variant specifically for defending a scoring formula —
  rules out each single-factor alternative by name before landing on the chosen weighting).
- "Future Scope: X" / closing "V2 decision:" line — explicitly defers unresolved specifics
  ("final factors/weights to be validated before implementation") instead of guessing them.
- A numeric threshold is always paired with an explicit "centrally configurable for future
  calibration" (or equivalent) note — never hardcode-and-forget a tunable knob.
- "X owns Y" as the fixed phrasing for a scope/ownership claim before a module breakdown.
- Progressive-question chains used as a whole-document backbone, not just a section opener — the
  same "rhetorical why/what framing" from §3, escalated across an entire doc's structure.

## 7. Tone markers

- **Evidence-tagging discipline**: every stat is explicitly sourced inline — `[internal_data]`,
  `Citation: [1,2]`, or a named quote attribution. Never a bare unsourced number.
- **Verbatim Hinglish quotes** as primary evidence, always with a real name attribution on the
  next line, e.g. "Minimum ka lag jaayega toh matlab sahi hoga..." — Lalit Kumar. Never
  paraphrased into English — this is core to his VOC style. (Only use this pattern when real
  quotes/attribution exist — never fabricate a quote or a name.)
- **Arrows (→) as argument structure**, compressing causal/sequential logic into one line.
- **Mid-sentence bold for the single load-bearing claim** in a paragraph — never whole-sentence
  or whole-paragraph bold.
- **"Why not X" sub-headers** to defend a prioritization call by walking through rejected
  alternatives one by one with a named reason each.
- **Self-critique / calibration**: explicitly checks whether outside research and internal data
  agree before trusting a thesis, e.g. "External Claims, Internal Confirmations — Stronger in Our
  Data Than in the Research."
- Numbers are precise with honest uncertainty markers rather than false precision: "~[N]L
  users", "+10–15%".
- Closing "Standing Test" pattern — ends strategic sections with a short reusable decision
  checklist framed as questions.

## 8. Formatting mechanics

- **Bold**: only for (a) the lead phrase of a bold-lead-in bullet, (b) fixed labels
  (`North Star Metric:`, `Why:`, `Rationale:`), (c) the single most important clause in a
  paragraph. Never bolds full sentences or paragraphs.
- No italics or underline — emphasis comes from bold + bullet structure + short-sentence pacing.
- Emoji only as a Title-level marker (one per major module), never inline in body copy.
- Code/config blocks (YAML, JSON) dropped in raw and inline in the doc body where exact system
  behavior needs to be specified — not pushed to an appendix.
- Section breaks are heading-level changes, not horizontal rules or blank-line conventions.
- `→` and `<>` used as informal connectors in headers/body in place of "vs." or "to"
  (`Competitor analysis<>Delta Exchange`).
- **Typeface and color (rendered docs only — docx/Google Docs, not markdown/chat)**: body font is
  **IBM Plex Sans, Light weight**; font color is **black** throughout — headings included, no
  color-coding or secondary gray text. Apply this whenever actually rendering a file, not when
  replying inline in chat.
