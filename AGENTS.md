# AGENTS.md

Guidance for agents working in this repository and in any job-search workspace that
uses these skills.

## Skills

- `.agents/skills/job-fit-evaluator/` evaluates the candidate's materials against a
  job description.
- `.agents/skills/application-tailor/` produces a role-targeted, standalone copy of
  the candidate's materials.

Both use the open Agent Skills layout, read by Codex, OpenCode, Cursor, Gemini CLI,
and other compatible agents. Agents that only look in `.claude/skills/` (for example
Claude Code) can follow these files directly, or expose them locally (that path is
git-ignored): on macOS/Linux use `ln -s`, on Windows use `mklink /J` - see the
repo `README.md` for the exact commands.

## Ground rules

- Ground every claim in the candidate's real materials. Never invent experience, metrics, tools, outcomes, or credentials.
- Never edit a master copy. Tailor on a copy.
- Tailored outputs must stand alone: no imports or links into the candidate's other files.
- Adapt to the candidate's field and format. Do not assume software engineering, LaTeX, or any specific tool.
- Do not assume a toolchain is installed, and do not install one. Validate by inspection.
- PDFs and exports are local artifacts and are git-ignored. Never treat a missing export as a failure.
- File organization is the candidate's choice. Do not impose a directory structure.

## Content rules

- Keep facts consistent across everything you produce for a candidate.
- If a job description asks for something the candidate lacks, say so; do not fake it.
- Be direct and specific. Cite the materials rather than guessing.
