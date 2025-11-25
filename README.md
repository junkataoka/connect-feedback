# Connect Perspective Generator

Generate thoughtful Microsoft Connect perspectives grounded in cultural principles.

## Philosophy

This generator produces feedback that is:
- **Balanced** — Includes both strengths and growth areas (Re-think is optional but encouraged)
- **Empathetic** — Acknowledges context and conditions without being dismissive
- **Actionable** — Provides specific alternatives, not vague suggestions
- **Culturally aligned** — Integrates Microsoft principles naturally, not performatively
- **Bilingual** — Includes mandatory Japanese translation

## Project Structure

```
connect-feedback/
├── .github/
│   └── agents/
│       ├── perspective.md              # Command file (main prompt)
│       ├── templates/
│       │   └── perspective-template.md
│       └── guides/
│           └── cultural-principles.md
├── observations/                        # Input files
│   └── aki.md                          # Example observation file
├── generated_perspectives/              # Output files
│   └── 2025-q4-aki-perspective.md      # Example output
└── README.md
```

## Usage

### Option 1: Use command with file path

```
/perspective observations/aki.md
```

### Option 2: Use command with direct observations

```
/perspective

Generate Connect perspective for Ryo:

Strengths:
- Excellent at debugging complex issues across system boundaries
- Proactively shares findings in team Slack channel
- ...

Development areas:
- Sometimes takes on too much without delegating
- ...
```

## Output Naming Convention

Output files are saved to `generated_perspectives/` directory at project root:

```
generated_perspectives/{YYYY}-{q1|q2|q3|q4}-{name}-perspective.md
```

Where:
- `YYYY` = Current year
- `q1` = January–March
- `q2` = April–June
- `q3` = July–September
- `q4` = October–December
- `name` = Colleague's name (lowercase)

Example: `generated_perspectives/2025-q4-aki-perspective.md`

## Key Differentiators

### vs. Generic Feedback Templates

| Generic | This Generator |
|---------|----------------|
| "Great team player" | Specific behaviors with measurable impact |
| Avoids development feedback | Re-think section required with empathetic framing |
| Corporate buzzwords | Natural language with authentic voice |

### Re-think Section Approach

The growth area section is **not optional**. Real feedback includes development areas. The key is framing:

❌ **Avoid:**
> "Your communication needs improvement."

✅ **Instead:**
> "During tight deadlines, I noticed decisions sometimes moved forward before all stakeholders had input. I recognize that time pressure affects all of us—consider being the person who asks 'Who else should weigh in?' even when things feel urgent."

## Cultural Principles Quick Reference

| Principle | Key Question |
|-----------|--------------|
| 🤝 One Microsoft | "How did this help beyond our team?" |
| 🧠 Awareness | "What conditions contributed to this?" |
| 🔍 Curiosity | "Did they seek to understand first?" |
| 💪 Courage | "Did they speak up or create safety?" |

## Customization

- Edit `templates/feedback-template.md` to adjust section structure
- Expand `guides/cultural-principles.md` with team-specific examples
- Add more examples to `examples/` directory

## Quality Checklist

Before finalizing, verify:

- [ ] 2+ cultural principles integrated
- [ ] Re-think acknowledges context (no blame) — if included
- [ ] Suggestions are specific and actionable
- [ ] Name used consistently (no "you" or pronouns)
- [ ] Past tense throughout
- [ ] 250-350 words total (English section)
- [ ] Japanese translation included and accurate
- [ ] Tone maintained across both languages
