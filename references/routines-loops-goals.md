# Routines, Loops, and Goals

A skill teaches the process. These three patterns keep it moving without someone asking each time. Build the skill first. Then pick the pattern that fits.

## The three patterns

**Routine.** A known process runs on a known cadence. Trigger, then process, then result. Every morning at eight, run the skill, the same job gets done.

**Loop.** Keep checking for change. Check, decide, act, wait, check again. Every hour, look for new ads and flag anything that moved.

**Goal.** Keep working until the outcome is real. Define done, work, verify, complete. If it fails, adjust and continue. Find why cost per sale rose and keep going until the cause is proven.

Routines repeat. Loops monitor. Goals finish.

## Which one

Choose based on what is fixed and what can stay flexible.

- The same job should run automatically, and the steps and cadence are known: **routine**. Be clear about the steps, the cadence, and the expected output.
- Something needs repeated checking or retrying, and the action depends on what is found: **loop**. Be clear about what to check, how often, and what action each finding triggers.
- The outcome is known but the best path is not: **goal**. Be clear about the definition of done and the guardrails. A goal can have an uncertain path. It can never have an unclear finish line.

## What changes in the skill

A skill that runs on its own has no one watching. Three things must be true of it that are optional in a hands-on skill:

- **It leaves its result somewhere named.** A file, a message, a page. The skill says exactly where, and the routine's result is that thing existing.
- **It ends with a receipt.** A short block at the end of the output saying what ran, what it used, and what it produced. When something goes wrong at three in the morning, this is how you find out.
- **It knows what to do when an input is missing.** Stop and say so, or skip and say so. Never guess and continue. A hands-on skill can ask; a scheduled one cannot.

If the skill does not have these, add them before scheduling it.

## Wiring it up

The skill is the process. The schedule is registered separately, in whatever tool runs the skill, and it does not travel with the skill folder. When someone copies the folder to a new machine, they re-register the schedule there.

The schedule needs one line: the prompt it will run. Write that line as the skill invocation with its inputs fixed. "Run the weekly report skill for last week." Not a paragraph. The skill carries the rest.

In Claude Code, a routine is set up with the schedule command, and a loop with the loop command. The pattern is the same in any tool that can run a prompt on a timer.
