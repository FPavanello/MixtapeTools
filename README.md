# MixtapeTools

Practical tools for quantitative empirical research with AI coding assistants (Claude Code, Cursor, etc.).

By [Scott Cunningham](https://github.com/scunning1975), author of [Causal Inference: The Mixtape](https://mixtape.scunning.com/).

---

## Philosophy

These tools emerged from real research projects - months of scraping, data cleaning, estimation, and paper writing with Claude Code. They address problems I kept running into:

1. **AI makes confident mistakes** - especially in code with subtle bugs (race conditions, off-by-one errors, file handling)
2. **Context gets lost** - AI forgets project decisions across sessions
3. **No one reviews AI work** - unlike human code, AI output often goes straight to production
4. **Tacit knowledge is hard to transfer** - I know what makes a good research presentation, but articulating it is hard

## What's Included

### `/claude`

**`CLAUDE.md`** - Template for research project context. Keeps AI grounded in your project's specifics: data sources, identification strategy, collaborators, decisions made.

**`referee2.md`** - Adversarial reviewer agent. Spawns a separate, skeptical AI to review code/analysis and produce a formal referee report. Forces you to fix issues or justify your choices. Like an R&R process before you submit.

### `/presentations`

**`rhetoric_of_decks.md`** - Principles for structuring research presentations. Based on the tacit knowledge embedded in thousands of good (and bad) academic talks.

### `/examples`

Sanitized examples from real projects showing these tools in action.

---

## Quick Start

### Using Referee 2

1. Complete some code or analysis with Claude
2. Open a new conversation
3. Paste the contents of `referee2.md` as system context
4. Paste your code/analysis and ask for a referee report
5. Take the report back to your original Claude conversation
6. Address each concern or justify not addressing it
7. Iterate until Referee 2 accepts

### Using CLAUDE.md

1. Copy the template to your project root
2. Fill in your project specifics
3. Claude Code will automatically read it and maintain context
4. Update it when you make important decisions ("we dropped X because Y")

---

## The "Design Before Results" Principle

One core philosophy from my research workflow:

> **Do NOT express concern or excitement about point estimates until the design is intentional.**

When estimating causal effects, it's easy to get attached to results - tweaking specifications until you get the "right" answer. This is backwards.

The correct workflow:
1. Design the empirical strategy based on identification arguments
2. Commit to the specification before seeing results
3. Only then interpret the estimates

These tools help enforce that discipline by keeping AI focused on *whether the design is correct*, not on *whether we like the numbers*.

---

## Contributing

These tools are opinionated and reflect my workflow. If you have improvements or alternative approaches for empirical research, PRs welcome.

---

## License

MIT

---

## Acknowledgments

Inspired by [Boris Cherny's ChernyCode](https://github.com/meleantonio/ChernyCode) template for AI coding best practices. Extended for quantitative empirical research workflows.
