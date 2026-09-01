# Process — Improve an Existing Skill

A skill that is not working is failing in one layer, and the fix belongs in that layer. This process finds the layer, fixes it, and re-runs. It does not rewrite the skill from scratch unless every layer is failing.

## Required inputs

- The skill folder, read in full before anything else. Every file.
- What the person expected and what they got. A real run, not a description of one.
- Their guess about why, if they have one. It is often right, and often about the wrong layer.

## Execution

1. **Read the whole skill.** Every file, in this order: `SKILL.md`, `strategy.md` if present, `processes/INDEX.md` if present, then each process file. Do not start fixing while reading. Note what looks off, then keep going.

2. **Reproduce the miss.** Run the skill on the case the person gave you. Watch what it does at each layer. If the person cannot give you a case, ask for the last time it went wrong and use that.

3. **Find the failing layer.** Match the miss to a layer:

   - It fired when it should not have, or did not fire when it should. That is the description line. Fix it with `references/writing-the-description.md`.
   - It picked the wrong approach. That is `strategy.md`. The decision questions are missing a case, or the tie-break points the wrong way.
   - It picked the right approach and executed it badly. That is the process file, or the steps in `SKILL.md` for a simple skill. A step is missing, out of order, or vague.
   - The result is the wrong shape. That is the output section. It is not specific enough about what goes where.
   - It skipped a step. Instructions alone did not hold. Make the step structural: give it a required line in the output so a skipped step is visible in the result. A step that leaves no trace will be skipped again.
   - It used something it should not have, or invented something. That is a missing hard rule.

4. **Fix that layer only.** Make the smallest change that closes the miss. Write the fix in the layer's own voice. If the miss is a known way to go wrong, add a WRONG and RIGHT pair next to the step so it does not come back.

5. **Re-run the same case.** The miss should be gone. If a new miss appears, it was hiding behind the first one. Go back to step three with the new miss.

6. **Run one more case.** A different one. The fix should not have broken anything else. If it did, the fix was too broad.

7. **Tell the person what changed and why.** File, section, the line before, the line after, and the miss it closes.

## Output content

The edited skill, and a short note: which layer was failing, what changed, what the re-run showed.

## What never to do

- Rewrite from scratch when one layer is off. The parts that work carry knowledge that a rewrite loses.
- Fix a strategy miss by editing a process, or a process miss by editing the strategy.
- Fix the result by hand and call the skill fixed.
- Add a rule for a miss that happened once and cannot be reproduced.
