---
name: make-dinner
description: Plan and run dinner for a group from what is in the kitchen and how much time there is, choosing the style of meal that fits the night and then walking through the shopping, timing, and cooking. Use when someone says make dinner, plan supper for friends, what should I cook tonight, or has people coming and a deadline. Does not plan a week of meals or a party menu; those are separate requests.
argument-hint: "[who is coming, any diets, and how long you have]"
---

# Make Dinner

## Goal

Get a good dinner on the table for the people coming, inside the time available, using what is already in the kitchen as far as possible. The finished result is a plan the cook can follow start to finish: what to buy if anything, what to start when, and what to do in what order.

This skill plans and runs one dinner. It does not plan menus for a week, and it does not handle a party with more people than one cook can serve at a table.

## What it can use

- The argument: who is coming, any diets or dislikes, and how much time there is.
- The kitchen inventory, if the project keeps one, or the cook's answer to "what do you have."
- `strategy.md`: picks the style of meal from the number of people, the diets, the time, and what is on hand.
- `processes/INDEX.md`: the menu of meal styles this skill knows how to run.
- `processes/<style>.md`: the exact steps and timing for the chosen style.

The three layers divide the work like this: this file explains the job, `strategy.md` chooses the meal style, and the process file runs it. If a process disagrees with `strategy.md` about when it should be chosen, `strategy.md` wins. If `strategy.md` says anything about how to cook, ignore it and follow the process.

## How this skill runs

1. **Pin down the constraints.** How many people. Any diets, allergies, or strong dislikes. How many minutes until food needs to be on the table. What is in the kitchen. If any of these is unknown, ask the one question that unblocks the most, then proceed with a stated assumption for the rest.

2. **Run `strategy.md` to pick the meal style.** It narrows by time first, then diets, then what is on hand. It names one process file.

3. **Load and execute the picked process.** The process holds the shopping list, the timeline counted back from serving time, and the cooking steps in order.

4. **Check the plan against the constraints.** Every diet is covered by at least one full plate. The timeline ends before the deadline with ten minutes to spare. Nothing on the shopping list is already in the kitchen.

5. **Hand the cook the plan** in the structure below, then stay with them through it, adjusting as things run early or late.

## Output structure

### The call

One line: the meal style chosen and why it fits tonight.

### Shopping list

Only what the kitchen does not already have. Grouped by store section.

### Timeline

Counted back from serving time. Each line: the clock time, the action, and how long it takes.

### Cooking steps

Numbered, in order, with the sensory cue that says a step is done. Not "cook for eight minutes" but "cook until the edges brown and it smells toasty, about eight minutes."

### Adjustments

Two or three things that commonly go wrong with this style and what to do about each.

## Hard rules

- **Every diet gets a full plate.** A vegetarian does not get the meal minus the meat. They get a meal.
- **The timeline ends ten minutes early.** Things run late. Plan for it.
- **Never buy what is already in the kitchen.** Check before listing.
- **Every step has a cue, not just a time.** Ovens and stoves vary. Senses do not.
- **Do not pick a style that needs a tool the kitchen does not have.**

## When NOT to use this skill

- Dinner is for one or two and there is no deadline. Just cook.
- The group is bigger than one cook can serve at a table. That is a party, and a different plan.
- The person wants a recipe, not a plan. Give them the recipe.

$ARGUMENTS
