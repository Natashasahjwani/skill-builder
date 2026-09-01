# Writing the Description

The description line in the frontmatter is the only part of a skill that is read before the skill is chosen. It decides whether the skill wakes up when it should and stays quiet when it should not. It is worth more care than any other line in the folder.

## The shape

Three parts, in one paragraph, in this order:

1. **What it does.** First sentence. Verb first. Names the finished thing. Written as if describing the skill to a teammate, not as a command to Claude.
2. **When to use it.** Starts with "Use when." Lists the situations and the words people actually say when they want this. Write the phrases the way they would be typed, in plain words.
3. **What it does not do, and where that goes.** One sentence. The nearest thing this skill could be confused with, and the skill or action that handles it instead.

Three to five sentences total. Long enough to be specific, short enough to read in one breath.

## The test

Cover everything but the description. Read it cold. Ask two questions:

- If someone typed a request that this skill should handle, is there a phrase here they would have used?
- If someone typed a request that a neighboring skill should handle, is there a line here that sends it away?

If either answer is no, the description is not done.

## Contrast

WRONG: "A skill for reports."

That does not say what kind of report, when to reach for it, or what it does not cover. It will fire on every mention of the word report and never on the phrases people actually use.

RIGHT: "Write the monthly performance report from last month's numbers, comparing each one to the prior month and to the goal. Use when someone says write the monthly report, pull together last month's numbers, or asks how last month did against plan. Does not build dashboards or forecast next month; those are separate requests."

The right version names the finished thing, the trigger phrases, and the edge.

## Argument hint

If the skill takes something typed after its name, add `argument-hint` in the frontmatter. Square brackets, plain words, say what to type. "[the month to report on, default last month]". If the skill takes nothing, leave the field out.

## What never to do

- Write the description as instructions to Claude. It describes the skill; it does not run it.
- Use a word that only means something inside your team without explaining it.
- List every possible situation. Five phrases people actually say beat twenty they might.
- Leave out the edge. A description with no "does not" line gets picked for its neighbors' jobs.
