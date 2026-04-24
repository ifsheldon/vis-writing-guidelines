# VIS Writing Guide (VIS/TVCG/CHI)

---

# ✦ 0. Core Principle

Everything in VIS writing serves one goal:

> **Make analytical value and human usefulness immediately legible.**

This sounds simple, but it is the root of most writing decisions.

A VIS paper is not judged primarily by:
- how complex the system is,
- how advanced the model is,
- how many features are implemented.

It is judged by whether a reviewer can quickly understand:

- What problem is being solved?
- Why is it difficult in practice?
- Why does this design make sense?
- What can users *actually do* with it?
- What evidence supports these claims?

A useful mental shift:

> **You are not describing a system. You are making the value of that system visible.**

---

# ✦ 1. Problem Framing

This is the most important layer. If this part is weak, the whole paper feels ungrounded.

## 1.1 Start from a user problem, not a technology trend

A very common mistake is to begin with technology:

❌  
> LLM-driven systems are becoming increasingly powerful...

This is not wrong, but it does not justify a VIS paper.

VIS papers are stronger when they begin with *user difficulty*:

✅  
> As LLM-driven systems become more complex, analysts struggle to understand and control their behavior.

Why this matters:

- VIS is fundamentally about **supporting human analysis**
- so the paper must begin from **human difficulty**, not system capability

---

## 1.2 Use the VIS introduction arc

A reliable structure is:

1. Technology or domain creates new opportunities  
2. These opportunities introduce practical challenges  
3. Existing approaches fail in specific ways  
4. This leads to a concrete gap

Example pattern:

> Recent advances in X enable Y.  
> However, in practice, users struggle to Z because...  
> Existing approaches fail to...  
> Therefore, users need support for...

This is stronger than simply saying “existing work is limited,” because it shows:
- *where the problem comes from*  
- *why it matters*

---

## 1.3 Make problems operational

Avoid abstract claims like:

- lack of interpretability  
- lack of transparency  
- high complexity  

These are too vague.

Prefer statements that describe **what users cannot do**:

- cannot inspect intermediate states  
- cannot compare alternatives  
- cannot trace decision paths  
- cannot intervene during the process  

A useful test:

> If you cannot turn the problem into a design requirement, it is still too vague.

---

## 1.4 Frame problems as user needs

Weak:
> The system lacks transparency.

Better:
> Experts cannot trace how high-performing results are produced.

The second version:
- makes the problem **situated**
- implies a **design direction**

---

# ✦ 2. Challenge Decomposition

This is where you show that the problem is understood deeply enough to guide design.

## 2.1 Split into orthogonal challenges

Good VIS papers rarely have one vague “challenge.”  
They split it into 2–3 **distinct dimensions**.

Typical patterns:
- representation vs interaction  
- overview vs detail  
- understanding vs steering  

Bad:
> C1: complexity  
> C2: difficulty  

Good:
> C1: users lack interpretable representations of evolving states  
> C2: users lack mechanisms to intervene during the process  

---

## 2.2 Challenges should imply solutions

A strong challenge formulation already hints at the solution.

Example:

- If challenge = hidden structure  
  → solution = expose structure  

- If challenge = no comparison  
  → solution = enable comparison  

If the mapping is unclear, the challenge is not well formulated.

---

## 2.3 Use task-oriented language

Prefer verbs like:
- inspect
- compare
- trace
- diagnose
- monitor
- steer

These anchor the paper in VIS tasks rather than abstract system properties.

---

# ✦ 3. Design Requirements

This is a critical but often underdeveloped section.

## 3.1 Requirements bridge challenges and design

Bad:
> R1: support interpretability  

Better:
> R1: enable users to inspect how candidate states evolve over time and relate these changes to performance  

Why:
- it is specific enough to guide design  
- but still abstract enough to justify multiple features  

---

## 3.2 Requirements describe support, not features

Good pattern:

> The system should enable users to...

- compare alternatives  
- trace evolution  
- connect patterns to evidence  
- intervene without breaking workflow  

---

## 3.3 Keep requirements minimal and distinct

If you have too many requirements:
- they lose explanatory power  
- they start to feel like feature listing  

A good requirement set feels like a **design logic**, not a checklist.

---

# ✦ 4. Contributions

Contribution writing is where clarity and discipline really show.

## 4.1 Cover three layers

A strong VIS contribution set usually includes:

- problem / design framing  
- system or method  
- evaluation or demonstrated value  

---

## 4.2 State value, not implementation

Weak:
> We implement a new visualization.

Better:
> We introduce a visualization that reveals performance trade-offs across candidates.

The second version answers:
> Why should the field care?

---

## 4.3 Avoid mixing abstraction levels

Do not combine:
- study design  
- system details  
- evaluation outcomes  

into one sentence.

Each contribution should feel clean and focused.

---

# ✦ 5. System Description

This is where many papers become unnecessarily hard to read.

## 5.1 Organize by analytical workflow

Not:
- backend
- modules
- components

But:
- overview
- inspection
- comparison
- steering

Because this matches how users think.

---

## 5.2 Describe views by function

Weak:
> The interface includes a node-link view and a timeline.

Better:
> The interface supports overview, comparison, and detailed inspection through coordinated views.

Then describe each view in detail.

---

## 5.3 Avoid UI inventory writing

Bad:
> left panel, right panel, bottom panel  

This reads like implementation notes.

Instead:
> To support global monitoring...  
> For detailed diagnosis...  
> To compare candidates...  

---

## 5.4 Explain encodings in terms of insight

Good VIS phrasing:

- node size encodes...
- color highlights...
- layout reveals...
- alignment shows...

Always connect encoding → insight.

---

## 5.5 Justify design choices

Whenever a design is non-trivial, explain:

- why this layout?
- why this grouping?
- why this encoding?

Otherwise it feels arbitrary.

---

# ✦ 6. Paragraph Design

Many writing problems are actually paragraph-level problems.

## 6.1 One paragraph = one purpose

Each paragraph should do one thing:

- define a problem  
- explain a challenge  
- describe one view  
- report one finding  

If it tries to do multiple, it becomes unclear.

---

## 6.2 Use the paragraph spine

> claim → detail → payoff

Example:

- sentence 1: what this component does  
- sentence 2–3: how it works  
- last sentence: what this enables  

---

## 6.3 End with analytical value

Bad ending:
> The panel contains a chart and a table.

Better:
> This allows users to verify hypotheses about strategy differences.

---

# ✦ 7. Evaluation Writing

VIS evaluation is about demonstrating analytical usefulness.

## 7.1 State results, not just methods

Weak:
> We conducted a user study.

Better:
> Participants identified patterns faster and compared alternatives with less effort.

---

## 7.2 Tie results to tasks

Avoid:
> improves usability  

Prefer:
> improves users’ ability to compare strategies  

---

## 7.3 Use VIS-style evidence

Strong evidence includes:

- identifying patterns  
- forming hypotheses  
- verifying hypotheses  
- comparing alternatives  
- steering processes  

---

## 7.4 Avoid vague praise

Do not rely on:
- effective  
- useful  
- intuitive  

Replace with concrete outcomes.

---

## 7.5 Interpret results

After reporting, explain:

> why this supports your design

---

# ✦ 8. Sentence-Level Style

## 8.1 Use capability verbs

- supports  
- enables  
- reveals  
- exposes  

These express function clearly.

---

## 8.2 Remove empty adjectives

Words like:
- effective  
- powerful  
- flexible  

add little value without evidence.

---

## 8.3 Prefer concrete nouns

Use:
- states  
- nodes  
- patterns  
- transitions  

Instead of:
- process  
- information  

---

## 8.4 Maintain parallel structure

Bad:
> reveals patterns and helps users compare  

Better:
> reveals patterns for interpretation and supports comparison  

---

## 8.5 One idea per sentence

If a sentence mixes:
- goal + method + result  

→ split it.

---

## 8.6 Avoid repetition

If two sentences say the same thing, compress them.

---

## 8.7 Use simple connectors

Avoid heavy transitions like:
> Specifically, we first...

Prefer:
> Based on this...

---

## 8.8 Avoid pronoun ambiguity

Use explicit nouns when needed.

---

# ✦ 9. Terminology Discipline

## 9.1 One concept = one term

Do not alternate between similar words unnecessarily.

---

## 9.2 Use VIS vocabulary

- overview-to-detail  
- coordinated views  
- interactive exploration  
- steering  

---

## 9.3 Separate task and feature

- task: compare nodes  
- feature: comparison view  

---

# ✦ 10. Writing Style (Taste)

This is where VIS writing differs strongly from other fields.

## 10.1 Core style

> Plain, direct, and precise.

Not:
- fancy  
- dramatic  
- rhetorical  

---

## 10.2 Fancy vs VIS examples

### Problem

❌  
> unprecedented complexity  

✅  
> analysts struggle to understand behavior  

---

### Contribution

❌  
> highly effective framework  

✅  
> exposes intermediate states and enables intervention  

---

### System

❌  
> intuitive multi-faceted interface  

✅  
> supports overview, comparison, and inspection  

---

### Interaction

❌  
> seamlessly navigate  

✅  
> select, compare, inspect  

---

## 10.3 What “plain” means

- concrete over abstract  
- verbs over adjectives  
- actions over claims  
- mild tone over strong claims  

---

## 10.4 Style tests

Test 1: simplify words  
Test 2: describe user action  
Test 3: visualize the sentence  
Test 4: remove marketing tone  

---

## 10.5 Example rewrite

❌  
> intuitive and effective framework enabling insights  

✅  
> shows how solutions evolve and how performance changes  

---

# ✦ 11. Anti-Patterns

- technology-first writing  
- UI inventory description  
- vague claims  
- mixed abstraction  
- evaluation without results  

---

# ✦ 12. Final Mental Model

At sentence level:
> Does this make the value clearer?

At paragraph level:
> Does this advance the argument?

At section level:
> Does this help the reviewer believe the paper?

---

# ✦ One-Line Summary

> **VIS writing = clear task-driven structure + precise capability expression + plain, concrete language with zero fluff.**