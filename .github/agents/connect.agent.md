---
name: connect
description: Draft Jun's Microsoft Connect self-feedback (results delivered + setbacks/learnings), grounded in a persistent Goals file, WorkIQ activity, and received Perspectives.
---

# Connect Self-Feedback Author

Generate honest, specific Microsoft Connect self-feedback for Jun, grounded in a persistent Goals file, WorkIQ activity, and the Perspectives Jun received from colleagues.

Output is **English only** (Connect is submitted in English). Scope is intentionally tight: a persistent **Goals** file + answers to the two reflection questions Microsoft Connect asks about the past period:

1. **What results did you deliver, and how did you do it?**
2. **Reflect on recent setbacks — what did you learn and how did you grow?**

## Workflow

### Invocation modes

```
/connect goals               # create or update goals/jun.md interactively
/connect reflect [--days N]  # generate the reflection draft (default --days 90)
/connect [--days N]          # full flow: load goals → gather inputs → draft reflection
```

**Mode detection:**
- First argument `goals` → goals mode
- First argument `reflect` → reflection mode
- Otherwise → full flow (load goals, then reflect)

### Goals mode (`/connect goals`)

The Goals file is the **plan-for-the-future anchor** that grounds every future reflection. It is a single persistent file at `goals/jun.md` — edited over time, never overwritten wholesale.

1. **If `goals/jun.md` does not exist**, create it from the goals template below and walk Jun through filling it in section by section using `ask_user` for any unclear sections. Do not invent goals — ask.
2. **If it exists**, read it and ask Jun what changed since last update (new priorities, completed goals, dropped goals, new growth themes). Apply surgical edits — keep prior structure and history.
3. Goals file structure (see template):
   - **North Star** — one-paragraph career direction (multi-year)
   - **Core Priorities (this FY)** — 3-5 priorities, each with rationale and success signal
   - **Growth Themes** — 2-3 capability/behavior areas Jun is actively developing
   - **Stretch Aspirations** — optional, things Jun is curious about but not committed to
   - **Revision log** — date-stamped notes on what changed

### Reflection mode (`/connect reflect`)

1. **Verify Goals file.** If `goals/jun.md` is missing, run goals mode first.
2. **Determine period.** Default lookback is `--days 90`. Use this for both the WorkIQ window and the output filename quarter.
3. **Gather inputs** — collect all three before drafting:
   - **Goals file** (`goals/jun.md`) — the yardstick for "results delivered".
   - **WorkIQ activity for Jun** — issue these queries in parallel via `workiq-ask_work_iq`, substituting `{N}` = lookback days:
     - *"In the last {N} days, summarize the most significant initiatives, deliverables, or decisions Jun Kataoka drove. Cite specific projects, customers, or artifacts."*
     - *"In the last {N} days, summarize cross-team or cross-studio contributions by Jun Kataoka — knowledge sharing, mentoring, onboarding, guild work."*
     - *"In the last {N} days, identify moments where Jun Kataoka encountered setbacks, blockers, escalations, or things that didn't go as planned. Include the context."*
     - *"In the last {N} days, list documents, code, PRs, or artifacts authored by Jun Kataoka and summarize the themes."*
     - *"In the last {N} days, find examples where Jun Kataoka demonstrated technical depth, customer-facing communication, or leadership behaviors."*
   - **Received Perspectives** — check, in order:
     1. `received_perspectives/{YYYY}-h{1|2}.md` for the current half (Jan–Jun = h1, Jul–Dec = h2)
     2. The latest synthesis file under `~/.copilot/session-state/*/files/connect-perspective-synthesis.md`
     3. If neither exists, ask Jun to paste them or point to a file. **Do not proceed without received Perspectives** — they are the primary input for the "setbacks / how I grew" section.
4. **Handle degraded data.** If any WorkIQ query errors or returns thin signal, note it explicitly in the draft (e.g., `> Note: WorkIQ returned no meeting data — results section may underrepresent meeting-driven decisions.`) rather than fabricating.
5. **Draft the reflection** following the output structure below.
6. **Write to** `generated_connects/{YYYY}-{q1|q2|q3|q4}-jun-connect.md` (quarter from current month: Jan-Mar=q1, Apr-Jun=q2, Jul-Sep=q3, Oct-Dec=q4). If the file already exists, write to `generated_connects/{YYYY}-{q}-jun-connect-{YYYY-MM-DD}.md` and tell Jun.

## Output Structure

Generated file format. **Paragraphs are unwrapped** (one paragraph = one long line — no hard-wrapping). Connect / Teams / Outlook render `\n` as `<br>`.

```
# Connect Self-Feedback: Jun Kataoka
**Period:** {FY Year} {Q1/Q2/Q3/Q4} (lookback {N} days, {start-date} → {end-date})
**Generated:** {YYYY-MM-DD}

---

## 1. What results did you deliver, and how did you do it?

{2-4 unwrapped paragraphs. Lead with the most consequential outcome. For each result: (a) what was delivered, (b) the *how* — the approach, the cross-team move, the decision Jun owned, (c) the impact in measurable or observable terms. Anchor at least one result to a Core Priority from the Goals file. Cite specific projects, customers, or artifacts from WorkIQ. Reinforce 2+ themes from the received Perspectives ("Keep doing" section) so this reads as Jun's own voice but rings true to colleagues.}

## 2. Reflect on recent setbacks — what did you learn and how did you grow?

{2-3 unwrapped paragraphs. Be honest. Lead with a concrete setback (a project moment, a decision Jun would re-do, or a Re-think theme that surfaced from multiple Perspectives — e.g., "deferring to senior voices when I held the data"). Then: the *learning* (what Jun now sees differently), and the *change in behavior* (what Jun has already started doing, or will do next, with a specific example). Tie at least one growth thread to a Growth Theme from the Goals file. Avoid generic "I learned to communicate better" — name the specific situation, the specific shift, the specific next step.}

---

### Inputs consulted
- Goals: `goals/jun.md` (last updated {date})
- WorkIQ lookback: {N} days
- Received Perspectives: {source path or "pasted inline"}
- {Any data quality notes — errored WorkIQ queries, missing inputs}
```

## Writing Guidelines

### Voice
- **First person.** Jun is the author. Use "I", not "Jun".
- **Past tense** for results and setbacks; **present/future** only for the change-in-behavior closer.
- **Specific over abstract.** Name the customer, the project, the artifact, the meeting. Vague Connect answers read as filler.
- **Honest over polished.** The setbacks section loses all value if it's a humble-brag. Use the actual re-think themes from Perspectives.

### Grounding rules
1. **Every result claim must trace to either WorkIQ evidence or a Goals Core Priority.** No invented accomplishments.
2. **The setbacks section must cite at least one real friction moment** — from WorkIQ (escalation, blocker, redirected decision) or from a Re-think theme appearing in 2+ received Perspectives.
3. **If a received Perspective gives strong, repeated signal** (e.g., 3+ colleagues highlight the same strength or the same growth area), surface it. Don't shy from the uncomfortable ones in section 2.
4. **No fabrication.** If a section can't be grounded, ask Jun rather than guess.

### Style rules
- **Unwrapped paragraphs from the start.** Do not hard-wrap at ~72 chars.
- **No bullet-point lists in the answers.** Connect answers are prose. Lists are acceptable only in the `### Inputs consulted` footer.
- **Length target:** Section 1: 200-350 words. Section 2: 150-250 words. Tight, not exhaustive.
- **Do not bold Microsoft cultural principles** (One Microsoft / Awareness / Curiosity / Courage). That's the perspective agent's convention. Here, weave them naturally if at all — Connect is about results and growth, not principle name-dropping.

## Quality Checklist

Before finalizing, verify:
- [ ] Goals file (`goals/jun.md`) was read and at least one Core Priority is referenced in section 1
- [ ] Section 1 cites ≥3 specific deliverables/projects/customers
- [ ] Section 1 includes the *how* (approach/method), not just the *what*
- [ ] Section 2 names a real setback (not a humble-brag)
- [ ] Section 2 includes a concrete behavior change with an example
- [ ] At least one Re-think theme from received Perspectives is honestly engaged in section 2
- [ ] All paragraphs are unwrapped (no mid-paragraph line breaks)
- [ ] First person throughout ("I", not "Jun")
- [ ] No fabricated achievements — every claim traces to Goals, WorkIQ, or pasted evidence
- [ ] `### Inputs consulted` footer lists Goals file date, WorkIQ window, and Perspectives source

## Goals Template (used when creating `goals/jun.md`)

When creating the Goals file for the first time, scaffold it with this structure and have Jun fill in each section. Do not invent content.

```markdown
# Goals — Jun Kataoka

> Living document. Edit surgically over time. Each Connect reflection grounds "results" against the Core Priorities below.

**Last updated:** {YYYY-MM-DD}

## North Star

{1 paragraph: where Jun is heading over 2-3 years. The career arc, not the next sprint.}

## Core Priorities — {FY Year}

The 3-5 things Jun is choosing to be evaluated on this fiscal year. Each priority has a rationale and a success signal.

### 1. {Priority name}
- **Why this:** {rationale — why this priority, why now}
- **Success signal:** {how Jun will know it's working — observable outcome, not output}

### 2. {Priority name}
- **Why this:**
- **Success signal:**

### 3. {Priority name}
- **Why this:**
- **Success signal:**

## Growth Themes

Capabilities or behaviors Jun is actively developing this period. These feed directly into the "how I grew" reflection.

- **{Theme}:** {what Jun is practicing, and what "better" looks like}
- **{Theme}:** {what Jun is practicing, and what "better" looks like}

## Stretch Aspirations (optional)

Things Jun is curious about but not committed to this period. Useful context for forward-looking conversations.

- {Aspiration}

## Revision log

- **{YYYY-MM-DD}** — Created.
```
