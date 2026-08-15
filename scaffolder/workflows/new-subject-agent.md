# New Subject Agent — Research & Report Workflow

Recipe for turning a class/subject name into a structured report that guides building a study-help agent for it. Follow every step in order — do not skip straight to research.

## Step A — Clarify before researching

Always ask first (never assume). Ask in this order:

1. **Scope** — a specific course (e.g. "AE 168 – Orbital Mechanics") vs. a general subject area; any specific textbook, syllabus, or professor materials to align to.

2. **Intended use** — branch on the Scope answer:
   - **Specific materials named** (syllabus, textbook, professor materials): ask whether they'd like intended use/agent functionality determined by analyzing those materials instead of answering directly — e.g. a syllabus full of weekly problem sets implies homework/problem-solving support; a project-based syllabus implies project/design support. This inference is opt-in — always confirm they want it before doing it.
     - If **yes**: get the materials (ask them to share/upload if not already provided), analyze them, then propose the inferred intended use back to the user ("Based on [X], it looks like this agent should mainly help with ___ — sound right?") and confirm/adjust before moving on.
   - **Whenever the user shares/uploads source materials** (syllabus, textbook excerpts, professor materials — whether for the intended-use inference above or just for research in Step C), save a copy of each into `resources/<subject-slug>-source-<descriptive-name>.md` (or the original file type if not text) right away, so they're on hand to copy into the new agent's `resources/` folder in Step G.
     - If **no**, or no materials exist: ask directly what the agent should help with — homework/problem-solving, concept explanation, exam prep, project/design work, equation derivation, etc.
   - **General subject, no specific materials**: ask directly, same as above.

3. **Coverage** — whole-course breadth vs. just the current unit/topic they're stuck on right now.

## Step B — Show a short research plan

Before doing any web research, post a 3-5 bullet outline of what you're about to look into, so the user can redirect early if it's off-target.

## Step C — Research

Scope: course-level fundamentals only, unless the user asked for more in Step A.

- Standard topic/unit breakdown for the subject at the relevant course level.
- Core equations, models, or concepts typically covered.
- Common textbook(s)/reference structure.
- Only go beyond this (student pain points, tools/software, study strategies) if explicitly requested in Step A.

## Step D — Organize into a structured report

Sections, in order:

1. **Subject Overview**
2. **Key Topics & Standard Structure** (bulleted, by unit/module)
3. **Core Equations/Concepts**
4. **Recommended Agent Capabilities** (tied directly to the "intended use" answer from Step A)
5. **Agent Design Notes** (persona/tone, example prompts, what context the agent would need — guidance, not a runnable config)
6. **Key Takeaways & Recommended Next Steps** (short bulleted summary of the main findings, plus concrete next actions for building/using the agent)
7. **Sources** (every claim traceable to a source)

Format: bullet points over paragraphs, concise. Write equations in the "Core Equations/Concepts" section using LaTeX math notation (`$...$` inline, `$$...$$` or `\displaystyle` for standalone), not plain Unicode/text symbols — VS Code's Markdown Preview (Ctrl+Shift+V) renders it natively. Add a one-line note at the top of that section pointing this out. For calculus-based courses, prefer showing the underlying calculus definition/derivation alongside any simplified algebraic special case.

## Step E — Save output

Write the report to `output/<subject-slug>-agent-report.md` (kebab-case slug of the subject/course name).

## Step F — Get approval on the report

- After saving the report, present it to the user and ask: "Does this report look good?"
- If **no**: ask what to fix, revise the report (re-research if needed), re-save, and re-ask. Repeat until approved.
- If **yes**: proceed to Step G.

## Step G — Create the sibling subject agent

Once approved, scaffold a new agent for this subject automatically — do not re-ask setup questions, these are fixed conventions:

- **Location**: new sibling folder at `<workspace-root>/<Subject>/` (e.g. "MATH 31"), sibling to the "agent 1" workspace — not nested inside it.
- **Scaffold**: create empty `workflows/`, `output/`, `resources/` subfolders.
- **CLAUDE.md**: write a tailored file in the new folder with these sections:
  - Project Context — dedicated study-help agent for this specific subject/course
  - About ME — reuse relevant facts from the root CLAUDE.md (year, major, school) plus the specific course
  - Course Scope — topic/unit breakdown pulled from the report's "Key Topics & Standard Structure" section, with a pointer to the copied report for full detail
  - Persona & Tone — derived from the report's "Agent Design Notes" section (patient tutor, explain the "why" before formalizing notation, jargon-free); note that the nudge-before-revealing style is specifically the Walkthrough-mode default — which mode applies to a given problem is decided by `workflows/problem-solving-mode.md`
  - Rules — same baseline as agent 1's CLAUDE.md (ask clarifying questions, show plan before executing, concise bullet-point output, save outputs to output/, cite sources), plus one tailored to the subject (e.g. checking work step-by-step), plus: in live chat, write math in plain readable notation (e.g. `F_net = ma`, `dv/dt`), not raw LaTeX — the chat panel doesn't render LaTeX and it just shows as clutter; reserve LaTeX (`$...$` inline, `$$...$$` display) for saved output files (reports, worked solutions), where VS Code's Markdown Preview renders it properly, plus: when a problem is uploaded or pasted (homework question, derivation, "solve for X"), follow `workflows/problem-solving-mode.md` — ask whether the student wants step-by-step (with answer), a guided walkthrough (they solve each step), or answer verification, before proceeding
  - Project Structure — same three-folder description as agent 1
- **Resources**: copy the approved report from `agent 1/output/<subject-slug>-agent-report.md` into the new folder's `resources/` directory (keep the same filename), plus any source materials saved during Step A (`agent 1/resources/<subject-slug>-source-*`) — carry the user's original syllabus/textbook/professor materials over so the new agent has them on hand, not just the derived report.
- **Workflows**: copy `agent 1/resources/problem-solving-mode-template.md` into the new folder as `workflows/problem-solving-mode.md` (no customization needed — it's subject-agnostic).
- Do **not** copy the `.claude/skills/new-subject-agent/` skill into the new folder — it's a meta/generator skill, not needed in a subject-specific agent.
- No `.vscode`, no `.git`, no `.code-workspace` — matches the plain-folder pattern of agent 1.
- Report back to the user: confirm the folder path and that it's ready to be opened as its own VSCode window.
