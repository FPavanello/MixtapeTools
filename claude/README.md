# Claude Tools

> **What's in this folder:** Templates and personas for working with Claude Code on research projects.

---

## Contents

### `CLAUDE.md` — Project Context Template

**What it is:** A template you copy into each project to give Claude persistent memory.

**How to use it:**
```bash
# Copy to your project root
cp CLAUDE.md /path/to/your/project/

# Edit with your project specifics
# Claude will automatically read it every session
```

**What goes in it:**
- Project description and research question
- Collaborator names (so Claude addresses them correctly)
- Key decisions you've made (so Claude doesn't re-suggest dropped ideas)
- Data sources, identification strategy, variable definitions
- Current status ("we're in the estimation phase")

**Why it matters:** Without this, every new Claude session starts from zero. You waste time re-explaining context. Worse, Claude might suggest things you've already tried and rejected.

---

### `referee2.md` — Adversarial Reviewer

**What it is:** A persona/process document for conducting adversarial code review.

**How to use it:**
1. Finish some code or analysis in your main Claude session
2. **Open a new, separate Claude conversation**
3. Paste the contents of `referee2.md` at the start
4. Paste your code/analysis
5. Ask for a referee report
6. Take the report back to your original session
7. Address concerns or justify not addressing them
8. Repeat until Referee 2 accepts

**Why a separate conversation?** The whole point is adversarial review. If you ask the same Claude that wrote the code to review it, you're grading your own homework. True separation catches real bugs.

**What Referee 2 checks:**
- Race conditions, edge cases, off-by-one errors
- File I/O issues, encoding problems
- Statistical assumptions, identification concerns
- Logic gaps, unstated assumptions

**Output format:** A formal referee report with:
- Major concerns (must address)
- Minor concerns (should address)
- Questions for authors
- Verdict: Accept / Minor revisions / Major revisions / Reject

---

## Philosophy

These tools exist because:

1. **AI makes confident mistakes** — especially subtle bugs that compile fine but fail silently
2. **Context gets lost** — without `CLAUDE.md`, every session starts fresh
3. **No one reviews AI work** — Referee 2 forces adversarial review before deployment
4. **"Design before results"** — keep Claude focused on whether the design is correct, not whether we like the numbers
