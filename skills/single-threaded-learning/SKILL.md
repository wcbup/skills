---
name: single-threaded-learning
description: Single-threaded concept learning. Use when the user explicitly asks to understand a complex topic step by step or says an explanation is overwhelming.
---

# Single-threaded Learning

Build understanding without multiplying the learner's unresolved questions. Keep one active learning thread, open at most two loops, and return from side questions without losing the suspended route.

## 1. Start one thread

Infer the learner's goal and relevant existing knowledge from the conversation. Start teaching immediately unless a missing prerequisite would materially change the route.

For a new topic, reset to the default pace. Give one self-contained sentence that locates the topic as a whole, then teach the first useful understanding. Keep the larger route internal and choose the next step by minimum likely confusion rather than by a fixed top-down or bottom-up order.

The active **thread** records:

- the learner's goal;
- the exact question currently being resolved;
- where that question is paused;
- the current pace.

## 2. Add one understanding

Each turn establishes one core understanding. Use as much explanation as it needs. Principle, example, diagram, or code may appear together when they all clarify that same understanding.

An **open loop** is something the learner must still understand for the current explanation to make sense: an unexplained term, an unclear component role, a missing causal step, or an opened branch or exception. Immediately settled terms, optional example details, and simple previews are not open loops.

Before sending, predict the questions the explanation is most likely to create. Keep agent-created open loops to at most two. If there are more, narrow the turn, explain an essential dependency first, or replace technical labels with sufficient plain language. A conceptual node may span multiple turns.

End at the first point where the current understanding can support the next step. At the main thread, ask:

> What questions do you have here, or shall we continue?

Repeated requests to continue settle the current understanding but keep the default pace. Increase pace only when the learner explicitly asks.

## 3. Follow questions locally

A question about the current explanation pauses the thread at its exact position and opens a side thread. Store each paused position on a **branch stack**. A question inside a side thread adds another position to the stack.

Stay with the active side thread until its question is settled. At its checkpoint, ask:

> Do you have any more questions here, or shall we return to the previous question?

Interpret navigation naturally:

- **Continue** — continue the active thread;
- **Got it / I understand** — settle the active side thread and return one level; on the main thread, settle the current understanding and advance one step;
- **Go back / Return one level** — return one level;
- **Return to the main thread** — return directly to the original main thread.

Whenever returning, give one short breadcrumb containing:

1. where the previous thread paused;
2. what the side thread settled;
3. what is being resumed now.

If the learner asks several independent questions at once, queue them in order and answer one at a time. Follow-ups on the active question take priority over queued questions. User-created queued questions do not consume the agent-created open-loop budget.

## 4. Control pace

Explicit requests such as “go faster” widen subsequent turns while preserving one active thread and the open-loop budget. The faster pace persists through side threads and returns. A new topic resets to the default pace.

Requests such as “slow down” or “one thing at a time” restore the default pace immediately.

## 5. Finish the thread

Finish when the learner's goal is settled or the learner says the explanation is sufficient. Recompose only the main-thread conclusion in one short summary. Bring in a side-thread result only when the conclusion depends on it.
