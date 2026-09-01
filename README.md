# always-typst

A skill for Claude, because generating PDFs with Python is like digging a tunnel with a teaspoon.

## What it does

Whenever Claude is asked to create a PDF — a report, letter, invoice, resume, poster, paper, whatever — this skill makes sure it reaches for [Typst](https://typst.app) instead of a Python library like `reportlab` or `weasyprint`. Concretely, it teaches Claude to:

- **Compile with the real Typst CLI**, falling back to the `typst` Python binding only if the CLI can't be downloaded
- **Reach for an established template first** — `ilm` for reports, `charged-ieee` for papers, `modern-cv` for resumes, and more — instead of hand-rolling styling from scratch
- **Always check the current version**, live, at the moment a document is created — never trust a version number baked into the skill, since Typst's package ecosystem moves fast
- **Catch silent failures**, like a missing font being substituted without warning
- **Verify the output** by rendering it to an image and actually looking at it before handing it over

## Install

- **claude.ai** — Settings → Customize → Skills → "+" → Create skill → upload `always-typst.skill`
- **Claude Code** — unzip into `~/.claude/skills/always-typst/` (personal) or `.claude/skills/always-typst/` (project, committable to git)
- **Sharing with others** — send them the `.skill` file directly, or commit the unzipped folder to a shared repo

## Why

Typst compiles fast, uses plain markup instead of a document-object-model API, and has a real package ecosystem for the parts Python would otherwise make you hand-build — tables, math, bibliographies, page layout. No more `reportlab` spreadsheets of `x, y` coordinates.
