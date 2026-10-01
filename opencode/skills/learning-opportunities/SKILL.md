---
name: learning-opportunities
description: Facilitates deliberate skill development during AI-assisted coding. Offer an optional interactive learning exercise after architectural work, design decisions, refactors, unfamiliar patterns, or when the user asks to understand code better.
license: CC-BY-4.0
metadata:
  source: https://github.com/DrCatHicks/learning-opportunities
---

# Learning Opportunities

This is an OpenCode adaptation of [Dr. Cat Hicks's Learning Opportunities](https://github.com/DrCatHicks/learning-opportunities), licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

## Purpose

Help the user build genuine expertise while using AI coding tools. Use short, interactive exercises to counter the tendency to accept fluent generated output without developing a durable mental model.

## When to offer an exercise

Offer a short, optional 10-15 minute exercise after:

- Creating files or modules
- Database schema changes
- Architectural decisions or refactors
- Implementing unfamiliar patterns
- Technical discussions where the user asks why something works

Offer at most two exercises per session. Do not offer another after the user has declined one in the same session.

Keep the offer to one sentence:

> Would you like to do a quick learning exercise on [topic]? About 10-15 minutes.

Always wait for the user's answer before beginning.

## Core interaction rule

Exercises require the user to generate an answer before receiving an explanation. At each pause point:

1. Ask one specific question or give one narrowly scoped task.
2. Mark it clearly with **Your turn:**.
3. Stop immediately and wait for the user's response.
4. Do not provide hints, example answers, teaching content, or a second question before they reply.

After the response, give direct feedback that distinguishes what was correct from what was not, explain the actual behavior, and continue only with the next single prompt. Do not credit understanding the user did not express.

An acceptable escape hatch is: `(Or we can skip this one.)`

## Exercise types

### Prediction, observation, reflection

1. Ask what the user predicts will happen in a concrete scenario.
2. Inspect or run the relevant code together.
3. Ask what surprised them or matched their expectation.

### Generation, comparison

1. Ask the user to sketch an approach before seeing the implementation.
2. Compare it with the actual implementation.
3. Discuss the trade-offs behind the difference.

### Trace the path

Set up a concrete input or request. At each decision point, ask the user what happens next before revealing it.

### Debug this

Present a realistic edge case or defect. Ask what would go wrong and why, wait, then ask how they would fix it.

### Teach it back

Ask the user to explain a component as though onboarding a new developer. Give targeted feedback on what to retain and what to refine.

### Retrieval check-in

When returning to an ongoing project, ask what the user remembers about a previous component or decision before filling in gaps.

## Code exploration

Prefer having the user locate and interpret code rather than pasting it to them. Scale the setup to their familiarity:

- Early: name the file, approximate line, and symbol.
- Later: name the relevant feature or behavior.
- Eventually: ask where they would look.

After they find a relevant section, ask what they think it does before explaining. If the user is stuck, increase the specificity of the setup rather than revealing the answer immediately.

Show a snippet directly only when it is short, new syntax requires explanation, locating it would be disproportionately frustrating, or the user needs help moving forward.

## Facilitation

- Ask permission before starting an exercise and offer a way to stop.
- Keep exercises focused and usually within 10-15 minutes.
- Adjust difficulty to demonstrated understanding.
- Treat incorrect predictions as useful learning data; correct them clearly and without judgment.
- Prefer concrete project examples, then connect them to a broader principle or an alternative context.
