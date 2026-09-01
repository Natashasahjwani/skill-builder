# Skill Anatomy

The folder layout and the shape of each file. Every build process assumes this is loaded.

## The folder

A skill is a folder. The folder name is the skill name: lowercase, words joined by hyphens, verb first when it does something (`write-weekly-report`), noun when it is a thing (`hooks`). The folder name and the `name` field in the frontmatter must match.

Simple skill:

```
<skill-name>/
└── SKILL.md
```

Complex skill:

```
<skill-name>/
├── SKILL.md
├── strategy.md
└── processes/
    ├── INDEX.md
    └── <way-one>.md
    └── <way-two>.md
```

Optional additions, for either kind:

- `references/`: knowledge that is too long for SKILL.md and that more than one step or process needs. Point at these files by name from the steps. Keep each one about one thing.
- `evals/evals.json`: test cases. A list of objects, each with an `id`, a `prompt` (what someone would ask), and an `expected_output` (what a correct run does, in one or two sentences). Used to check the skill after edits.
- `agents/openai.yaml`: a small interface block if the skill also runs in Codex. Display name, a one-line description, and a default prompt.

Where it lives:

- `.claude/skills/<skill-name>/` inside a project: the skill works in that project and travels with it.
- `~/.claude/skills/<skill-name>/`: the skill works in every project on this machine.
- Codex reads from `~/.codex/skills/<skill-name>/` with the same layout.

## SKILL.md

The one required file. Frontmatter, then the sections below in this order. Headers only; the prose under each header describes what belongs there.

```
---
name: <matches the folder name>
description: <see writing-the-description.md>
argument-hint: "<optional, what to type after the command>"
---

# <Title>

## Goal

## What it can use

## How this skill runs

## Output structure

## Hard rules

## When NOT to use this skill
```

What each section holds:

**Frontmatter.** `name` and `description` are required. `argument-hint` is optional and shows the person what to type after the skill name. Nothing else goes here.

**Title.** The skill name as a heading, in plain words.

**Goal.** What the skill produces and why it matters, in two to four sentences. Then, in its own short paragraph, what the skill does not do and where that work goes instead. A skill that names its edges is picked correctly more often than one that does not.

**What it can use.** Every input and where it lives. Documents by path. Tools and data connections by name. Folders to read. For a complex skill, this is also where the three layers are named and their division of labor stated: SKILL.md for the job, strategy.md for the choice, processes for the steps, and which wins when they disagree.

**How this skill runs.** Numbered steps in the order they happen. Each step starts with a bold lead of three to six words, then one to three sentences. For a complex skill, one step says to run strategy.md and pick, and the next says to load and execute the picked process. Steps that produce something say what they produce. Steps with a known way to go wrong carry a WRONG and RIGHT pair.

**Output structure.** The most specific section in the file. Each part of the finished result gets a `###` sub-heading, in the order it appears, with what goes in it, how long, what to include, what to leave out. If the finished result has parts that prove a step ran, such as a list of sources used or a check that passed, those parts are named here. A step that leaves no trace in the output will be skipped.

**Hard rules.** The rules that must hold on every run. Bulleted, bold lead, then one sentence. Absolute language: never, always, every, none. Five to twelve is the usual range. A rule that only applies to one process goes in that process file instead.

**When NOT to use this skill.** Three to five situations where this skill is the wrong tool, and what to do instead.

Simple skills that take an argument end with `$ARGUMENTS` on its own line, so what the person typed after the command lands in the skill.

## strategy.md

Only in a complex skill. Its whole job is to decide which process to run. Headers only:

```
# <Skill> — Strategy

## What to load before deciding

## <First decision>

## <Second decision>

## Which process
```

The decision sections are questions about the situation, in the order they narrow the choice. Each one says which answers point to which process. The last section maps the answers to process names, with a tie-break for when it is unclear. The strategy doc never carries steps. If a step appears here, it belongs in a process file.

## processes/INDEX.md

Only in a complex skill. A short intro saying what a process is in this skill and what to load first, then one bullet per process: bold name, what it is, what it is best for. This is the menu strategy.md picks from.

## processes/<name>.md

One per way of doing the job. Headers only:

```
# Process — <Name>

## When to pick

## Required inputs

## Execution

## Output content

## What never to do
```

The first paragraph under the title is one or two sentences on what makes this way different. When to pick has a best-for line and a worst-for line. Execution is numbered steps with bold leads, the same shape as SKILL.md. Output content lists what this way adds to the shared output contract. What never to do holds the rules specific to this way. A process file assumes SKILL.md and strategy.md are loaded and repeats nothing from them.
