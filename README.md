# cv-match

Two small [Agent Skills](https://agentskills.io) that turn any AI coding agent into
a job-application assistant: **score how well your materials fit a role**, then
**tailor them to it**. Works for any field and any file format - engineering,
design, product, marketing, and everything in between.

There is no prescribed folder structure. You bring your CV/resume, portfolio, and
job descriptions wherever they already live; the skills ask for paths and work with
what you have.

## What's here

```
.agents/skills/
├── job-fit-evaluator/   # Evaluate your materials against a job description
└── application-tailor/  # Produce a role-targeted version of your materials
```

## The workflow

1. **Keep a source of truth.** The real versions of your resume/CV, portfolio
   pieces, case studies, project write-ups, and the numbers behind them. One place,
   any format. Every claim the agent makes must trace back to these materials.
2. **Get the job description.** A file, pasted text, or a URL.
3. **Evaluate.** Ask the agent to evaluate your materials for the role. You get an
   honest, structured report - fit score, qualifications match, gaps, red flags,
   next steps - written to `output/<company>-<role>.md`.
4. **Tailor.** If it's worth applying, ask the agent to tailor your resume/CV, cover
   letter, or portfolio ordering for that role. It works on a copy and produces a
   standalone version.
5. **Review and send.** The master stays untouched. Export whatever the employer
   wants; PDFs and other exports are not tracked.

## Principles

- **Truth over polish.** The evaluator is a tough hiring manager, not a cheerleader.
  It cites evidence and never fabricates.
- **Masters are sacred.** Tailoring always happens on a copy; source-of-truth files
  are never edited.
- **Standalone outputs.** A reviewer receives one file, so tailored materials do not
  import or link to your other files.
- **Any field, any format.** The evaluator adapts its criteria to the role instead
  of assuming software or LaTeX. A designer's portfolio is judged as a portfolio.
- **You organize your files.** Per-application folders, one flat folder, or a branch
  per application - all fine. Nothing here requires a layout.

## Worked examples

The folder names below are just one way to stay organized. Use your own.

### Software engineer

- Source of truth: `resume.md`, `projects/`, `brag-doc.md`
- Job description: `jds/stripe-senior-backend.txt`
- Evaluate → `output/stripe-senior-backend.md`
- Tailor → `applications/stripe-senior-backend/resume.md` (plus optional
  `cover-letter.md`)

### Graphic designer

- Source of truth: `cv.md`, `portfolio/` (case-study PDFs), `case-notes.md`
- Job description: `jds/studio-brand-designer.txt`
- Evaluate → `output/studio-brand-designer.md`
- Tailor → `applications/studio-brand-designer/cv.md`,
  `applications/studio-brand-designer/portfolio-order.md`,
  `applications/studio-brand-designer/cover-letter.md`

## Using the skills

The skills live at `.agents/skills/`, the open Agent Skills location, so they work
unchanged in Codex, OpenCode, Cursor, Gemini CLI, GitHub Copilot, and other
compatible agents. Codex also reads `AGENTS.md`.

Options:

- **Clone this repo** and add your own materials next to it, then point the agent at
  your files.
- **Copy `.agents/skills/`** into an existing job-search repo.
- **Install to your user skills** (`~/.agents/skills/`) to use them anywhere.

Claude Code currently loads skills only from `.claude/skills/`. Either let it follow
`.agents/skills/<name>/SKILL.md` directly, or expose them locally (that path is
git-ignored):

macOS / Linux:

```sh
mkdir -p .claude/skills
ln -s ../../.agents/skills/job-fit-evaluator .claude/skills/job-fit-evaluator
ln -s ../../.agents/skills/application-tailor .claude/skills/application-tailor
```

Windows (a directory junction needs no admin rights), from the repo root:

```bat
mkdir .claude\skills
mklink /J .claude\skills\job-fit-evaluator .agents\skills\job-fit-evaluator
mklink /J .claude\skills\application-tailor .agents\skills\application-tailor
```

The repository contains no committed symlinks, so it clones and works the same on
Linux, macOS, and Windows.

## PDF policy

PDFs and other exports are local build artifacts and are **not tracked** - see
`.gitignore`. Commit your sources (in whatever format) and export the file you
actually send.

## License

MIT. See [LICENSE](LICENSE).
