# Research Skill Graph — Command Center

## 1. Mission

Deep research system that takes ONE question and produces a multi-angle analysis no single Google search or AI prompt could ever match.

Instead of 50 open tabs and scattered notes, this system forces structured thinking through 8 research lenses, each one rethinking the question from a fundamentally different angle.

This is a prompt engineering framework — a structured set of instructions that guides AI agents through multi-perspective research. Its value comes from constrained, diverse analysis passes, not from any single lens.

Research Question: [PASTE YOUR QUESTION HERE]
Scope: [DEFINE BOUNDARIES — what's in, what's out]
Time Horizon: [how far back and forward are we looking?]
Output Goal: [what decision does this research inform?]

## Prior Research (optional — for compound mode)
Check [[research-log]] for previous research that may connect to this question.
Relevant prior projects: [link any related projects from research-log.md, or leave empty for clean slate]

## 2. Node Map

Every node below is a knowledge file. Read the relevant ones before executing any task. The [[wikilinks]] are clickable — follow them.

### Methodology
- [[research-frameworks]] — how to approach different types of questions. start here to pick the right research structure
- [[question-formulation]] — how to sharpen your question before research begins. scope narrowing, assumption surfacing, success criteria
- [[source-evaluation]] — criteria for judging if a source is worth trusting. tier system from primary data to random blog posts
- [[synthesis-rules]] — how to combine findings across lenses without losing nuance. the hardest part of research
- [[contradiction-protocol]] — what to do when sources disagree. this is where the real insights hide
- [[output-evaluation]] — quality criteria for the 4 output types. evaluate before finalizing
- [[knowledge-maintenance]] — keeping the knowledge base fresh and organized as it grows
- [[retrospective-template]] — post-project review for improving the process

### Lenses (the core engine)
- [[technical]] — how does it work mechanically? what do the numbers actually say? strip away narrative, look at data
- [[economic]] — follow the money. who pays, who profits, what markets move, what incentives drive behavior
- [[historical]] — what patterns repeat? what's been tried before? what context does everyone forget?
- [[geopolitical]] — which states, corporations, and power networks shape this? who holds leverage?
- [[contrarian]] — what if the consensus is wrong? who benefits from the current narrative? what's nobody saying?
- [[first-principles]] — forget everything you think you know. rebuild from fundamental truths only
- [[ethical]] — what SHOULD happen? what values are in tension? who bears the cost?
- [[cultural]] — how do people actually behave? what cultural factors shape this beyond rational models?

### Templates
- [[executive-summary-template]] — structure for the final synthesis (500 words max)
- [[deep-dive-template]] — structure for the full analysis organized by lens
- [[key-players-template]] — structure for mapping actors, incentives, and influence
- [[open-questions-template]] — structure for documenting what's still unknown

### Outputs
- [[executive-summary]] — the final synthesis. 500 words max. what did we learn, what does it mean, what's still unknown
- [[deep-dive]] — the full analysis organized by lens, with cross-references and contradictions highlighted
- [[key-players]] — people, organizations, countries that matter most on this topic
- [[open-questions]] — what we STILL don't know after research. often more valuable than what we found

### Knowledge Base
- [[concepts]] — key terms, definitions, mental models relevant to the research
- [[data-points]] — hard numbers, statistics, metrics collected during research. always with source attribution

### Sources
- [[source-template]] — template for processing raw sources into structured notes

## 3. Execution Instructions

When given a research question:

1. Read this file completely. understand the scope and goal
2. Read [[question-formulation]] to sharpen the question: narrow scope, surface assumptions, define success criteria, pre-commit to what would change your mind
3. Read [[research-frameworks]] to pick the right approach for this type of question
4. Read [[source-evaluation]] so you know what counts as good evidence
5. For EACH lens in the order specified by [[research-frameworks]] for your question type:
   a. Read the lens file for its specific angle and questions
   b. Research the topic THROUGH that lens only — respect the Independence Rule
   c. Record findings, sources, and confidence level
   d. Note any contradictions with previous lenses (but do not let them bias your analysis)
6. Read [[contradiction-protocol]] — resolve or document disagreements between lenses
7. Read [[synthesis-rules]] — combine everything
8. Produce all 4 output files using templates: [[executive-summary-template]], [[deep-dive-template]], [[key-players-template]], [[open-questions-template]]
9. Evaluate outputs against [[output-evaluation]] criteria. revise any that don't meet the minimum bar
10. Update [[concepts]] and [[data-points]] with everything learned (see [[knowledge-maintenance]] for format)
11. Complete [[retrospective-template]] and log the project in [[research-log]]

If no specific question type applies, default lens order: technical → economic → historical → geopolitical → contrarian → first-principles → ethical → cultural.

CRITICAL RULE: each lens must RETHINK the question, not just add more information. the technical lens and the contrarian lens should feel like they were written by two different researchers who disagree with each other. that tension is where insight lives.

## 4. Working with AI Limitations

This system asks one AI agent to play 8 different analytical roles. That's inherently limited — the same model arguing with itself produces performative tension, not genuine disagreement. Strategies to mitigate:

- **Temporal separation:** complete each lens in a separate conversation or session to prevent context bleed
- **Adversarial prompting:** after synthesis, explicitly ask "attack this conclusion with the strongest counter-argument you can construct"
- **Human-in-the-loop:** review each lens's output before moving to synthesis. you are the quality control
- **Multi-agent setup:** if your platform supports it, assign different lenses to different agents or model instances

The lens isolation rule ("Independence Rule") in each lens file helps, but it's not foolproof. Your judgment is the ultimate quality gate.

## 5. Your Role as Researcher

The AI executes the lenses. You own the quality. Your responsibilities:

- **Choose the right question type** — a misclassified question wastes every lens that follows
- **Evaluate outputs honestly** — use [[output-evaluation]] criteria. if the contrarian lens feels like it's agreeing with everyone, it failed
- **Curate the knowledge base** — stale data is worse than no data. see [[knowledge-maintenance]]
- **Decide when "done" is done** — more lenses always feel safer. know when diminishing returns have set in
- **Run the retrospective** — the system only improves if you reflect on what worked and what didn't
