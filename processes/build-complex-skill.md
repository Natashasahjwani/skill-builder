# Process — Build a Complex Skill

A complex skill chooses the recipe, then follows it. It has three layers: `SKILL.md` explains the job and what it can use, `strategy.md` teaches Claude when to pick each way of doing it, and `processes/` holds one file per way with the exact steps. The shape of each file is in `references/skill-anatomy.md`; this file is the order of work.

## Required inputs

- The task, in the person's words.
- The different ways they do it, and what makes them pick one over another. If they cannot name at least two ways, stop and re-check `strategy.md`. It may be a simple skill.
- What they use: documents, tools, data connections, past results.
- A real finished result from at least two of the ways, if they exist.

## Execution

1. **Pick one job.** One sentence, verb first, names the finished thing. Same rule as a simple skill. The job is the same no matter which way it is done. If the ways produce different finished things, they are different jobs.

2. **List the processes.** Every genuinely different way the task can be done. Give each a short name that says what makes it different. Test each one: is this a different approach, or a stage of the same approach? Stages go inside a process as numbered steps. Approaches get their own file. Three to eight processes is the usual range. One is a simple skill. More than ten means at least one of them is a stage in disguise.

   WRONG: processes named "research," "draft," "review." Those are stages.
   RIGHT: processes named "problem-first," "story-first," "comparison." Those are ways.

3. **Create the strategy doc.** This is the file that teaches Claude to choose. It has four parts: what to load before deciding, the questions to ask about the situation, which answers point to which process, and a tie-break for when it is unclear. Write the choice logic as decisions, in order, each one narrowing the field. The strategy doc decides and stops. It never carries steps.

4. **Write each process file.** One file per way. Each holds: a one-line summary of the way, when to pick it and when not to, the required inputs, the numbered steps, what the output contains, and what never to do in this way. A process file assumes `SKILL.md` and `strategy.md` are loaded, so it carries only what is specific to this way. Shared rules stay in `SKILL.md`.

5. **Write the process index.** `processes/INDEX.md` lists every process with one line each: the name, what it is, and what it is best for. This is the menu `strategy.md` chooses from.

6. **Define what it can use.** In `SKILL.md`, name every input, document, tool, and data connection, and where each lives. Name the three layers and how they divide the work: `SKILL.md` for the job, `strategy.md` for the choice, `processes/` for the steps. Say which wins when two files disagree.

7. **Specify the output.** In `SKILL.md`, the parts of the finished result that are the same no matter which process ran. In each process file, the parts that are specific to that way. The `SKILL.md` output section is the contract; the process file fills it in.

8. **Add the hard rules to `SKILL.md`.** The rules that hold across every process. A rule that only applies to one way of doing it goes in that process file under "What never to do."

9. **Write the description line.** Follow `references/writing-the-description.md`.

10. **Test and refine.** Run the skill on two real cases that should pick different processes. Check two things separately: did `strategy.md` pick the right process, and did the process produce the right result? A wrong pick is a strategy fix. A wrong result is a process fix. Do not fix one by editing the other.

## Output content

One folder holding `SKILL.md`, `strategy.md`, and `processes/` with `INDEX.md` plus one file per way. `SKILL.md` sections in this order: frontmatter, title, Goal, What it can use, How this skill runs, Output structure, Hard rules, When NOT to use this skill. The How this skill runs section always includes a step that says "run `strategy.md` to pick the process" and a step that says "load and execute the picked process file."

## What never to do

- Put steps in the strategy doc.
- Put choice logic in a process file.
- Paste the same rule into every process file. Move it to `SKILL.md`.
- Build a complex skill because the task felt important. Importance is not the test.
- Test with one case. One case cannot show whether the choice works.
