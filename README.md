# Research Skill Graph

A markdown-based research system that takes one question and produces a multi-angle analysis through 6 independent lenses. No subscriptions, no fancy tools — just a folder of `.md` files and one AI agent.

Instead of 50 open tabs and surface-level summaries, this system forces structured thinking through 6 research lenses, each one rethinking the question from a fundamentally different angle. The tension between lenses is where the real insight lives.

## The 6 Lenses

| Lens | Angle |
|------|-------|
| **Technical** | What do the numbers actually say? Data only, no narrative. |
| **Economic** | Follow the money. Who pays, who profits, what incentives drive behavior? |
| **Historical** | What patterns repeat? What's been tried before? |
| **Geopolitical** | Zoom out to the global chessboard. Power dynamics, alliances, conflicts. |
| **Contrarian** | What if the consensus is wrong? Who benefits from the current narrative? |
| **First Principles** | Forget everything. Rebuild from fundamental truths only. |

## Structure

```
├── index.md                    — Command center. Start every research here.
├── research-log.md             — Tracks all projects for compound knowledge.
├── methodology/
│   ├── research-frameworks.md  — Pick the right approach for your question type.
│   ├── source-evaluation.md    — 5-tier system for judging source credibility.
│   ├── synthesis-rules.md      — How to combine findings without flattening nuance.
│   └── contradiction-protocol.md — What to do when sources or lenses disagree.
├── lenses/
│   ├── technical.md
│   ├── economic.md
│   ├── historical.md
│   ├── geopolitical.md
│   ├── contrarian.md
│   └── first-principles.md
├── projects/                   — One subfolder per research topic.
├── sources/
│   └── source-template.md      — Template for processing each major source.
└── knowledge/
    ├── concepts.md             — Key terms and mental models (grows over time).
    └── data-points.md          — Hard numbers with attribution (grows over time).
```

## How to Use

### Option 1: Claude Projects (recommended)

1. Create a new Project on [claude.ai](https://claude.ai)
2. Upload all files from this folder to the project knowledge
3. Open `index.md` and fill in:
   - **Research Question** — the one thing you want answered
   - **Scope** — what's in, what's out
   - **Time Horizon** — how far back and forward to look
   - **Output Goal** — what decision this research informs
4. Start a conversation: *"Follow the execution instructions in index.md"*
5. Claude runs through all 6 lenses and produces 4 output files: executive summary, deep dive, key players, and open questions

### Option 2: Claude Code (most powerful)

1. Open Claude Code pointed at this directory
2. Edit `index.md` with your research question
3. Tell Claude to follow the execution instructions in `index.md`
4. Claude reads and writes files directly — updating knowledge, creating project subfolders, and logging results. The system evolves itself.

### Option 3: Paste Context (works anywhere)

Copy `index.md` + the relevant lens files into any AI chat. Less powerful but portable.

## Research Frameworks

The system supports 4 types of questions, each with a recommended lens order:

- **"Is X true?"** (Verification) — start with technical, then contrarian, then historical
- **"Why is X happening?"** (Causal Analysis) — start with historical, then economic, then technical
- **"What happens if X?"** (Scenario Planning) — start with first principles, then technical, then economic
- **"What should I do about X?"** (Decision Support) — run all 6 lenses, rank by agreement

Three depth levels: Quick Scan (30 min, 3 lenses), Standard (2-3 hours, all 6), Deep Dive (1-2 days, 50+ sources).

## The Compound Effect

This system gets better every time you use it:

- `knowledge/concepts.md` and `knowledge/data-points.md` accumulate across all projects
- `research-log.md` tracks every project with key findings and connections
- Open questions from one research become the starting point for the next
- After 5 projects, your AI starts with hundreds of verified data points and dozens of defined concepts

For a clean slate, use only `methodology/` and `lenses/` — same system, fresh brain.

## Intellectual Lineage

This system draws on established analytical traditions:

- **Structured Analytic Techniques (SATs)** — The US Intelligence Community's toolkit for rigorous analysis, developed from the 1990s onward. The multi-lens approach mirrors SAT methodology; the source tier system adapts IC source grading.
- **Analysis of Competing Hypotheses (ACH)** — Richards Heuer's framework for weighing evidence across multiple hypotheses. The synthesis rules and contradiction protocol are direct descendants.
- **Six Thinking Hats** — Edward de Bono's parallel thinking method (1985). Six defined perspectives applied sequentially to a problem. Key lesson borrowed: mode-switching is hard and requires deliberate isolation between perspectives.
- **Devil's Advocacy & Red Teaming** — The Contrarian lens formalizes the intelligence community's practice of designated dissent to prevent groupthink.
- **Socratic Method & Cartesian Doubt** — The First Principles lens applies systematic doubt: strip away assumptions, rebuild from what can be known with certainty.
- **Realist International Relations Theory** — The Geopolitical lens draws on the realist tradition: states as primary actors, power as the currency, interests over ideology.
- **Public Choice Theory** — The Economic lens borrows from Buchanan and Tullock: analyze political and social outcomes through the lens of individual incentives, not stated intentions.

The system's core insight — that tension between perspectives is where the real insight lives — echoes the Hegelian dialectic (thesis-antithesis-synthesis), adapted from a binary framework to a multi-perspective ensemble.

## Visualize with Obsidian (optional)

Open this folder as a vault in [Obsidian](https://obsidian.md). The `[[wikilinks]]` throughout all files create a connected graph with `index.md` at the center, lenses radiating out, and methodology files connecting to everything. Graph view helps you spot research gaps and unexpected connections between projects.
