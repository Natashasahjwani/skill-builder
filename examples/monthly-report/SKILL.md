---
name: monthly-report
description: Write the monthly performance report from last month's numbers, comparing each one to the prior month and to the goal, and saying what most likely moved it. Use when someone says write the monthly report, pull together last month's numbers, or asks how last month did against plan. Does not build dashboards or forecast next month; those are separate requests.
argument-hint: "[the month to report on, default last month]"
---

# Monthly Report

## Goal

Produce the monthly performance report: one page that says how each tracked number did against last month and against the goal, with the most likely reason for each move. The reader is someone who has ten minutes and needs to know what happened and what to do about it.

This skill writes the report. It does not decide the goals, build charts, or predict next month. If the numbers for the month are not in yet, it says so and stops.

## What it can use

- The numbers source: the file or connected data tool named in the project's instructions file as the source of truth for performance numbers. Every number in the report comes from here and nowhere else.
- The goals document: the file in the project that lists each tracked number and its monthly target.
- Last month's report, in the same folder this one will be saved to. Read it first so this report continues the story rather than restarting it.
- The month to report on, from the argument. If none is given, the most recent full month.

If the numbers source or the goals document cannot be found, stop and say which one is missing. Do not estimate.

## How this skill runs

1. **Read last month's report.** Note what it said to watch. Those items get a line in this report whether or not they moved.

2. **Pull every tracked number for the month.** One value per number, from the numbers source. Record where each one came from. If a number is missing for the month, write "not available" and carry on. Never fill a gap with a guess or an average.

3. **Compare each number two ways.** Against the prior month, and against the goal. Say whether it is up, down, or flat, and by how much, using the values as pulled. Do not compute anything the source does not already provide.

4. **Write one reason per number that moved.** The single most likely cause, drawn from what the project's documents say happened that month: a launch, a promotion, a change in spend, a seasonal pattern. If nothing in the documents explains it, say "no documented cause" rather than inventing one.

5. **Pick the two or three things to watch.** The numbers furthest from goal, or moving fastest in the wrong direction. These become next month's step one.

6. **Write the report** in the structure below, and save it to the reports folder with the month in the file name.

## Output structure

### Headline

Two sentences. How the month went overall, and the one thing that matters most.

### The numbers

One line per tracked number, in the order the goals document lists them. Each line holds: the name, this month's value, the change from last month, the gap to goal, and the reason in one clause. A number that was not available says so in place of its value.

### What to watch

Two or three items, each one line: the number, why it is on the list, and what would change the picture next month.

### Sources

Every file and data pull used, by name. The month the numbers cover. The date the report was written.

## Hard rules

- **Every number names its source.** A number that cannot be traced to the numbers source does not appear.
- **Never invent, estimate, or compute a number.** If the source does not have it, the report says "not available."
- **One reason per move, from the documents.** Not a list of possible reasons. Not a reason from general knowledge of the industry.
- **Same order every month.** The numbers section follows the goals document's order so reports can be read side by side.
- **Plain language.** No abbreviations that do not appear in the goals document.
- **Stop when a source is missing.** Do not write a partial report and present it as complete.

## When NOT to use this skill

- Someone wants to know one number right now. Look it up and answer.
- Someone wants a chart or a dashboard. That is a different job.
- Someone wants to change the goals. Edit the goals document; this skill only reads it.

$ARGUMENTS
