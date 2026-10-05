---
name: application-tailor
description: Use when tailoring application materials to a specific job description - resume, CV, cover letter, portfolio ordering, or a short "why this role" note. Produces a standalone, role-targeted copy without touching the candidate's master files. Works for any field and any format. Use when the user asks to tailor, customize, adapt, or target their resume/CV/cover letter/portfolio to a role.
---

# Application Tailor

Produce a role-targeted version of the candidate's application materials that
stands on its own and honestly reflects their real experience. This is the second
half of the workflow: run `job-fit-evaluator` first if the user has not already
assessed the fit.

## Workflow

### Step 1: Ground in truth

Read the candidate's source-of-truth materials and the target job description. If
either is missing, ask for it. Never invent experience, metrics, tools, projects,
or credentials. If the JD asks for something the candidate lacks, do not fake it -
note the gap so the candidate can decide.

### Step 2: Identify the format and work on a copy

Never edit a master file. Always tailor a copy.

- Determine the format the candidate uses (Markdown, LaTeX, DOCX, Google Doc
  export, plain text, ...).
- If you can edit that format directly, produce a new file.
- If you cannot (e.g. a binary format), produce the tailored text in Markdown for
  the candidate to transfer.

### Step 3: Tailor to the role

- Lead with what the job description weights most: reorder sections, projects, and
  bullets so the most relevant material comes first.
- Mirror the JD's vocabulary only where it is honest - no keyword stuffing.
- Cut or shorten anything irrelevant to this role.
- Keep the strongest, most specific evidence; keep real numbers.
- Match the register of the field: a design portfolio leads with the work and
  process; a backend resume leads with systems and outcomes; a marketing CV leads
  with campaigns and results.
- Optionally draft a cover letter or a short "why this role" note if the
  application asks for one.

### Step 4: Keep it standalone

The tailored file must stand alone, because a reviewer receives one file. Do not
introduce imports, includes, or links to the candidate's other files; copy the
needed content in.

### Step 5: Save and report

Save to a path the user chooses. If they have no preference, suggest:

`<materials-dir>/<company>-<role>-<type>.<ext>`

Then report briefly:

- What you changed and what you emphasized
- Which parts of the JD the tailored version now speaks to
- Anything the candidate must verify or add before sending

## Principles

- Never fabricate. Gaps get flagged, not papered over.
- Preserve the candidate's voice; edit rather than rewriting into generic prose.
- Never overwrite a master file.
- Prefer fewer, stronger, more relevant items over a longer list.
