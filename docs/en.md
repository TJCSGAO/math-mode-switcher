# math-mode-switcher

## Overview

`math-mode-switcher` is a lightweight TraeWork skill for standardizing how mathematical expressions are presented in conversation. Its purpose is not to invent new formulas, but to ensure that formulas are returned in the **right display mode** for the user's current need.

It addresses a very common interaction problem:

- when the user wants rendered math, the model returns raw code
- when the user wants reusable source code, the model returns only visual rendering
- when the user wants both, the conversation becomes repetitive and ambiguous

## Why it matters

For users who frequently work with formulas, formatting ambiguity creates unnecessary friction in:

- academic writing
- patent drafting
- technical reports
- LaTeX / PDF preparation
- formula review and revision

This skill introduces a compact and explicit protocol for formula display, which can significantly reduce back-and-forth clarification.

## Supported modes

### Render mode

Used when the user wants to see the final visual presentation of a formula.

Rules:
- inline math uses `$...$`
- display math uses `$$...$$`
- multi-line derivations prefer `aligned`
- formulas intended for rendering should not be wrapped in ` ```latex ` code fences

Typical use cases:
- previewing how LaTeX will look
- checking visual clarity
- reviewing equation layout

### Source mode

Used when the user needs copyable formula code.

Supported variants:
- `Source mode (Markdown)`
- `Source mode (LaTeX)`

Typical use cases:
- pasting into Markdown editors
- inserting equations into LaTeX projects
- preparing formulas for PDF, Word, or automated document pipelines

### Dual mode

Shows the rendered result first, then provides copyable source code.

Typical use cases:
- reviewing and copying in one pass
- reducing coordination overhead in collaborative workflows
- keeping both readability and reusability

## Recommended prompts

Use one of the following:

- `Mode: render`
- `Mode: source (md)`
- `Mode: source (latex)`
- `Mode: dual`

Users may also directly say:

- `render mode`
- `source mode`
- `dual mode`

## Default inference logic

When the user does not explicitly specify a mode, the skill recommends:

- requests like "show me how it renders" -> default to `render mode`
- requests like "I need code for PDF / LaTeX / Word" -> default to `source mode (LaTeX)`
- ambiguous cases -> default to `dual mode`

## Best practices

- ask for `Markdown` or `LaTeX` explicitly when source code is needed
- prefer `$$...$$` for display equations
- if rendering fails for complex structures, provide LaTeX source first and a simplified rendered version second
- in long-running collaborations, make `dual mode` the default interaction contract

## Installation

Copy `.trae/skills/math-mode-switcher/` into your workspace so that the final path becomes:

```text
<your-workspace>/.trae/skills/math-mode-switcher/SKILL.md
```

## Files

- Main skill file: `.trae/skills/math-mode-switcher/SKILL.md`
- Chinese documentation: `docs/zh-CN.md`
