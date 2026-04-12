# Meta-Evaluation: The Research Skill Graph Applied to Itself

> **Research Question:** Is the Research Skill Graph an effective system for producing deep, multi-angle analysis of complex questions?
> **Scope:** The system itself — its lenses, methodology, structure, and assumptions
> **Framework:** Type 4 (Decision Support) — all 6 lenses in parallel
> **Output Goal:** Identify what works, what's broken, and what's missing

**A note on paradox:** Evaluating a research system with its own tools is inherently self-referential. The system's blind spots are also this evaluation's blind spots. Where possible, I flag this limitation explicitly.

---

## Lens 1: Technical — What Do the Mechanisms Actually Do?

**METRIC:** System complexity
**VALUE:** 16 markdown files, ~4,000 words of instruction, zero external dependencies
**TREND:** Lean and portable — a strength
**CAVEAT:** Leanness trades off against structural enforcement

### Findings

**1. Lens ordering contradiction.** `index.md` hardcodes a fixed execution order (Technical → Economic → Historical → Geopolitical → Contrarian → First-Principles). But `research-frameworks.md` prescribes *different* lens orderings per question type (e.g., Type 1 Verification uses Technical → Contrarian → Historical). These two files contradict each other. A researcher following `index.md` step-by-step will override the framework-specific optimization that `research-frameworks.md` was designed to provide.

**2. No feedback loops or quality metrics.** The system produces outputs but has no mechanism to evaluate whether those outputs are good. There is no rubric, no comparison baseline, no definition of success. The "compound knowledge effect" (README) is asserted but unmeasurable — you cannot tell if project #5 is actually better than project #1.

**3. Knowledge base scaling.** `concepts.md` and `data-points.md` are flat files with no indexing, tagging, categorization, or search mechanism. After 10+ projects, these become walls of text. The system that prizes structured thinking stores its accumulated knowledge in an unstructured format.

**4. Depth levels are aspirational, not enforced.** "Quick Scan: 30 min, 3 lenses" has no mechanism to constrain scope. An AI agent will use whatever context and effort it applies regardless of these labels. They serve as intent signals but not as operational constraints.

**5. Output templates are referenced but undefined.** The system specifies 4 output files (executive-summary, deep-dive, key-players, open-questions) but provides no templates for them — unlike the well-defined source-template.md. The most important deliverables have the least structural guidance.

### Improvements

- Fix the ordering contradiction: `index.md` should defer to `research-frameworks.md` for lens sequence
- Add `methodology/output-evaluation.md` with quality rubrics and success criteria
- Structure knowledge files with categories, tags, or per-domain separation
- Create output templates for all 4 deliverable types

---

## Lens 2: Economic — Cost, Incentives, and ROI

**ACTOR:** AI provider (token consumption)
**INCENTIVE:** Thoroughness costs tokens; brevity saves them
**MAGNITUDE:** A Deep Dive (50+ sources, 6 lenses) can consume 100k+ tokens per run
**IMPLICATION:** Token cost is the dominant resource constraint, yet the system never acknowledges it

### Findings

**1. The single-agent tension problem.** The system's core thesis is that tension between lenses produces insight. But when the same AI model writes both the Technical lens and the Contrarian lens in the same session, the "tension" is performative — the model is arguing with itself, constrained by its own priors. This is the system's deepest structural weakness. The economic incentive (use one agent, save cost) directly undermines the analytical incentive (genuine disagreement between perspectives).

**2. Token budget is invisible.** The system defines three depth levels but never links them to actual resource costs. A practitioner has no way to estimate whether a Standard Research run is feasible within their budget, or how much each additional lens costs at the margin.

**3. Opportunity cost of 6 lenses.** Every lens gets roughly 1/6 of total effort. For many questions, the Geopolitical lens is irrelevant (e.g., "Is this algorithm correct?") or the Historical lens adds nothing (e.g., "What should this API return?"). The system partially addresses this with Quick Scan (3 lenses) but never specifies *which* 3 lenses to use for which domains — only which 3 to use for which question *types*.

**4. Knowledge ROI requires maintenance.** Compound knowledge accrues value only if it's maintained. Stale data points (outdated statistics with old sources) are worse than no data points — they create false confidence. The system has no deprecation, review cycle, or freshness indicator for stored knowledge.

### Improvements

- Add token/cost estimates to depth levels
- Address the single-agent problem explicitly: suggest multi-agent setups, adversarial prompting techniques, or human-in-the-loop for the Contrarian lens
- Add domain-based lens selection guidance (not just question-type-based)
- Add `methodology/knowledge-maintenance.md` with review cycles, deprecation rules, and freshness tracking

---

## Lens 3: Historical — Precedents and Patterns

**PRECEDENT:** Structured Analytic Techniques (SATs) — US Intelligence Community, 1990s–present
**SIMILARITY:** High — Analysis of Competing Hypotheses, Devil's Advocacy, Red Team analysis map directly to the Research Skill Graph's architecture
**OUTCOME:** SATs improved intelligence quality when rigorously applied; degraded into checkbox exercises when applied mechanically
**KEY DIFFERENCE:** SATs use multiple human analysts; this system uses a single AI agent

### Findings

**1. The system reinvents established frameworks without acknowledging them.** The Contrarian lens is Devil's Advocacy. The synthesis rules approximate Analysis of Competing Hypotheses (ACH). The source tier system mirrors intelligence community source grading. These are well-studied techniques with decades of refinement. By not acknowledging its intellectual lineage, the system misses the lessons already learned — particularly around the problem of a single analyst performing multiple roles (exactly the single-agent problem identified above).

**2. Six Thinking Hats parallel.** Edward de Bono's Six Thinking Hats (1985) uses the same structure: 6 defined perspectives applied sequentially to a problem. De Bono's key finding was that **mode-switching is hard** — people bleed between hats. The same applies to AI: without strong isolation instructions, the Technical lens's conclusions leak into the Economic lens's analysis. The system's lens files are well-defined in isolation but lack explicit "forget previous lens conclusions" instructions.

**3. The dialectical scaling problem.** Hegelian dialectic works with thesis-antithesis-synthesis — a binary tension. This system creates a 6-way tension, which makes synthesis combinatorially harder. With 6 lenses, there are 15 possible pairwise tensions. The synthesis-rules.md file acknowledges this is hard but doesn't provide tools to manage the complexity (e.g., prioritized tension pairs, structured comparison matrices).

**4. No system evolution log.** The project path (`researcher2.0`) implies a v1 existed. But there is no record of what was learned, what changed, or why. A system that prizes historical context for its research subjects keeps no historical context about itself.

### Improvements

- Add `methodology/intellectual-lineage.md` documenting predecessors (SATs, Six Thinking Hats, ACH) and what to borrow from each
- Add explicit lens isolation instructions: "Do not reference findings from previous lenses; rethink from scratch"
- Add a structured tension-pair matrix to synthesis methodology
- Add `CHANGELOG.md` for system evolution tracking

---

## Lens 4: Geopolitical — Power Dynamics and Dependencies

**ACTOR:** AI model provider (Anthropic/Claude)
**POSITION:** Sole execution engine for the system
**LEVERAGE:** Complete — the system cannot function without the AI
**VULNERABILITY:** Model changes, policy changes, pricing changes, capability changes all break the system without recourse

### Findings

**1. Single-provider dependency.** The system is designed for three deployment modes — all Claude-specific (Claude Projects, Claude Code, paste context). There is no consideration of portability, model-agnostic operation, or graceful degradation if the AI provider changes behavior. The execution instructions reference Claude-specific affordances.

**2. The user's role is understated.** The system positions the AI as the researcher and the user as the question-asker. But output quality depends critically on user judgment: choosing the right question type, setting appropriate scope, evaluating whether the Contrarian lens is genuinely contrarian or merely performative, and curating the knowledge base. The system has no guidance for the user's quality-control responsibilities.

**3. Western analytical bias.** The Geopolitical lens asks about "countries, power dynamics, alliances" — a state-centric Westphalian framework. Non-state actors (corporations, NGOs, decentralized networks), civilizational analysis, and non-Western analytical traditions (e.g., Chinese stratagems, Ubuntu philosophy, Islamic jurisprudence frameworks) are absent. The lens set itself reflects a particular worldview.

**4. Language and source bias.** The source evaluation system implicitly assumes English-language sources. Tier 1 examples (UN, World Bank, peer-reviewed studies) skew toward institutions that publish primarily in English. For genuinely global research questions, this creates systematic blind spots.

### Improvements

- Add model-agnostic guidance; keep deployment instructions general where possible
- Add a `methodology/user-guide.md` or section defining the user's role in quality control
- Broaden the Geopolitical lens to explicitly include non-state actors and non-Western analytical frameworks
- Add a note in source-evaluation about language bias and the value of non-English sources

---

## Lens 5: Contrarian — What if This Whole System Is Wrong?

**CONSENSUS:** Structured multi-lens analysis produces deeper, more nuanced research than unstructured thinking
**COUNTER-ARGUMENT:** Rigid decomposition fragments understanding; a skilled analyst thinking holistically may outperform 6 template-driven passes
**CREDIBILITY:** Medium-high — there is genuine evidence on both sides
**WHO BENEFITS:** The system's creator benefits from the consensus; users benefit from knowing the counter-argument

### Findings

**1. Decomposition vs. holistic thinking.** The system's fundamental bet is that breaking a question into 6 perspectives and recombining them beats unconstrained analysis. This is the "ensemble methods" argument — diverse weak models combine into a strong model. But ensemble methods require that component models be **diverse and independent**. When one AI model generates all 6 lenses sequentially in one session, neither condition is met. The system may produce the *appearance* of multi-angle analysis while actually reflecting one model's coherent worldview repackaged 6 times.

**2. Why 6 lenses? Why these 6?** The system provides no first-principles justification for its lens selection. Why not 4 (cutting Geopolitical and Historical for most topics)? Why not 8 (adding Ethical and Cultural)? The number and selection appear to be authorial judgment, not derived from any framework. The system's own First-Principles lens would demand this justification.

**3. The Contrarian lens is the weakest by design.** A lens whose job is "challenge the consensus" is paradoxically the easiest to perform poorly. The AI can write surface-level "but what if not?" statements that feel contrarian without genuinely threatening the analysis. There are no structural guardrails requiring the Contrarian lens to achieve a minimum level of actual dissent — no pre-mortem protocol, no required bet-against-consensus exercise, no adversarial scoring.

**4. Untested system.** The projects/ directory is empty. Zero completed research projects. The system is a theory of research methodology, not a proven practice. It may be elegant on paper and unworkable in execution — output too long, synthesis too hard, knowledge base too noisy, or simply slower than a good researcher thinking freely.

**5. Synthesis may destroy the value analysis creates.** The synthesis rules require combining 6 lens outputs into a coherent narrative. But the value of multi-lens analysis is precisely that it *doesn't* collapse into one narrative — it preserves irreducible tension. The synthesis step may systematically destroy the system's most valuable output (productive disagreement) in favor of false coherence.

### Improvements

- Add explicit justification for the lens set; make lenses modular and customizable
- Strengthen the Contrarian lens with structured adversarial techniques: pre-mortem analysis, required bet-against-consensus, adversarial scoring criteria
- Run pilot projects immediately — 3 minimum across different question types — before refining further
- Revise synthesis rules to preserve irreducible tensions rather than resolving them
- Add a "holistic pass" after the 6-lens analysis: one unconstrained analysis that can challenge or override the structured output

---

## Lens 6: First Principles — Stripping to Fundamentals

**AXIOM:** All analysis is model-dependent; combining diverse, independent models approximates truth better than any single model
**REASONING:** The Research Skill Graph is an ensemble method applied to reasoning → its value depends on component diversity and independence → current architecture fails both criteria (same model, sequential execution, no isolation)
**CONCLUSION:** The core architecture is sound in theory but structurally undermined in implementation
**CONFLICTS WITH:** The system's implicit assumption that one AI agent can genuinely produce 6 independent perspectives

### Findings

**1. Question formulation is the most neglected critical step.** `index.md` allocates one line to it: "Research Question: [PASTE YOUR QUESTION HERE]." From first principles, the quality of any analysis is bounded by the quality of the question. A vague question produces vague analysis regardless of how many lenses you apply. The system invests heavily in analytical machinery and almost nothing in ensuring the input is well-formed. This is like building a precision instrument with no calibration step.

**2. Synthesis is under-invested relative to its difficulty.** The system allocates 6 files to lenses (~2,400 words of instruction) and 1 file to synthesis (~600 words). Yet `synthesis-rules.md` itself acknowledges "this is the hardest part of research." From first principles, the hardest step should receive the most structural support, not the least. The synthesis methodology needs expansion — possibly into multiple files covering agreement resolution, tension preservation, confidence calibration, and narrative construction separately.

**3. The system is a prompt engineering framework.** Stripped to fundamentals, this is a structured prompt template that constrains AI behavior into sequential, lens-specific analysis passes. Its value proposition is that constrained generation produces higher quality than unconstrained generation. This is empirically supported in prompt engineering research — but it means the system should be evaluated and refined as a prompting strategy, with A/B testing against simpler prompts.

**4. Missing: feedback integration.** The system has no mechanism for incorporating feedback from completed projects. After a project, there is no structured step to ask: "What did the system get wrong? Which lens was most/least valuable? What would I do differently?" Without this, the system cannot improve itself — it can only accumulate knowledge, not wisdom.

**5. The 80/20 is probably 3 lenses, not 6.** For most questions, 80% of the insight comes from 2-3 lenses. The remaining 3-4 lenses add diminishing returns at increasing cost. A first-principles design would optimize for this: a core set of 2-3 lenses selected per question, with the remaining lenses as optional depth expansions.

### Improvements

- Add `methodology/question-formulation.md` with structured guidance: scope narrowing, assumption surfacing, success criteria definition, and "what would change my mind" pre-commitment
- Expand synthesis methodology into multiple sub-documents
- Add a post-project retrospective template to the methodology
- Implement a core/optional lens distinction: 2-3 mandatory lenses per question type, remainder optional based on relevance

---

## Synthesis

### Agreement Map

| Finding | Lenses That Agree | Confidence |
|---|---|---|
| Question formulation is critically under-specified | Technical, Economic, First Principles, Contrarian | **High** |
| Single-agent produces fake inter-lens tension | Economic, Contrarian, First Principles, Historical | **High** |
| System is untested — needs pilot projects immediately | All 6 | **High** |
| Synthesis methodology is under-invested | Technical, First Principles, Historical, Contrarian | **High** |
| Knowledge base needs structure and maintenance protocol | Technical, Economic, Historical, First Principles | **High** |
| Lens ordering contradiction between index.md and research-frameworks.md | Technical | **High** (mechanical bug) |
| The lens set should be justified and customizable | Contrarian, First Principles, Economic | **Medium** |
| Output templates are missing | Technical | **Medium** |

### Tension Map

| Tension | What It Reveals |
|---|---|
| **Technical vs. Contrarian:** The system is mechanically clean, but the Contrarian lens questions whether the mechanism works at all | The architecture is sound *if* the independence problem is solved; unsound if it isn't |
| **Historical vs. First Principles:** Precedents (SATs, Six Hats) validate multi-perspective analysis, but first principles says the specific configuration is unjustified | Borrow from validated predecessors rather than reinventing; but adapt, don't copy |
| **Economic vs. Geopolitical:** Token costs say "fewer lenses"; platform dependency says "more portability" | These are different axes of optimization that shouldn't be collapsed into one decision |
| **Contrarian vs. Synthesis Rules:** The Contrarian lens says synthesis destroys valuable tension; synthesis rules say combination is the whole point | The resolution: synthesis should *preserve* key tensions as findings, not resolve them into false agreement |

### Second-Order Insights

1. **The system's greatest strength is also its greatest weakness.** Forcing structured multi-angle analysis is powerful as a thinking discipline. But when implemented as sequential single-agent generation, it produces the appearance of disagreement without the substance. The system needs architectural changes (multi-agent, human-in-the-loop, or stronger isolation) to deliver on its core promise.

2. **The compound knowledge system is the most strategically valuable and least developed component.** If the knowledge base works well, project #10 is dramatically better than project #1. If it doesn't, it's dead weight. This component deserves more investment than the lenses themselves.

3. **The system is more valuable as a thinking discipline than as a production pipeline.** Even if the outputs are imperfect, the *process* of going through 6 lenses teaches the user to think from multiple angles. This suggests the system's real value may be pedagogical, not analytical — and the design should reflect that.

### Confidence Calibration

| Claim | Evidence | Confidence | What Would Change My Mind |
|---|---|---|---|
| The system needs pilot projects before further design iteration | Zero completed projects in projects/ | **High** | Evidence that the system has been used extensively outside this repo |
| Question formulation needs its own methodology file | index.md has one line for it; all other steps have dedicated files | **High** | Showing that vague questions produce good outputs anyway |
| 6 lenses are approximately right, but 1-2 should be added or reconfigured | Gap analysis shows missing Ethical and Cultural dimensions; overlap between Economic and Geopolitical | **Medium** | A completed project showing all 6 lenses contributed unique, non-overlapping insight |
| The single-agent tension problem is real and significant | Same model writing all lenses in one session cannot achieve true independence | **Medium** | An experiment showing AI-generated contrarian analysis that genuinely surprised the other lenses' conclusions |
| Synthesis methodology needs significant expansion | 600 words for "the hardest part of research" vs. 2,400 for the lenses | **Medium** | A completed project where synthesis worked well with current guidance |

---

## Recommendations

### Priority 1: Do Before Anything Else

**Run 3 pilot projects.** Pick one Type 1 (Verification), one Type 2 (Causal Analysis), and one Type 3 (Scenario Planning) question. Run them through the system as-is. Document what worked, what broke, what was wasteful. Every recommendation below is theoretical until validated against real execution.

**Fix the lens ordering contradiction.** `index.md` Step 4 should say "Follow the lens order specified in research-frameworks.md for your question type" instead of hardcoding a sequence.

### Priority 2: Add Missing Methodology

**Add `methodology/question-formulation.md`:**
- Scope narrowing protocol (too broad → specific)
- Assumption surfacing (what are you already assuming?)
- Success criteria (what would a good answer look like?)
- Pre-commitment: "What evidence would change my mind?"

**Add `methodology/output-evaluation.md`:**
- Quality rubric for each of the 4 output types
- Minimum bar: what makes an executive summary "done"?
- Comparison framework: was this better than an unstructured prompt?

**Add `methodology/knowledge-maintenance.md`:**
- Review cycle (every N projects, audit knowledge base)
- Freshness indicators (date stamps, expiry flags)
- Deprecation rules (when to remove stale data points)
- Scaling strategy (categories, tags, or domain-specific files)

### Priority 3: Strengthen Existing Components

**Expand synthesis methodology:**
- Split into sub-sections or files: agreement resolution, tension preservation, confidence calibration, narrative construction
- Add a structured tension-pair matrix (15 possible pairs for 6 lenses)
- Add explicit guidance: "Preserve irreducible tensions as findings, not problems to solve"

**Strengthen the Contrarian lens:**
- Add pre-mortem protocol: "Assume this analysis is wrong. Why?"
- Add required bet-against-consensus: "If you had to wager against the main finding, what's your case?"
- Add adversarial scoring: rate the Contrarian output's genuine threat level to other lenses (1-5)

**Add lens isolation instructions:**
- Each lens file should include: "Do not reference findings from previous lenses. Approach the question fresh. Your analysis should be able to stand alone."

**Add post-project retrospective template:**
- What did each lens contribute?
- Which lens was most/least valuable?
- Where did the system help vs. hinder?
- What would you change for next time?

### Priority 4: Consider Adding or Reconfiguring Lenses

**Candidate new lens: Ethical/Philosophical**
- Angle: What *should* happen? What values are in tension?
- Why: Many research questions (AI policy, bioethics, inequality) are fundamentally normative. The current system has no lens for normative reasoning.
- Output format: VALUE, TENSION, STAKEHOLDER IMPACT, FRAMEWORK, IMPLICATION

**Candidate new lens: Cultural/Behavioral**
- Angle: How do people actually behave? What cultural factors shape this?
- Why: The gap between Economic (rational incentives) and actual human behavior is well-documented. Psychology, sociology, and cultural context are absent.
- Output format: BEHAVIOR, DRIVER, CULTURAL CONTEXT, DEVIATION FROM RATIONAL, EVIDENCE

**Consider refining existing lenses:**
- Economic and Geopolitical overlap at the macro-actor level. Consider narrowing Economic to purely financial/market analysis and broadening Geopolitical to "Power Dynamics" (including non-state actors).
- First Principles and Contrarian both challenge assumptions. Add explicit differentiation: First Principles rebuilds from axioms *without knowledge of consensus*; Contrarian starts *from* consensus and attacks it.

### Priority 5: Architectural Considerations

**Address the single-agent tension problem:**
- Option A: Multi-agent setup — different model instances or temperature settings per lens
- Option B: Human-in-the-loop — user writes or reviews the Contrarian lens
- Option C: Adversarial prompting — explicit instructions to contradict previous lenses with evidence
- Option D: Temporal separation — run lenses in separate sessions to prevent context bleed

**Make lenses modular:**
- Allow custom lens sets per project
- Define core lenses (2-3 per question type) vs. optional expansion lenses
- Add guidance for when to skip a lens

**Acknowledge the system's nature:**
- Add a section to README: "This is a prompt engineering framework" — helps users understand what they're optimizing
- Add intellectual lineage section: SATs, Six Thinking Hats, ACH — what to borrow from each

---

## Open Questions

1. **Does structured multi-lens analysis actually outperform a single well-crafted prompt?** No evidence exists within this system. Needs A/B testing.
2. **What is the optimal number of lenses?** The current 6 is authorial judgment. Is 3 core + 3 optional better? Is 8 with added Ethical and Cultural better?
3. **Can a single AI agent produce genuinely independent lens analyses?** The theoretical answer is "probably not fully." The practical answer requires experimentation.
4. **How does the knowledge base scale?** At what project count does it become unwieldy? What's the maintenance cost?
5. **Is the system's value primarily analytical or pedagogical?** If pedagogical (teaching multi-angle thinking), the design implications differ significantly from an analytical tool.
