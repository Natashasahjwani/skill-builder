---
name: skill-builder
description: Turn a task you do over and over into a skill Claude can run the same way every time. Builds the folder, the SKILL.md, and, when the task has more than one good way to do it, the strategy doc and one process file per way. Use when someone says make this a skill, build a skill for X, turn this into a repeatable process, or wants to fix a skill that keeps getting it wrong. Works in any project and needs nothing outside this folder.
argument-hint: "[the task to turn into a skill, or the path of a skill to improve]"
---

# Skill Builder

## Goal

Turn one repeatable task into a skill: a folder Claude can load that explains the job, the steps, what it may use, and what the finished result looks like. A good skill means the task gets done the same way whether the person runs it today, next month, or hands it to a teammate who has never done it.

This skill builds and improves skills. It does not run the skill it builds, and it does not decide which of your tasks deserve to be skills. If the request is "do the task," do the task. If the request is "make it so this task gets done the same way every time," this is the skill.

## The two kinds of skills

One decision shapes everything else: does the task have one reliable path, or many?

- **Simple skill.** One consistent way to do it. A repeatable procedure written down. It follows the recipe. A monthly performance report is a simple skill.
- **Complex skill.** Many valid ways to do it, and picking the right one takes judgment. It chooses the recipe, then follows it. Writing an ad script is a complex skill.

Simple follows the recipe. Complex chooses the recipe.

A simple skill is one file: `SKILL.md`. A complex skill adds `strategy.md`, which teaches Claude when to pick each way, and a `processes/` folder with one file per way. `strategy.md` in this folder holds the test for telling the two apart, and it leans simple. Most tasks are simple. A complex skill that should have been simple is slower and more fragile, not smarter.

## What it can use

- `strategy.md`: how to decide simple or complex, and which process file to run.
- `processes/INDEX.md`: the menu of processes, one per way this skill can run.
- `references/skill-anatomy.md`: the folder layout and the section-by-section shape of a SKILL.md. Every build process assumes it is loaded.
- `references/writing-the-description.md`: how to write the description line. That line is what decides whether the skill wakes up at the right moment.
- `references/writing-rules.md`: the style rules every file in a skill follows.
- `references/routines-loops-goals.md`: how to make a finished skill run on its own on a schedule.
- `examples/`: two complete skills, one simple and one complex, to match shape against.
- The person's own material: the steps they follow today, the documents they lean on, the tools and data connections they have, and a real finished result if one exists. Ask for a real finished example. One is worth more than any amount of description.

## How this skill runs

1. **Get the job into one sentence.** Read what the person gave you, and if a skill already exists at the path they named, read the whole thing before anything else. Write the job as one sentence that starts with a verb and names the result. If you cannot, the request is either two jobs or not yet a job. Say which.

2. **Decide simple or complex.** Run `strategy.md`. It asks whether the person does this the same way every time or picks an approach depending on the situation. Name the answer and the reason in one line. When you genuinely cannot tell, build simple.

3. **Draft first, ask second.** Lead with the most complete draft you can from whatever you were given, even if that is a single line. This is not an interview. Make sensible assumptions, list them in a short block above the draft, and let the person correct you. Ask a question only when the answer changes the shape of the skill and you cannot guess well. Ask at most two, and ask them after the person has seen something concrete.

4. **Load and execute the picked process.** `build-simple-skill` for one path, `build-complex-skill` for many, `improve-existing-skill` when there is already a skill and it is not working. Each process is the step-by-step playbook. Follow it in order.

5. **Write the files.** Create the folder in the place the person wants it. Project skills go in `.claude/skills/<name>/` inside the project. Personal skills that should work everywhere go in `~/.claude/skills/<name>/`. If they did not say, default to the project and tell them. Never overwrite an existing skill you have not read.

6. **Self-check against the hard rules below.** Fix every miss before showing the draft. Then read the description line on its own and ask: would Claude know when to reach for this, and when not to?

7. **Test it for real.** Run the new skill on one real case, the messier the better. Compare what came out to what the person expected. Fix the instructions where they missed, not the output. A skill that has never run is a draft, not a skill.

8. **Hand it back.** Show the folder, the files, how to run it, what happened in the test, and what to watch on the next few runs. Then, if the task should happen on a schedule, point at `references/routines-loops-goals.md` and offer to set that up.

## Output structure

### The skill folder

For a simple skill:

```
<skill-name>/
└── SKILL.md
```

For a complex skill:

```
<skill-name>/
├── SKILL.md
├── strategy.md
└── processes/
    ├── INDEX.md
    └── <one file per way of doing the task>.md
```

Either kind may add `references/` for knowledge that is too long for SKILL.md, and `evals/evals.json` for test cases. The full layout and the shape of every section lives in `references/skill-anatomy.md`.

### The message back to the person

In this order:

- **Assumptions I made.** Three to six lines. The job as you understood it, simple or complex and why, what inputs you assumed exist, and any judgment call.
- **What I built.** The file list with one line per file saying what it holds.
- **How to run it.** The exact command, with the argument if it takes one.
- **The test run.** What case you ran it on, what came out, what you changed because of it.
- **What to watch.** The two or three places most likely to need tuning after three real runs.

## Hard rules

- **One job per skill.** If the request holds two jobs, build the first and name the second. A skill that does two things does both worse.
- **Steps in the order a person actually does them.** Not the order that looks tidy. Ask "what do you actually do first?" and write that.
- **Name everything the skill may use.** Every input, document, tool, data connection, where each one lives, and what to do when one is missing or empty. Claude does not know anything it was not told. A step that says "check the numbers" without saying where the numbers are will be guessed.
- **The output section is the most specific section.** Say every part the finished result contains, in order, and what goes in each. A vague output section is the single biggest cause of a skill that produces something different every run.
- **Simple stays one file.** Do not add a strategy doc or processes to a task with one path. A branch that says "if this input is missing, skip step four" is a step, not a second process.
- **In a complex skill, every process is a genuinely different way to do the job.** Not a stage of the job. Stages go inside a process as numbered steps. Ways get their own file.
- **The strategy doc decides. It never does the work.** The process files do the work. They never decide. If a process file is choosing between approaches, that choice belongs in `strategy.md`.
- **Point at knowledge, do not paste it.** If the rules live in a document, name the document and its path. A pasted copy is stale the moment the original changes.
- **Plain language.** Written so someone new to the team could follow it on day one. Short sentences. Common words. No invented vocabulary.
- **Describe the shape, never a list of examples.** Say what kind of thing goes in a section. Do not give a list of sample values. Claude copies example lists, and every result ends up sounding the same.
- **Show a failure by contrast.** When a step has a known way to go wrong, write the WRONG version and the RIGHT version next to each other. A description of the mistake is not enough.
- **Specific over vague.** The words several, many, some, and a few do not appear. Say the number or say the rule.
- **Never call it done without a real run.** Step seven is not optional.
- **Ask before writing outside the skill folder.** Creating the skill folder and its files is the job. Editing other files in the project is not, unless the person asked.

## When NOT to use this skill

- The person wants the task done, not turned into a skill. Do the task.
- The task has been done once and may never be done again. A skill pays off on the third run, not the first.
- The change is a typo or a wording fix inside an existing skill. Just edit it.
- The task is really a one-line reminder. Put it in the project's instructions file instead.

$ARGUMENTS
