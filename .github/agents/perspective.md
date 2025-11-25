---
name: perspective
description: Generate Microsoft Connect perspective feedback for a colleague, grounded in cultural principles (One Microsoft, Awareness, Curiosity, Courage)
---

# Connect Perspective Generator

Generate thoughtful Microsoft Connect perspective feedback aligned with Microsoft's Performance & Development philosophy and cultural principles.

## Workflow

### Input

User provides either:
1. **A file path** after the command (e.g., `/perspective observations/aki.md`)
2. **Direct observations** in the message

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
