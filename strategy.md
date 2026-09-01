# Skill Builder — Strategy

This document makes two decisions: whether the task is simple or complex, and which process file to run. It decides. It does not build anything. The building happens in `processes/`.

## What to load before deciding

- The person's description of the task, in their own words.
- A real finished result, if one exists. Ask for it.
- The existing skill, read in full, if the request is to improve one.

## First decision: one skill or more than one?

One job per skill. A request holds more than one job when:

- The steps split into groups that each produce a different finished thing.
- The person says "and then it should also."
- Two different people on a team would each run a different half.

When you see this, split it. Build the first skill. Name the others so they are not lost.

## Second decision: simple or complex?

The test. Picture three real past runs of this task. Did the person follow the same steps each time, with only the inputs changing? That is simple. Did they do it a different way depending on the situation, and could they say why they chose that way? That is complex.

Signs of a simple task:

- The person can list the steps without saying "it depends."
- The finished result has the same shape every time.
- A checklist would get a new teammate most of the way there.

Signs of a complex task:

- The person says "it depends" and can name what it depends on.
- They have names for the different approaches, even informal ones.
- The finished result changes shape based on the approach.
- Two experienced people would do it differently and both be right.

Things that look complex but are simple:

- A long checklist. Length is not complexity.
- A branch that only skips or adds a step when an input is missing. That is a step with a condition, not a second way of doing the job.
- A task with many inputs but one path through them.
- A task that is hard. Hard is not the same as many-pathed.

Things that look simple but are complex:

- The person describes one approach, then mentions "but sometimes I do it the other way."
- The output has two or three distinct formats they switch between.
- They describe the job as choosing before doing.

The tie-break: when in doubt, build simple. Add the strategy layer later, when the second real path shows up in practice. A simple skill that turns out to need a strategy doc is a twenty-minute upgrade. A complex skill built for a task with one path is a maze nobody needed.

## Third decision: which process?

- New task, one path: run `processes/build-simple-skill.md`.
- New task, many paths: run `processes/build-complex-skill.md`.
- A skill already exists and is not producing what the person wants: run `processes/improve-existing-skill.md`.
- The skill needs to run on its own on a schedule: build it first with one of the above, then follow `references/routines-loops-goals.md`.

## What complex is not

Complex means the approach varies. It does not mean the task is long, hard, important, or has a lot of inputs. A three-step task where the three steps change based on the situation is complex. A forty-step task where the forty steps never change is simple.
