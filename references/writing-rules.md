# Writing Rules

The style every file in a skill follows. These exist because a skill is read by a model on every run, and small habits in the writing turn into large habits in the results.

## Plain language

Write so someone new to the team could follow it on day one. Short sentences. Common words. If you have never heard a person say the word out loud, do not write it. Warm and plain beats clever.

## Directive voice

Say what to do. Never "you might consider," "it could be helpful to," or "try to." Those are read as optional and get skipped.

WRONG: "It may be worth checking whether the numbers are from the right month."
RIGHT: "Check that every number is from the month being reported. If one is not, stop and say which."

## Short blocks

Four or five sentences, then a break or a header. A wall of text gets skimmed, and the rule in the middle is the one that gets lost.

## Specific over vague

The words several, many, some, a few, and various do not appear. Say the number, or say the rule that produces the number. "Three to six lines," not "a few lines."

## Describe the shape, never a list of examples

Say what kind of thing goes in a place. Do not give a list of sample values. A model given a list of examples reproduces the examples, and every result comes out sounding the same.

WRONG: "Name the emotion, such as frustration, relief, pride, or fear."
RIGHT: "Name the one emotion the reader feels at this moment, in one word, chosen from what the source material actually shows."

## Real examples only

When an example earns its place, it comes from a real result, a real document, or a real run. If there is no real one, describe the criteria instead of making one up. An invented example teaches the model to invent.

## Show a failure by contrast

When a step has a known way to go wrong, write the WRONG version and the RIGHT version next to each other, labeled. A sentence describing the mistake is not enough. The pair is what the model matches against.

## Point at knowledge, do not paste it

If the rules live in a document, name the document and its path. A pasted copy drifts the moment the original changes, and nobody notices until the results are wrong.

## Say what to accomplish, name what is available

Name the tools, data connections, and documents the skill may use. Do not script the exact sequence of tool calls. The model picks the calls; the skill sets the goal and the allowed means.

## Numbers and facts

A skill that touches numbers says where each number comes from and what to do when it is missing. It never asks the model to calculate. It never lets the model estimate a number that was not provided. The rule is: name the source or say it is missing.

## Formatting

- Numbered lists for steps, because order matters.
- Bullets for rules, because order does not.
- A bold lead of three to six words on every step and rule, so the file can be scanned.
- No tables inside instruction text. They break when copied and are hard to read in a terminal.
- Headers only in any output skeleton. Never a bracketed "describe what goes here" line under a header. The prose describes; the skeleton shows the bones.
