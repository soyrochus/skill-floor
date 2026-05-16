# Structured HTML Report Skill for GitHub Copilot

This package provides a GitHub Copilot-oriented skill for generating rich, visually polished, and iteratively editable HTML reports.

The objective is to move beyond simple Markdown output. Reports generated with this skill should be complete HTML documents using Tailwind CSS, minimal dependencies, inline SVG diagrams, optional Chart.js charts, print support, stable section IDs, bounded edit regions, editable components, and a machine-readable manifest so future Copilot edits can target precise parts of the document.

## Folder layout

The repository folder is named `_github` in this ZIP so it is easy to view in editors and file explorers. For actual use in a GitHub repository, copy or rename `_github` to `.github`.

```text
html-report-copilot-skill-v2/
  README.md
  _github/
    copilot-instructions.md
    skills/
      structured-html-report-skill/
        SKILL.md
    prompts/
      create-structured-html-report.prompt.md
      edit-structured-html-report.prompt.md
    templates/
      report-shell.html
      component-patterns.html
    examples/
      delivery-transformation-report.html
```

Target repository layout after installation:

```text
.github/
  copilot-instructions.md
  skills/
    structured-html-report-skill/
      SKILL.md
  prompts/
    create-structured-html-report.prompt.md
    edit-structured-html-report.prompt.md
  templates/
    report-shell.html
    component-patterns.html
  examples/
    delivery-transformation-report.html
```

## Installation

Recommended full installation:

```text
1. Copy `_github` into your repository.
2. Rename `_github` to `.github`.
3. Commit the `.github` folder.
```

Recommended minimal installation:

```text
.github/copilot-instructions.md
.github/skills/structured-html-report-skill/SKILL.md
```

Recommended full installation paths:

```text
.github/copilot-instructions.md
.github/skills/structured-html-report-skill/SKILL.md
.github/prompts/create-structured-html-report.prompt.md
.github/prompts/edit-structured-html-report.prompt.md
.github/templates/report-shell.html
.github/templates/component-patterns.html
.github/examples/delivery-transformation-report.html
```

## Usage

Ask GitHub Copilot Chat to use the skill when creating or editing reports. Example prompts:

```text
Use the structured HTML report skill to create a polished Tailwind HTML report from these notes.
```

```text
Use the structured HTML report skill. Create an iterable HTML report with stable section IDs, bounded edit regions, inline SVG, a risk table, and a report manifest.
```

```text
Edit only the section-executive-summary region of this report. Preserve all existing IDs and update the manifest only if necessary.
```

## Design stance

This skill treats the report as a durable document artifact, not a one-shot webpage. The generated HTML should be attractive, but also easy for Copilot to edit incrementally across multiple interactions.

The practical rule is simple: generate structured HTML that is pleasant for humans to read and stable enough for AI to modify without rewriting everything.
