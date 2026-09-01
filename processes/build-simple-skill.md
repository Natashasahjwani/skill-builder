# Process — Build a Simple Skill

A simple skill is a repeatable procedure written down so Claude follows it the same way every time. It is one file, `SKILL.md`, with five parts. The shape of each section is in `references/skill-anatomy.md`; this file is the order of work.

## Required inputs

- The task, in the person's words.
- The steps they follow today, even if rough.
- What they use to do it: documents, tools, data connections, past results.
- A real finished result, if there is one.

## Execution

1. **Pick one job.** Write the job as a single sentence that starts with a verb and names the finished thing. "Write the monthly performance report from last month's numbers." If the sentence needs an "and," it is two jobs. Keep the first, note the second. This sentence becomes the first line of the Goal section, and the description line grows out of it.

2. **List the steps in the order they actually happen.** Ask the person what they do first, then next, then next. Write each step as a numbered line with a bold lead of three to six words, then one to three sentences on what the step does and what it produces. Include the steps they skip when they are rushed. Those are usually the ones that matter.

   WRONG: "Gather the data, analyze it, and write the report."
   RIGHT: "1. **Pull last month's numbers** from the source named below. 2. **Compare each number to the month before** and to the goal. 3. **Write one line per number** saying whether it moved, which way, and the most likely reason."

3. **Define what it can use.** Make a section that names every input and where it lives: documents by path, tools by name, data connections by name, folders to read. Say what to do when one is missing, and what to do when it is there but empty or half filled in. A blank column is the case that gets missed. Claude does not know anything it was not told, so a step that says "check the numbers" with no source will be guessed.

4. **Specify the output.** This is the most important section. Name every part of the finished result, in order, and say what goes in each, how long it is, and what stays out. If the person has a real finished example, describe its shape here, part by part. Do not paste the example in. Describe the shape.

5. **Add the hard rules.** The things that must never happen. Numbers that must not be invented. Sources that must be named. Language that must not be used. Bold lead, then one sentence. Five to twelve rules is the usual range. More than that and the important ones get lost.

6. **Write the description line.** Follow `references/writing-the-description.md`. What it does, when to use it, what it does not do.

7. **Test and refine.** Run the skill on one real case. Compare the result to what the person expected. Where it missed, fix the instruction that caused the miss, not the result. Run again. A simple skill usually settles in two or three runs.

## Output content

One folder holding one `SKILL.md`, with these sections in this order: frontmatter, title, Goal, What it can use, How this skill runs, Output structure, Hard rules, When NOT to use this skill.

## What never to do

- Add a strategy doc or a processes folder. That is a complex skill. If you feel the pull, go back to `strategy.md` and re-check.
- Write steps in the tidy order instead of the real order.
- Leave the output section as a single sentence.
- Call it done without a run.
