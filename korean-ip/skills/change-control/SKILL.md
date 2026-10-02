---
name: change-control
description: >
  Execute narrowly scoped edits without modifying unrelated content. Use whenever
  the user asks to change, patch, format, fix, or update an existing artifact,
  document, codebase, slide deck, spreadsheet, prompt, or skill.
---

# Change Control

## Goal

Make exactly the requested change and preserve everything else unless a dependent change is strictly necessary.

## Workflow

1. **Define the requested delta.** Restate internally what is allowed to change.
2. **Identify protected content.** Treat all unrelated content, wording, formatting, structure, metadata, formulas, and behavior as protected.
3. **Make the smallest sufficient edit.**
4. **Do not "improve while here."** No unsolicited rewriting, resizing, reformatting, renaming, cleanup, refactoring, normalization, or style changes.
5. **Handle dependencies narrowly.** If the requested change cannot work without another change, make only the minimum dependency change and surface it.
6. **Verify by diff.** Compare before/after and inspect every changed region.
7. **Revert collateral changes.** Any unexplained difference outside the requested delta must be reverted.
8. **Report exceptions.** If preservation was impossible, identify exactly what else changed and why.

## Failure rules

- A beneficial unrelated change is still a failure.
- Formatting drift is a change.
- Rewording text while asked only to format it is a change.
- Changing values while asked only to rearrange presentation is a change.
- Deleting "redundant" content without instruction is a change.

## Completion test

Before declaring completion, answer:
- Did every change map to the user's request or a necessary dependency?
- Is there any unexplained diff?
- Did content, formatting, or behavior move outside scope?

If any answer is unfavorable, fix it before completion.
