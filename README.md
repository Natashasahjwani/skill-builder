# Skill Builder

A skill that builds skills.

A skill is a repeatable task you do again and again, written down so an AI coding agent like Claude Code does it the same way every time. This folder is a skill that takes a task you describe and turns it into a skill folder, following one consistent structure.

## The idea in one minute

There are two kinds of skills.

**Simple skills** have one reliable way to do the task. They are a repeatable procedure. Five parts make one reliable: pick one job, list the steps, define what it can use, specify the output, test and refine. A monthly performance report is a simple skill.

**Complex skills** have many valid ways to do the task, and picking the right one takes judgment. Six steps make one work: pick one job, list the processes, create a strategy doc that teaches the model when to pick each one, define what it can use, specify the output, test and refine. Writing an ad script is a complex skill.

Simple follows the recipe. Complex chooses the recipe.

Under the hood, a simple skill is one file, `SKILL.md`. A complex skill adds `strategy.md`, which decides, and a `processes/` folder with one file per way of doing the job, which execute.

## Install

Fastest way, to use it in every project on your machine:

```
git clone https://github.com/jimmyslagle/skill-builder.git ~/.claude/skills/skill-builder
```

Or copy this folder into one of these places:

- `.claude/skills/skill-builder/` inside a project, to use it in that project.
- `~/.claude/skills/skill-builder/` to use it in every project on your machine.
- `~/.codex/skills/skill-builder/` if you use Codex.

That is the whole install. Nothing else to configure. To get updates later, run `git pull` inside the folder.

## Use

Describe the task you do over and over:

```
/skill-builder make a skill for our weekly customer support summary
```

It will draft the skill from what you said, list the assumptions it made so you can correct them, write the files, run the new skill on a real case, and tell you what to watch.

To fix a skill that is not working:

```
/skill-builder the weekly-report skill keeps firing when I just ask for one number
```

## What is in this folder

- `SKILL.md`: the skill itself. Start here if you want to read how it works.
- `strategy.md`: how it decides whether your task is simple or complex.
- `processes/`: the step-by-step playbooks for building a simple skill, building a complex skill, and fixing an existing one.
- `references/`: the folder layout and section shapes, how to write the description line that makes a skill trigger at the right moment, the writing rules, and how to run a finished skill on a schedule.
- `examples/`: two complete skills to match shape against. `monthly-report` is simple. `make-dinner` is complex.
- `evals/`: test cases for checking this skill after edits.
- `agents/`: a small interface file for Codex.

## Two rules worth knowing before you start

One job per skill. If you find yourself saying "and then it should also," that is a second skill.

When in doubt, build simple. A simple skill that later needs a strategy doc is a quick upgrade. A complex skill built for a task with one path is a maze nobody needed.
