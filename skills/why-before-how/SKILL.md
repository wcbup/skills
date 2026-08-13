---
name: why-before-how
description: Reframe a consequential software or product solution into its motive and solution-agnostic minimum testable need before planning. Use when the user proposes a costly implementation, architecture, feature, or technical route without a clear desired outcome, or when ongoing work has become complex, slow, or non-convergent and its original need should be re-established. Skip routine small changes and execution of a settled spec.
---

# Why Before How

Trace upward from the proposed route to the **minimum testable root**: the one current need that is independent of an implementation yet concrete enough to decide whether a radically different solution works.

This skill finds the root; it does not design the route. Stop after the user confirms the root. The user may then invoke grilling, research, prototyping, specification, or any other downstream workflow.

## Interview discipline

Handle exactly **one cognitive decision per turn**. Give your recommended answer and why, then wait. A factual investigation is your work, not another decision for the user.

When the user adds information instead of answering, incorporate it and return to the still-open decision. Never treat several local agreements as approval of the assembled root.

When invoked automatically, briefly name the solution already embedded in the request, state why choosing it prematurely could be costly, and ask the first question below. If the user says the route is settled or asks you to proceed directly, exit the interview.

## 1. Recover the trigger

Start with the concrete event or recurring situation that existed before the proposed solution:

> Before you thought of this solution, what happened or what did you observe that made the current situation need to change?

Separate four things as they emerge: firsthand observation, interpretation of its cause, experienced or expected impact, and proposed solution. Ask about only one unresolved distinction at a time.

This step is complete when the observed situation and its impact are concrete enough that their load-bearing facts can be investigated.

## 2. Find the motive

Trace why the impact matters, one level at a time. Surface multiple genuine motives, then help the user classify them as primary, secondary, preference, or non-goal.

Different success conditions mean different efforts. Ask the user which single effort this run is rooting rather than combining practical relief, learning, creative satisfaction, and product ambition into one project.

A named method or artifact is normally a route. Test whether it is itself part of the motive:

> If a ready-made solution removed the practical problem completely, but you did not build or use this particular method yourself, would you be satisfied?

If yes, keep the method out of the root. If no, learning, making, or using that method may be the current effort's motive. If partly, split the efforts and root one now.

This step is complete when one current motive has priority and its success condition does not silently bundle a separate effort.

## 3. Verify the load-bearing facts

Verify only claims whose reversal would materially change the motive, scope, or a necessary condition. Prefer the environment, source code, official documentation, and other primary sources. Ask the user for decisions and firsthand experience, not facts you can investigate.

Keep these evidence states distinct:

- `[User confirmed]` — a preference, priority, or decision the user owns.
- `[User observed]` — firsthand experience not independently established.
- `[Verified: source]` — a fact checked against the named source.
- `[Critical unknown]` — unresolved; state what would change if it is false.

Leave facts about how to implement a candidate solution to the downstream design process. If a load-bearing fact cannot be verified, continue with an explicitly provisional root rather than laundering the assumption into fact.

This step is complete when every fact capable of overturning the root is either verified or marked as a critical unknown with its consequence.

## 4. Climb the abstraction ladder

Move upward one level at a time. At each level show only:

- the current need statement;
- the next more abstract statement;
- what new solution space the abstraction gains;
- what meaning, constraint, or testability it loses;
- your recommendation to stop or continue, with the reason.

Let the user choose the level. Recommend stopping at the first **minimum testable root** that:

- no longer prescribes a solution, except where the method itself is the confirmed motive;
- retains the real actor, situation, impact, and conditions needed for satisfaction;
- can accept a substantially different solution;
- would become less useful for deciding this work if abstracted again.

For each proposed condition, run the **missing test**, one condition per turn:

> If every other part of the current root were satisfied but this condition were absent, would you still consider the original problem solved?

Keep the condition when its absence leaves a real failure for the user. Otherwise treat it as a route or preference. Explain what simpler options the condition excludes and give your recommendation before asking the user.

For work already in progress, treat specs, ADRs, tickets, and code as historical evidence rather than authority over the user's current need. Surface divergence during the interview; leave artifact changes to a later workflow.

This step is complete when one root passes every missing test and the user chooses to stop at that abstraction level.

## 5. Confirm the root

Present exactly three short sections in the user's language:

```markdown
**Motive**
<why this matters; rank multiple motives only when they bear on the chosen effort>

**Core need**
<the single solution-agnostic minimum testable root, marked provisional when necessary>

**Basis**
<only load-bearing evidence, each carrying its evidence-state label>
```

Keep the original proposed solution in the conversation rather than adding a fourth section that anchors downstream work to it. Ask the user to confirm or correct the three sections as a whole. Revise until confirmed.

Return the confirmed result in the conversation. Create or update a document only when the user explicitly asks. Then stop.
