---
name: zooming
description: Zoom through complex concepts top-down, one cognitive level at a time. Use when the user wants to understand a concept, paper, framework, code architecture, or system design step by step or top-down, or when a complex unfamiliar topic needs a mental model before details. Prefer a direct answer for simple definitions and procedure-only how-tos.
---

# Zooming

Build the learner's mental model from whole to parts to mechanism to detail. Treat the topic as a goal-specific concept tree, then reveal only the part the learner can use now.

The tree is navigation, not a syllabus. Teach toward the learner's question, not toward encyclopedic completeness.

## 1. Zoom out

Infer the learner's goal and already-known knowledge from the conversation. Start teaching rather than interviewing them; ask about background only when an unknown prerequisite would materially change the route and cannot be inferred.

For a specific paper, project, framework, or implementation, ground factual claims in the provided or available source material before building the explanation. Keep source facts distinct from explanatory inference.

Build a shallow concept tree:

- Start with purpose and the simplest useful whole-system mental model.
- Identify roughly 3–6 goal-relevant top-level parts.
- Order prerequisites before the concepts that depend on them.
- Prune branches the learner already knows or does not need for their goal.
- Plan the skeleton; grow deeper branches lazily as they become relevant.

Show the learner the short mental model and top-level map, then begin the first teaching frontier. Do not expose the full deep tree.

The **teaching frontier** is the set of goal-relevant nodes whose prerequisites are settled and which can therefore be explained without guessing about unopened dependencies.

This step is complete when a shallow route to the learner's goal exists and the first frontier can be taught without unresolved prerequisites.

## 2. Zoom in one level

Teach one small concept block from the current frontier. A block may contain a few tightly coupled sibling nodes, but it stays at one cognitive depth. Widen the frontier when useful; do not silently descend through multiple layers.

A node has enough explanation when the learner can place its role and minimum necessary mechanism correctly inside the parent mental model without requiring any unopened child node.

Use **just enough prerequisite**: define a newly required term only deeply enough to support the current node. If the learner needs more, that term can become a temporary zoom target.

Introduce the plain idea first when helpful, attach the real technical term early, and then use the real term consistently.

Choose the medium that minimizes cognitive load for this node:

- explain the real mechanism directly;
- use one concrete example, preferably a running example that can be reused;
- use a small diagram, code fragment, or formula when it communicates the mechanism more directly than prose;
- use analogy only when it genuinely compresses an abstraction, then reconnect it immediately to the real mechanism and its limits.

Include a caveat now only when omitting it would cause the current mental model to make a materially wrong prediction. Leave implementation details and non-blocking exceptions for later nodes.

At the end, point to the next direction if useful, but do not unfold it. Stop and give the learner a natural checkpoint for questions or continuation.

The node is now **presented**, not settled and not mastered.

## 3. Settle at the checkpoint

Treat the learner's next move as navigation:

- **Continue**: mark the presented block **settled** and recompute the frontier. Settled means "enough for the current learning goal to move on", not mastered.
- **Question about the current node**: resolve it while staying on the node, then checkpoint again.
- **Question about a child detail**: zoom into that child, resolve the requested depth, then return to the suspended path.
- **Side question**: open a temporary branch, resolve it, then return to the suspended path unless the learner explicitly makes it the new main goal.
- **Learner summary**: test the mental model. Preserve a useful approximation, but state where it becomes inaccurate. If the error would contaminate later understanding, reopen the earliest broken assumption, repair only that part, then return.
- **Granularity change**: obey natural requests such as "go deeper", "faster", "skip this", "zoom out", or "one shot". Reshape the remaining tree immediately.

When the learner repeatedly wants to move faster, combine more tightly coupled nodes at the current depth. **Speed up by widening the frontier, not by jumping deeper.**

After every settled block or repaired assumption, recompute the goal-specific tree and teaching frontier. The learner's questions can reveal new prerequisites, remove branches, or change the target.

## 4. Keep orientation lightweight

Do not repeat the full map every turn. Show orientation when it pays for itself:

- show the top-level map at the start;
- use a short breadcrumb during ordinary progression;
- show the relevant map again when entering a new top-level part or returning from a long branch.

The learner should know where they are without having to reread the syllabus on every turn.

## 5. Recompose

The session is complete when the learner's goal-relevant nodes and required dependencies are settled, no blocking question remains, or the learner says the explanation is sufficient.

Finish by recomposing the settled parts into one short, end-to-end mental model. This is not a second full tutorial: compress the path the learner just built so the parts become a coherent whole.
