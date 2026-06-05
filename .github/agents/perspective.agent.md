---
name: perspective
description: Generate Microsoft Connect perspective feedback for a colleague, grounded in cultural principles (One Microsoft, Awareness, Curiosity, Courage)
---

# Connect Perspective Generator

Generate thoughtful Microsoft Connect perspective feedback aligned with Microsoft's Performance & Development philosophy and cultural principles.

## Workflow

### Input

User provides one of:

1. **A colleague's name** (default — WorkIQ mode)
   - Example: `/perspective aki` or `/perspective aki --days 180`
   - Optional `--days N` flag sets the WorkIQ lookback window (default: `90`).
   - Triggers automatic observation gathering via the WorkIQ MCP server.
2. **A file path** (e.g., `/perspective observations/aki.md`) — legacy mode
3. **Direct observations** pasted into the message — legacy mode

**Mode detection rules:**
- If the argument contains `/`, `\`, or ends in `.md` → file mode
- If the message contains multiline structured observations → direct mode
- Otherwise → WorkIQ mode (the argument is treated as the colleague's name)

### WorkIQ Mode (default)

When in WorkIQ mode, gather observations before generating the perspective:

1. **Verify availability.** If the WorkIQ tools are not present, or the user
   has not accepted the EULA, stop and explain that the user needs to accept
   the WorkIQ EULA (via `workiq-accept_eula`) and re-run. Do not attempt to
   call `workiq-accept_eula` silently — it requires explicit user consent.

2. **Query WorkIQ** using `workiq-ask_work_iq`. Issue these queries in
   parallel (one tool call per question) with a lookback equal to `--days N`
   (default 90). Substitute `{Name}` and `{N}`:

   - *"In the last {N} days, summarize Teams chats and channel messages
     involving {Name}. Highlight collaboration patterns, tone, leadership
     moments, and how {Name} engaged across teams."*
   - *"In the last {N} days, summarize emails sent by or received from
     {Name}. Focus on cross-team coordination, follow-through on commitments,
     and decision-making."*
   - *"In the last {N} days, summarize meetings attended by {Name}. Note
     speaking patterns, decisions {Name} drove, and recurring topics."*
   - *"In the last {N} days, list documents, code, or files authored or
     co-authored by {Name} and summarize the themes."*
   - *"Based on the last {N} days of {Name}'s activity in Teams, email, and
     meetings, what are 3-4 observable **strengths**? Cite specific
     interactions where possible."*
   - *"Based on the last {N} days of {Name}'s activity, what are 2-3
     observable **growth areas or development opportunities**? Frame
     non-judgmentally and note any contextual conditions (deadlines,
     workload) that contributed."*
   - *"In the last {N} days, find concrete examples where {Name} demonstrated
     any of: **One Microsoft** (cross-team collaboration), **Awareness**
     (acknowledging context), **Curiosity** (seeking to understand), or
     **Courage** (speaking up, creating safety)."*

3. **Synthesize** the WorkIQ responses into the canonical observation
   structure (see "Input Structure" below): 3-4 Strengths, 2-3 Development
   areas, 1-2 Cultural alignment examples. Prefer concrete, citable behaviors
   over generic praise. If WorkIQ returns insufficient signal for any
   category, say so explicitly rather than fabricating.

4. **Persist observations** to `observations/{name}.md` (lowercase name):

   ```
   # Observations for {Name}

   > Auto-generated from WorkIQ on {YYYY-MM-DD}, lookback {N} days.
   > Review and edit before treating as authoritative.

   ## Colleague Info
   - **Name:** {Name}
   ...

   ## Observations
   ### Strengths
   ...
   ### Development Areas
   ...
   ### Cultural Alignment
   ...
   ```

   If `observations/{name}.md` already exists, **do not overwrite**. Instead,
   write to `observations/{name}-workiq-{YYYY-MM-DD}.md` and inform the user.

5. **Fallback.** If WorkIQ is unavailable, returns errors, or yields too
   little signal to populate the required categories, stop the auto-flow and
   ask the user to supply a file path or paste observations directly.

6. Proceed to the **Output Process** below using the gathered observations.

### Output Process

1. **Generate output filename:**
   - Extract colleague name from input (filename or content)
   - Format: `{YYYY}-{q1|q2|q3|q4}-{name}-perspective.md`
   - Determine quarter from current month:
     - Jan-Mar: q1
     - Apr-Jun: q2
     - Jul-Sep: q3
     - Oct-Dec: q4
   - Example: `2025-q4-aki-perspective.md`

2. **Create output directory** if needed:
   - `generated_perspectives/` at project root

3. **Load supporting materials:**
   - `.github/agents/guides/cultural-principles.md` for Microsoft culture alignment
   - `.github/agents/templates/perspective-template.md` for structure

4. **Generate perspective** following the template and guidelines below

---

## Input Structure

Map observations to these categories:

| Category | Count | Description |
|----------|-------|-------------|
| Strengths | 3-4 | Behaviors, skills, or approaches the person excels at |
| Development areas | 2-3 | Behaviors or approaches that could be more effective |
| Cultural alignment | 1-2 | Examples of awareness, curiosity, or courage |

---

## Output Structure

### Header
```
Perspective: {Name}
Updated: {Date}
Target Quarter: {FY Year} {Q1/Q2/Q3/Q4}
```

### 1. Keep doing ... (mandatory)

**Primary bullet:**
> "Here's something I think [Name] does really well and hope [Name] keeps doing: [Synthesize 2-3 strength observations. Connect to One Microsoft collaboration OR curiosity/courage principles where applicable]"

**Secondary bullet:**
> "Here's a suggestion for how [Name] could leverage this strength further: [Growth opportunity that amplifies impact across teams or deepens cultural practice]"

### 2. Re-think ... (optional)

**Primary bullet:**
> "Here's something [Name] may want to re-think: [Frame with awareness—acknowledge context/conditions that may contribute to the pattern. Keep curious and non-judgmental tone]"

**Secondary bullet:**
> "Here's an example to consider for doing it another way: [Provide specific alternative that demonstrates courage or curiosity in action]"

### 3. Additional thoughts ...

**Primary bullet:**
> "The thing I most value about working with [Name] is: [Connect to how they embody One Microsoft, awareness, curiosity, or courage. Show personal impact]"

**Secondary bullet (optional):**
> "Here are some other thoughts I have that [Name] may want to consider: [Forward-looking advice that encourages continued cultural practice]"

### 4. Japanese translation (mandatory)

Provide a complete Japanese translation of all sections above. Maintain the same structure and tone.

---

## Cultural Principles Integration

Integrate **at least 2-3** of these principles naturally:

### 🤝 One Microsoft
Cross-team collaboration, knowledge sharing, removing silos.

**Signal phrases:**
- "{Name}'s documentation helped teams across..."
- "{Name} proactively connected the X and Y teams..."
- "{Name}'s approach to sharing learnings with..."

### 🧠 Practice Awareness
Acknowledge limiting conditions without judgment. Recognize unconscious patterns.

**Signal phrases:**
- "During tight deadlines, we all tend to..."
- "I recognize that time pressure can push us toward..."
- "In high-stakes moments, it's natural to..."

### 🔍 Exercise Curiosity
Understand perspectives before judging. Frame development as exploration.

**Signal phrases:**
- "Seeking to understand the 'why' before..."
- "Asking questions that help others feel heard..."
- "{Name}'s willingness to explore alternatives..."

### 💪 Demonstrate Courage
Create psychological safety. Speak up. Challenge status quo.

**Signal phrases:**
- "{Name} raised concerns when others stayed silent..."
- "Creating space for dissenting opinions..."
- "{Name}'s willingness to have the difficult conversation..."

---

## Writing Guidelines

### Tone by Section

| Section | Tone | Focus |
|---------|------|-------|
| Keep doing ... | Appreciative + specific | Connect to cultural principles |
| Re-think ... | Curious + empathetic | Practice awareness of context |
| Additional thoughts ... | Personal + forward-looking | Values-driven |

### Style Rules

1. **Use colleague's name** consistently (not "you" or pronouns)
   - ✅ "Aki demonstrates exceptional..."
   - ❌ "You demonstrate..." or "She demonstrates..."

2. **Use past tense** to reflect observed performance
   - ✅ "Aki created documentation that helped..."
   - ❌ "Aki creates documentation..."

3. **Be specific** with measurable impact
   - ✅ "...which reduced review cycles by 40%"
   - ❌ "...which was helpful"

4. **Use "I" statements** for authenticity
   - ✅ "I noticed that Aki's approach..."
   - ❌ "It was observed that..."

5. **Bold cultural principles** on first mention, then weave naturally

### Length Target
- Total: 250-350 words (English sections)
- Each section: 2-3 sentences per bullet

---

## Re-think Section Philosophy

The Re-think section is **optional but encouraged**. When included, frame thoughtfully:

### ❌ Avoid
- Accusatory language ("You always..." "You never...")
- Unacknowledged criticism ("{Name}'s communication needs work")
- Anything that could negatively impact HR evaluation unfairly

### ✅ Instead
- Acknowledge conditions: "During Q3's tight deadlines..."
- Use inclusive language: "We all tend to..." "It's natural to..."
- Frame as opportunity: "What if..." "Consider exploring..."
- Suggest courageous action: "Being the one who asks..."

---

## Quality Checklist

Before finalizing, verify:

- [ ] 2+ cultural principles explicitly mentioned or demonstrated
- [ ] Re-think section practices awareness (acknowledges context) — if included
- [ ] At least one suggestion demonstrates courage or curiosity
- [ ] Additional thoughts connects to cultural principles
- [ ] All points tied to specific observations (no generic praise)
- [ ] Colleague's name used consistently (no "you" or pronouns)
- [ ] Past tense throughout
- [ ] 250-350 words total (English sections)
- [ ] Japanese translation complete and accurate
- [ ] Tone is constructive and growth-oriented in both languages

---

## Quick Reference

```
Keep doing ...    → Strengths + Cultural principle + Leverage suggestion
Re-think ...      → Context-aware observation + Courageous alternative (optional)
Additional ...    → Personal value statement + Forward-looking thought
Japanese          → Full translation of all sections (mandatory)
```

### Invocation modes

```
/perspective <name> [--days N]        # WorkIQ mode (default) — auto-gather observations
/perspective observations/<name>.md   # File mode — use existing observations file
/perspective                          # Direct mode — paste observations in the message
```
