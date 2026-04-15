# Research Skill Graph

This is a multi-lens research system. When the user asks a research question, follow the execution instructions in `index.md`.

## Quick Reference

- **8 lenses:** technical, economic, historical, geopolitical, contrarian, first-principles, ethical, cultural
- **4 question types:** Verification, Causal Analysis, Scenario Planning, Decision Support (see `methodology/research-frameworks.md`)
- **3 depth levels:** Quick Scan (3 core lenses), Standard (core + expansion), Deep Dive (all lenses, 50+ sources)
- **4 outputs:** executive-summary, deep-dive, key-players, open-questions (templates in `templates/`)

## How to Handle Research Requests

When the user provides a research question (directly or via the /research command):

1. Read `index.md` for full execution instructions
2. Sharpen the question using `methodology/question-formulation.md`
3. Classify the question type and pick lens order from `methodology/research-frameworks.md`
4. Run each lens independently (respect the Independence Rule in each lens file)
5. Synthesize using `methodology/synthesis-rules.md`
6. Produce outputs using templates in `templates/`
7. Evaluate against `methodology/output-evaluation.md`
8. Update `knowledge/` and `projects/research-log.md`

## Project Structure

- `methodology/` — 8 files defining how to research, evaluate sources, synthesize, and maintain quality
- `lenses/` — 8 analytical perspectives, each with core questions and output format
- `templates/` — output structure for the 4 deliverables
- `knowledge/` — accumulated concepts and data points across projects
- `projects/` — one subfolder per completed research project
- `sources/` — source processing template

## Rules

- Each lens must rethink the question independently — do not let previous lens findings bias the next
- Preserve irreducible tensions as findings, not problems to resolve
- Always cite source tiers (see `methodology/source-evaluation.md`)
- Create project subfolder in `projects/` for each research run
- Log every project in `projects/research-log.md`
