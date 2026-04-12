# Research Skill Graph

A markdown-based research system that takes one question and produces a multi-angle analysis through 8 independent lenses. No subscriptions, no fancy tools — just a folder of `.md` files and an AI agent.

This is a prompt engineering framework — a structured set of instructions that guides AI agents through multi-perspective research. Its value comes from constrained, diverse analysis passes that force thinking from angles you'd otherwise skip.

Instead of 50 open tabs and surface-level summaries, this system forces structured thinking through 8 research lenses, each one rethinking the question from a fundamentally different angle. The tension between lenses is where the real insight lives.

## The 8 Lenses

| Lens | Angle |
|------|-------|
| **Technical** | What do the numbers actually say? Data only, no narrative. |
| **Economic** | Follow the money. Who pays, who profits, what incentives drive behavior? |
| **Historical** | What patterns repeat? What's been tried before? |
| **Geopolitical** | Power dynamics — states, corporations, networks. Who holds leverage? |
| **Contrarian** | What if the consensus is wrong? Who benefits from the current narrative? |
| **First Principles** | Forget everything. Rebuild from fundamental truths only. |
| **Ethical** | What SHOULD happen? What values are in tension? Who bears the cost? |
| **Cultural** | How do people actually behave? What cultural factors shape this? |

Not all 8 lenses run for every question. See `research-frameworks.md` for core vs. optional lens designations per question type and domain.

## Structure

```
├── index.md                           — Command center. Start every research here.
├── research-log.md                    — Tracks all projects for compound knowledge.
├── methodology/
│   ├── research-frameworks.md         — Pick the right approach for your question type.
│   ├── question-formulation.md        — Sharpen your question before research begins.
│   ├── source-evaluation.md           — 5-tier system for judging source credibility.
│   ├── synthesis-rules.md             — How to combine findings without flattening nuance.
│   ├── contradiction-protocol.md      — What to do when sources or lenses disagree.
│   ├── output-evaluation.md           — Quality criteria for the 4 output types.
│   ├── knowledge-maintenance.md       — Keeping the knowledge base fresh as it grows.
│   └── retrospective-template.md      — Post-project review template.
├── lenses/
│   ├── technical.md
│   ├── economic.md
│   ├── historical.md
│   ├── geopolitical.md
│   ├── contrarian.md
│   ├── first-principles.md
│   ├── ethical.md
│   └── cultural.md
├── templates/
│   ├── executive-summary-template.md  — Structure for the final synthesis.
│   ├── deep-dive-template.md          — Structure for the full lens-by-lens analysis.
│   ├── key-players-template.md        — Structure for mapping actors and influence.
│   └── open-questions-template.md     — Structure for documenting unknowns.
├── projects/                          — One subfolder per research topic.
├── sources/
│   └── source-template.md             — Template for processing each major source.
└── knowledge/
    ├── concepts.md                    — Key terms and mental models (grows over time).
    └── data-points.md                 — Hard numbers with attribution (grows over time).
```

## How to Use

### Option 1: AI Project Context (e.g., Claude Projects, custom GPTs)

1. Create a new project in your AI platform's knowledge/context system
2. Upload all files from this folder to the project knowledge
3. Open `index.md` and fill in:
   - **Research Question** — the one thing you want answered
   - **Scope** — what's in, what's out
   - **Time Horizon** — how far back and forward to look
   - **Output Goal** — what decision this research informs
4. Start a conversation: *"Follow the execution instructions in index.md"*
5. The AI runs through the lenses and produces 4 output files: executive summary, deep dive, key players, and open questions

### Option 2: AI Coding Agent (e.g., Claude Code, Cursor, Aider)

1. Open your AI coding agent pointed at this directory
2. Edit `index.md` with your research question
3. Tell the agent to follow the execution instructions in `index.md`
4. The agent reads and writes files directly — updating knowledge, creating project subfolders, and logging results. The system evolves itself.

### Option 3: Paste Context (works anywhere)

Copy `index.md` + the relevant lens files into any AI chat. Less powerful but portable.

## Research Frameworks

The system supports 4 types of questions, each with recommended core lenses and optional expansion lenses:

- **"Is X true?"** (Verification) — core: technical, contrarian, historical
- **"Why is X happening?"** (Causal Analysis) — core: historical, economic, technical
- **"What happens if X?"** (Scenario Planning) — core: first principles, technical, economic
- **"What should I do about X?"** (Decision Support) — all 8 lenses, rank by agreement

Three depth levels: Quick Scan (30 min, 3 core lenses), Standard (2-3 hours, core + expansion), Deep Dive (1-2 days, all lenses, 50+ sources).

## The Compound Effect

This system gets better every time you use it:

- `knowledge/concepts.md` and `knowledge/data-points.md` accumulate across all projects
- `research-log.md` tracks every project with key findings and connections
- Open questions from one research become the starting point for the next
- After 5 projects, your AI starts with hundreds of verified data points and dozens of defined concepts
- See `methodology/knowledge-maintenance.md` for keeping this knowledge base fresh

For a clean slate, use only `methodology/` and `lenses/` — same system, fresh brain.

## Intellectual Lineage

This system draws on established analytical traditions:

- **Structured Analytic Techniques (SATs)** — The US Intelligence Community's toolkit for rigorous analysis, developed from the 1990s onward. The multi-lens approach mirrors SAT methodology; the source tier system adapts IC source grading.
- **Analysis of Competing Hypotheses (ACH)** — Richards Heuer's framework for weighing evidence across multiple hypotheses. The synthesis rules and contradiction protocol are direct descendants.
- **Six Thinking Hats** — Edward de Bono's parallel thinking method (1985). Six defined perspectives applied sequentially to a problem. Key lesson borrowed: mode-switching is hard and requires deliberate isolation between perspectives.
- **Devil's Advocacy & Red Teaming** — The Contrarian lens formalizes the intelligence community's practice of designated dissent to prevent groupthink.
- **Socratic Method & Cartesian Doubt** — The First Principles lens applies systematic doubt: strip away assumptions, rebuild from what can be known with certainty.
- **Realist International Relations Theory** — The Geopolitical lens draws on the realist tradition: states as primary actors, power as the currency, interests over ideology — extended to include non-state actors and non-Western frameworks.
- **Public Choice Theory** — The Economic lens borrows from Buchanan and Tullock: analyze political and social outcomes through the lens of individual incentives, not stated intentions.
- **Normative Ethics** — The Ethical lens draws on consequentialist, deontological, and virtue ethics traditions, plus Rawlsian justice and stakeholder theory.
- **Behavioral Economics & Cultural Theory** — The Cultural lens draws on Kahneman and Tversky's work on systematic deviations from rational choice, Hofstede's cultural dimensions, and anthropological traditions.

The system's core insight — that tension between perspectives is where the real insight lives — echoes the Hegelian dialectic (thesis-antithesis-synthesis), adapted from a binary framework to a multi-perspective ensemble.

## Visualize with Obsidian (optional)

Open this folder as a vault in [Obsidian](https://obsidian.md). The `[[wikilinks]]` throughout all files create a connected graph with `index.md` at the center, lenses radiating out, and methodology files connecting to everything. Graph view helps you spot research gaps and unexpected connections between projects.
