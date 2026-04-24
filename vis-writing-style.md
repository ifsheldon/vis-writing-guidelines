# 1. The Core Taste of VIS Writing

A good mental model:

> **Write like you are explaining the system to a careful colleague, not impressing a reviewer.**

That leads to three consistent traits:

* **short, direct sentences**
* **ordinary words with precise meaning**
* **claims that sound slightly conservative, but are clearly supported**

Not:

* dramatic
* metaphorical
* overly abstract
* rhetorically embellished

---

# 2. Fancy vs VIS Style (Concrete Examples)

## 2.1 Problem Statements

❌ Fancy / inflated

> The rapid proliferation of LLM-driven systems has introduced unprecedented complexity, rendering traditional analytical paradigms increasingly inadequate.

✅ VIS style

> As LLM-driven systems become more complex, analysts struggle to understand and control their behavior.

Why this works:

* “rapid proliferation,” “unprecedented,” “paradigms” → all removed
* replaced with **what actually happens to users**

---

## 2.2 Challenge Description

❌ Fancy

> This opacity severely impedes users’ capacity to derive actionable insights from intermediate computational states.

✅ VIS style

> Users cannot inspect intermediate states or understand how results are produced.

Notice:

* “impedes capacity to derive actionable insights” → replaced by **two concrete actions: inspect, understand**

---

## 2.3 Contribution Statements

❌ Fancy

> We introduce a novel and highly effective framework that significantly enhances interpretability and user agency.

✅ VIS style

> We introduce a framework that exposes intermediate states and allows users to intervene during the process.

Key difference:

* replaces vague praise (“novel,” “effective”) with **what it actually does**

---

## 2.4 System Description

❌ Fancy

> The interface features an intuitively designed, multi-faceted visualization paradigm that facilitates comprehensive analytical exploration.

✅ VIS style

> The interface supports overview, comparison, and detailed inspection through coordinated views.

Even better (more VIS-like):

> The interface supports three tasks: overview, comparison, and detailed inspection.

---

## 2.5 View Description

❌ Fancy

> This visualization provides an insightful depiction of structural relationships and performance dynamics.

✅ VIS style

> This view shows how nodes are connected and how their performance changes over time.

This is very typical VIS language:

* “shows how X relates to Y”
* “reveals changes over time”
* “highlights differences”

---

## 2.6 Interaction Description

❌ Fancy

> Users are empowered to seamlessly navigate complex analytical pathways through interactive mechanisms.

✅ VIS style

> Users can select nodes, compare them, and inspect their details.

Simple verbs win:

* select
* compare
* inspect
* filter
* adjust

---

## 2.7 Evaluation Claims

❌ Fancy

> Our results demonstrate the system’s superior effectiveness and usability.

✅ VIS style

> Participants identified patterns more quickly and compared alternatives with less effort.

Even stronger:

> Participants used the overview to locate suspicious nodes and then used the detail view to verify their hypotheses.

This sounds almost like storytelling, but very grounded.

---

## 2.8 Transitions

❌ Fancy

> Building upon these aforementioned considerations, we subsequently elaborate on...

✅ VIS style

> Based on these requirements, we design the system as follows.

Or even simpler:

> Based on these requirements, we design the system.

VIS writing prefers **quiet transitions**, not rhetorical ones.

---

# 3. What “Plain” Actually Means (Subtle but Important)

Plain does **not** mean simplistic or shallow.

It means:

### 3.1 Concrete over abstract (with one exception)

In tutorial or background sections where readers are building up new concepts, explicit backward references (e.g., "the aforementioned probabilistic impurity") can help readers recall context. The "simplify" rule yields to clarity when the reader's working memory is loaded with unfamiliar concepts.

**Elsewhere**, prefer simple references:

Avoid:

* mechanism
* paradigm
* process
* framework (when overused)

Prefer:

* states
* nodes
* results
* steps
* views

---

### 3.2 Verbs over decorations

Avoid:

> provides an intuitive and flexible way to...

Prefer:

> shows...
> reveals...
> lets users...

---

### 3.3 Specific actions over general capability

Avoid:

> supports analysis

Prefer:

> supports comparing nodes across generations
> supports tracing how results change over time

---

### 3.4 Mild tone over strong claims

VIS papers rarely say:

* groundbreaking
* transformative
* highly novel

Instead:

* we introduce
* we support
* we enable
* results show

There is a quiet confidence.

---

# 4. A “Taste Test” You Can Apply

When proofreading, try this:

### Test 1: Can I replace this with a simpler word?

* “utilize” → “use”
* “facilitate” → sometimes “help,” but better: “enable X”
* “demonstrate” → often “show”
* “cross-tabulate” → “examine together” or “compare”
* “aforementioned” → “these” or “the above”
* “paradigm” → “approach” or “model”

**Audience check:** Many VIS reviewers are not native English speakers. A word that feels natural to a native speaker may force a non-native reader to pause or guess from context. When choosing between a precise but uncommon word and a plain but clear one, prefer the plain one. The figure or formula can carry the precision; the sentence should carry the meaning.

Rule of thumb: if a word would not appear in a typical spoken explanation between colleagues, replace it.

**Avoid idioms and figurative language.** Phrases like "follows suit," "lowers the barrier," and "turning strangeness into a source of wonder" may feel natural to native speakers but force non-native readers to decode figurative meaning. Replace with literal equivalents:

* "follows suit" → "also addresses this level"
* "lowers the barrier" → "makes X accessible to Y"
* "a source of wonder" → "tangible through interactive feedback"

---

### Test 2: Can I say exactly what the user does?

If sentence contains:

> improves usability

Rewrite:

> lets users compare X and Y directly

---

### Test 3: Can I visualize what this sentence describes?

If not, it’s too abstract.

Bad:

> improves interpretability

Better:

> shows how results change across iterations

---

### Test 4: Does this sound like marketing?

If yes, remove:

* effective
* powerful
* intuitive
* flexible

Replace with mechanism.

---

### Test 5: Am I promising insight or delivering it?

Meta-claims like "understanding X can reveal Y" or "analyzing X is useful" tell the reader the analysis will be valuable without showing how. Replace with a concrete taste of the finding.

❌ Meta-claim (promises insight):

> Understanding this landscape can reveal where coverage is thin.

✅ Concrete hint (delivers a taste):

> ...yet existing work concentrates on only a few.

❌ Meta-claim:

> Existing techniques vary in maturity and can face different technical challenges at each level.

✅ Concrete bookends:

> Existing techniques face qualitatively different challenges at each level, from scalability limits for quantum states to the lack of visualization support for complete algorithms.

The reader gets immediate value and is motivated to read on for the full picture.

**Extension to transitions and roadmaps:** Even structural sentences (transitions, roadmaps, summaries) should name what's coming rather than just promise that something is coming. Transitions are valuable -- don't cut them -- but make them concrete.

❌ Vague roadmap:

> Despite this relative maturity, a fundamental visualization challenge and an underexplored opportunity remain.

✅ Concrete preview:

> Despite this relative maturity, two issues stand out: the scalability of state visualization and the secondary treatment of phase.

---

### Test 6: Do adjacent sentences say the same thing?

If two consecutive sentences make the same point with different words, merge them. This is surprisingly common in introductions and related work sections where authors hedge the same claim twice.

❌ Redundant:

> Despite its growing importance, existing VIS4QC research has not been systematically surveyed. The existing surveys remain sparse, and the research landscape has not been clearly outlined.

✅ Merged:

> Despite this growing importance, no systematic survey of VIS4QC exists to map the research landscape or guide future work.

---

### Test 6: Am I framing by purpose or by user group?

When introducing categories, lead with **what the visualization does** (its purpose), not **who uses it**. User groups overlap; purposes are distinct. Framing by user group can accidentally imply mutual exclusivity.

❌ User-group framing (implies disjoint groups):

> For newcomers, visualizations support learning. For experienced users, visualizations improve productivity.

✅ Purpose-first framing (allows overlap):

> Visualizations for *learning and interpretation* teach QC concepts or provide novel visual representations. Visualizations for *productivity and utility* help users accomplish tasks more efficiently.

---

### Test 7: Can I use a colon to signal structure?

When a sentence packs two or three parallel items, a colon after the setup phrase tells the reader "here come the parts." This often avoids the need to split into choppy sentences.

❌ Overstuffed:

> Visualizations support learning by teaching new concepts in educational settings and interpretation by providing novel representations that offer fresh perspectives.

✅ Colon-signaled:

> Visualizations serve two goals: *learning*, by teaching new concepts in educational settings, and *interpretation*, by providing novel representations that offer fresh perspectives.

---

### Test 9: Does this sentence pivot?

If a sentence sets up one idea and then redirects (with "but," "yet," "although," "despite," "obscuring"), consider splitting at the pivot. The pivot is where the reader's mental model shifts. A period at that point gives them room to absorb the first idea before processing the turn.

❌ One sentence, two jobs:

> All 2^N amplitudes may change, obscuring the fact that the transformation derives from a simple local mechanism.

✅ Split at the pivot:

> All 2^N amplitudes may change. Yet the transformation is local.

---

# 5. A Short Before → After Paragraph Example

### ❌ Fancy version

> We present a novel visual analytics framework that provides an intuitive and effective mechanism for understanding complex evolutionary processes. The system facilitates comprehensive exploration through a multi-view interface, enabling users to derive actionable insights and make informed decisions.

### ✅ VIS-style version

> We present a visual analytics system for understanding evolutionary processes. The system exposes how candidate solutions change over time and how these changes affect performance. It provides coordinated views for overview, comparison, and detailed inspection, allowing users to identify promising candidates and analyze their evolution.

What changed:

* removed all vague praise
* added **what is shown**
* added **what users can do**

---

# 6. The Deeper Principle Behind This Taste

The preference for plain language in VIS comes from the nature of the field:

* VIS is about **making things visible**
* writing should follow the same philosophy

So:

> If your sentence hides meaning, it contradicts your research goal.

That’s why the best VIS papers often feel:

* calm
* direct
* slightly understated
* but very clear

---

# 7. Terminology Discipline

* **One concept = one term, throughout the paper.** If you call them "works" in the methodology, do not switch to "items" or "studies" elsewhere when referring to the same collection. Define the term once and use it consistently.
* **Avoid overloading common words.** If "community" means "research community" in one paragraph and "QC user community" in the next, readers will conflate them. Use distinct nouns: "research community," "user base," "practitioners."

---

# 8. One-Line Style Rule

> **If a sentence sounds impressive, simplify it. If it sounds obvious but precise, keep it.**

