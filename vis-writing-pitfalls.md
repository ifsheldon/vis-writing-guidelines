# VIS Writing Pitfalls to Avoid

Clear wording is necessary, but a readable paper also needs a clear sequence of ideas.
A passage can contain accurate statements and still leave readers unsure why a concept matters, how a step works, or why the next paragraph follows.

Use this guide alongside [VIS Writing Style](vis-writing-style.md) and [VIS Writing Guide](vis-writing-guideline.md).
For preserving an existing manuscript's argument while polishing it, see [VIS Editing Pitfalls](vis-editing-pitfalls.md).
The nine main pitfalls below focus on explanatory logic and revision practice.
The examples illustrate writing decisions; claims about a particular system must still be checked against its sources.

## 1. Repairing sentences without checking the surrounding argument

**Pitfall:** A local edit makes one sentence clearer but creates repetition, a missing explanation, an ambiguous reference, or a premature conclusion elsewhere.

For example, moving the explanation of timing into an earlier paragraph may leave the next paragraph introducing timing again.
Moving a discussion of evaluation may also change which actor readers associate with “the reviewer.”

**Better approach:** Identify each paragraph's purpose before editing, then revise the connected passage.
After a substantive change, reread the preceding paragraph, the revised passage, and the following paragraph.
If the change moves a definition, example, conclusion, or handoff, also check the subsection's overall sequence.

Ask:

- What does this paragraph add that the previous one has not established?
- Did moving this idea leave a duplicate or an unexplained reference elsewhere?
- Does the next paragraph still follow from the revised ending?

The unit of revision should be large enough to repair the explanation.
A sentence-level request can require changes to neighboring sentences.
Avoid using a restatement of the previous paragraph's conclusion as the next paragraph's main point.
For example, after explaining what a distribution shows, advance to how analysts investigate the observations behind a selected region.
A brief backward reference can establish continuity while the paragraph develops the next question.

## 2. Naming components without explaining why they exist or how they work

**Pitfall:** The prose lists fields, modules, or responsibilities while leaving the method unexplained.
Readers learn the vocabulary but cannot describe what happens.

**Weak:**

> Each comparison specifies a region, a time window, an aggregation method, and a rationale.

This is a compact inventory.
It does not explain why a comparison needs those elements or how they are determined.

**Better:**

> Comparing regional trends requires observations from comparable periods. Analysts choose the geographic coverage and time window before aggregating the observations. We store these choices with each result so readers can inspect which observations it includes.

The explanation gives readers a reason for the fields before naming them.
The aggregation method and its rationale can then be introduced when the reader needs to understand how the selected observations become a result.

The opposite failure is equally common: replacing an inventory with a sentence so general that the mechanism disappears.

**Too general:**

> Analysts interpret the records; scripts organize their decisions consistently.

**More informative:**

> Analysts identify reports that describe the same event. Scripts group these reports by the assigned event identifier and order the resulting events by their recorded dates.

For each important concept, establish:

- **Need:** What problem or decision requires it?
- **Action:** Who determines it, and from what evidence?
- **Use:** What does the resulting decision enable next?

These are questions to answer, not a mandatory three-sentence template.
Include technical details when they explain the transformation or a consequential design choice.
Move exhaustive field lists to a table, schema, or supporting documentation when the main text does not need them.
Explain why a representation is needed through the analytical distinctions or decisions it supports.
Saying that the software needs a data structure does not explain why the chosen structure serves the research problem.

Make the connection between a representation and its benefit explicit:

> The system retains measurements from before and after filtering. Having both sets lets analysts identify which observations the filter removed.

The second sentence explains what retaining both sets enables.
When a design choice and its benefit are merely adjacent, state how the choice enables the comparison, inspection, or decision.

## 3. Using examples that repeat the claim instead of explaining it

**Pitfall:** An example appears before the reader knows its purpose, or replaces abstract nouns with domain terms while leaving the same reasoning gap.

**Weak:**

> Selection criteria must be specific. For example, a study needs to say exactly which sensor readings it includes.

The example says that specificity matters, but it does not show which condition could be lost or how that loss changes the selected data.

**Better:**

> A summary can retain one selection condition while omitting another that changes which observations qualify. Suppose a study uses readings from the last twelve months and excludes readings from uncalibrated sensors. A summary stating only “we used readings from the last twelve months” retains the time window and omits the calibration condition. Readers need both conditions to reproduce the data selection.

This example identifies the original criteria, a plausible summary, the missing condition, and the consequence for reproduction.
It explains what the preceding claim means in practice.
Introduce the principle that the example will demonstrate, then show the concrete distinction and explain why it matters.

Ask:

- What distinction does this example make visible?
- Which part of the preceding claim does it justify?
- Can the reader explain why the distinction changes the result or decision?

An example should contribute something the general statement alone leaves unclear.
When several concepts build on each other, continue one example across them if doing so reduces the reader's need to reconstruct context.

## 4. Adding connecting words where the logical relationship is missing

**Pitfall:** Words such as “also,” “then,” and “therefore” make sentences sound connected without explaining why one idea follows another.
A new component or actor appears without a reason for being introduced.

**Weak:**

> Analysts record a rationale for each category assignment. An independent reviewer then checks the assignments.

The sequence is visible, but the purpose of the review and the role of the rationale remain implicit.

**Better:**

> Analysts record why each interview passage was assigned to a category, making their interpretation reviewable. Assignment errors could change which themes appear common across participants. An independent reviewer therefore checks the assignments and rationales against the original passages.

The transition now follows from a relationship: interpretive decisions can affect later judgments, so those decisions need review.

Useful connections include:

- A limitation motivates the next method.
- A decision creates a need for justification or checking.
- One step produces the input needed by the next.
- An example exposes a distinction that the next paragraph explains.
- A condition determines when the previous observation supports a particular conclusion.
- A representation enables the comparison or decision described next.
- An inspection of what is present leads to an examination of how it was produced.

Before adding a transition word, state the relationship in plain language.
Choose a connector that matches that relationship, such as qualification, consequence, comparison, or change in scope.
An observation followed by the conditions for interpreting it is not automatically an opposing claim that needs “however.”
If that relationship is already clear, a short transition may be enough.
Do not add a lengthy justification for an obvious connection.

## 5. Ordering information without respecting what the reader needs first

**Pitfall:** The explanation moves between a concept, its construction, its use, and its consequences without making the changes in scope clear.
It may present a conclusion before establishing its basis, then return to an unexplained assumption or unfinished decision.

In a method description, this can look like:

> Define part of a grouping method → describe evaluation → return to another grouping decision → review the grouping choices.

The reader must reconstruct which decisions belong to which activity and whether the current explanation is finished.
A clearer sequence for that passage is:

> Explain the grouping problem → develop the grouping criteria → justify and review the choices → explain what evaluation examines.

The general lesson extends beyond pipelines.
A design rationale needs the relevant user need first; a result interpretation needs the relevant evidence; an unfamiliar distinction needs enough context to be understood.

**Better approach:** Order the passage around conceptual dependencies and make changes in scope explicit.
Establish the relevant domain process before introducing a distinction that depends on it.
Define the objects or groups before introducing mappings or comparisons between them.
A preview can help readers understand the purpose of a section, but it should remain recognizable as a preview.
It should not sound like a completed explanation while essential decisions remain unexplained.

Ask:

- Have I established what the next sentence depends on?
- Am I developing the current idea, previewing a later one, or changing the subject?
- Will the reader recognize that change?
- Is it clear who is acting and what has already been defined?

There is no universal requirement to follow implementation order.
Choose the order that makes the explanation easiest to follow.

## 6. Proposing a structural repair but implementing only a wording change

**Pitfall:** The revision plan correctly identifies a missing explanation or broken sequence, but the actual edit changes only a phrase.
The final passage therefore retains the problem that the plan promised to solve.

For example, a plan to explain why category assignment needs interpretation is not fulfilled by adding “keyword matching is insufficient.”
The text must show the distinction that a keyword match cannot resolve.
Likewise, promising to motivate independent review is not fulfilled by adding “therefore” before the reviewer appears.

**Better approach:** Translate the proposed repair into questions that can be answered by reading the final prose.

- If the plan promised a reason, where does the text explain it?
- If it promised an example, what does that example establish?
- If it promised a transition, what relationship connects the paragraphs?
- If it promised a clearer sequence, does the passage still return to unfinished earlier work?

Read the edited passage without relying on the explanation given in a review comment or conversation.
Readers of the paper will only have the paper.
When a manuscript includes paragraph outlines or source comments, update the corresponding entry when the paragraph's core message or role changes.
An outline should state what the paragraph establishes, not merely list the terms it contains.
Preserve other outline entries while making the scoped revision.

A clean diff, successful compilation, and correct formatting establish mechanical correctness.
They do not establish that the explanation works.
Review the prose itself after those checks.

## 7. Assuming the reader shares the authors' conversational context

**Pitfall:** An explanation works in discussion because the participants already know the domain, actors, and preceding decisions, but the paper copies the compressed wording without supplying that context.
Replacing jargon with generic statements can leave the same gap.

**Too generic:**

> A filter receives data and produces a subset.

**More informative:**

> The filter selects observations whose recorded timestamps fall within the interval chosen by the analyst.

The revision identifies the actor, the information examined, the selection criterion, and the result.
It gives an unfamiliar reader the context needed to understand the next design choice.

**Better approach:** Use simplified feedback to recover the intended reasoning, then write prose that supplies its missing premises.
Retain the relevant domain actors, information, and processes while removing jargon and repetition.
Judge the explanation from the reader's starting knowledge, not from the authors' ability to recognize their own shorthand.

## 8. Packing several distinctions into one comparison

**Pitfall:** A sentence combines several actors, locations, time points, or exceptions in a nested contrast.
Each clause may be correct while the combined sentence leaves the reader unsure what is being compared.

**Dense:**

> The interface distinguishes a measurement missing from the source dataset from one present in that dataset but excluded from the displayed subset.

**Clearer when explaining an inspection capability:**

> Analysts can check whether a measurement appears in the source dataset and whether the displayed subset includes it.

The revision names the two inspection questions directly.
If the absence categories are themselves the claim, explain each case separately and state why the distinction matters.

**Better approach:** Give each sentence one main explanatory job and identify the relevant actors or locations explicitly.
Separate a method's benefit from a qualification about interpreting the result.
Use a parallel list when readers need to compare several cases.
Do not delete a necessary condition merely to shorten a sentence.

## 9. Replacing explanation with defensive qualifications

**Pitfall:** The prose anticipates an objection without explaining a method, a condition, or a consequence that the reader currently needs.
Phrases such as “respects the limits of the evidence” can sound careful while leaving the underlying action unspecified.

**Vague qualification:**

> The displayed links rely on the available evidence and do not assume that similar observations have the same source.

**Method explanation:**

> We link each plotted observation to its source row using the dataset identifier and row index.

The revision explains how the relationship is established.
As with every example in this guide, the described method must match the work being reported.

Choose the revision according to what the qualification contributes:

- Remove a qualification that only repeats a distinction already established.
- Explain a necessary condition where it changes the interpretation or decision.
- Incorporate an evidence requirement into the description of the method that uses it.

For example, missing observation durations affect whether event rates can be computed.
The useful explanation is the consequence: “We report event counts and omit rates for periods whose observation durations are unavailable.”
Retain uncertainty, limits on causal claims, and other conditions that affect what the evidence supports.
The aim is to explain those conditions precisely, not to eliminate qualifying language.

## Additional sentence-level traps

| Trap | Why it fails | Revision principle |
|---|---|---|
| Technical inventories before the core message | Readers see implementation details before understanding their purpose. | State the transformation or analytical value first, then retain the details that explain it. |
| Generic nouns such as “dataset,” “sample,” or “the analyst” | The noun may refer to several collections, units of analysis, or actors. | Name the specific collection, unit, or actor when the reference could be ambiguous. |
| Switching between related terms without defining their relationship | Readers may treat raw observations and aggregate values as interchangeable. | Use one term per concept and explain how distinct concepts relate. |
| Statements that merely promise correctness | Saying that meaning is preserved or results are checked may add no understanding. | Explain the consequential decision or check when needed; otherwise omit the generic assurance. |
| Compression that removes reasons and connections | A short sentence can require more effort when readers must infer its logic. | Cut repetition and decoration while retaining the explanation needed to follow the method. |

These checks do not justify deleting necessary qualifications or overstating evidence.
State consequential limitations clearly where they affect what the reader can conclude.

## A revision pass

1. **State the core message.** Write one plain sentence describing what the passage should teach the reader and what prior knowledge it assumes.
2. **Map the paragraph roles.** Identify what each paragraph adds, what the next paragraph depends on, and any repeated conclusions.
3. **Check purpose, mechanism, and benefit.** For each important new concept, explain why it is needed, enough of how it works, and what it enables.
4. **Check examples and transitions.** Introduce the example's purpose, make it demonstrate a specific distinction, and state the actual relationship between paragraphs.
5. **Revise the connected passage.** Recheck neighboring paragraphs, qualifications, and the subsection after moving or expanding an idea, and update any affected outline entries.
6. **Read the actual result.** Confirm that the promised explanation is present, actors and references are clear, and the prose preserves the evidence and its limits.

The final check is whether a reader unfamiliar with the system can explain what happens, why it happens, and how the ideas connect.

## Source of the lessons

Adapted from the writing review and lessons learned in [Fix issue 4 memory definition](thread://01a072b2-aaed-71a1-ae18-a3ef02b63c16?hostId=local).
The lesson about premature handoffs is generalized here to conceptual dependencies and explicit changes in scope, rather than treated as a rule about pipeline order.
Updated on 2026-09-09 with recurring lessons about assumed reader context, explicit benefits, paragraph progression, dense comparisons, and qualifications.
The examples are generalized for use across papers and illustrate writing decisions rather than prescribing a particular research method.
