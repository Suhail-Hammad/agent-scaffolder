# Agent Generator

An agent that turns a college course into a dedicated study-help agent. I made this because I wanted to have a course-specific personalized tutor for all my upcoming classes, instead of just opening a Claude chat over and over again.

You give it a course name. It interviews you about what you actually need, researches the course against your real syllabus, writes a structured report, waits for your approval, and then scaffolds a working sibling agent with that course's context already loaded.

Built in Claude Code.

## The problem

Setting up a useful AI tutor for a class takes longer than the tutoring saves. You have to explain the course, the textbook, the professor's grading scheme, and how you want to be taught, and you have to do it again for every class and again every time you open a new conversation.

The intelligence was never the bottleneck. The setup was. So I automated the setup.

## How it works

1. **Clarify.** Asks about scope (specific course or general subject), intended use, and coverage. If you share a syllabus, it asks permission before inferring what the agent should do from it, then proposes that inference back for confirmation.
2. **Plan.** Posts a short research outline before touching the web, so you can redirect early instead of after.
3. **Research.** Course structure, core concepts, standard textbooks. Every claim traced to a source.
4. **Report.** Writes a seven-section report to `output/`, covering topics, core equations, recommended agent capabilities, and design notes.
5. **Approve.** Stops. Nothing is created until you say the report is right.
6. **Scaffold.** Builds a sibling agent folder with a tailored `CLAUDE.md`, the approved report and your original course materials copied into `resources/`, and the shared problem-solving workflow copied into `workflows/`.

## Design decisions

**A hard approval gate.** The agent could scaffold immediately after research, It does not. Generation is cheap and wrong generation is expensive to notice later, so the report is the artifact you review, not the agent.

**Workflows are plain English, not code.** The skill file is deliberately thin. It points at a workflow file and instructs the agent not to improvise around it. Behavior lives in readable markdown recipes that I can edit, instead of being buried in strings.

**Context is inherited, not re-derived.** Each generated agent ships with the professor's own syllabus and grading rubric in its `resources/` folder. It's not working from a generic idea of what the course covers.

**Capabilities come from grading weights, not topic lists.** In the CAD course, exams are 60 percent of the grade and test drafting conventions rather than software mechanics, so the report prioritizes exam drilling over software walkthroughs. What matters is what is scored, not what is listed.

**Three problem-solving modes.** Full solution, guided walkthrough, or answer verification. One tutoring style was wrong for most sessions during my initial tests. The mode question is skipped if you already said what you want, and you can switch mid-problem without restarting.

**LaTeX in files, plain notation in chat.** VS Code's Markdown Preview renders LaTeX. The chat panel does not, so it shows up as clutter. Saved reports use LaTeX, live conversation uses readable notation like `dv/dt`. Small rule, large difference in daily use.

## Repository structure

```
.claude/skills/new-subject-agent/   Entry point, delegates to the workflow
workflows/                          Plain-English recipes the agent follows
output/                             Generated course reports
resources/                          Templates and reference material
CLAUDE.md                           Workspace context and rules
```

## Example output

Three reports are included in `output/`, generated for some courses in my first-semester schedule:

- `ae-20-agent-report.md` (Computer-Aided Design)
- `math-31-agent-report.md` (Calculus II)
- `phys-50-agent-report.md` (Mechanics)

The CAD report is the best example of syllabus-aligned output, It's written against the actual course rubric rather than a generic CAD curriculum. Course materials themselves are not committed here, since they are the instructors' work and contain personal contact information.

## Status and known limitations

I built it (him?) over roughly a month before my first semester. The generated agents have not yet been tested against live coursework, and I am the only user.

Three things I know are wrong:

**Inheritance is by copy, not by reference.** The shared problem-solving workflow is duplicated into every generated agent. Fixing one bug means fixing it N times, and an updated report cannot be pushed to an agent that already exists. This is the next thing I am changing.

**No evaluation.** I have no measurement of whether a generated agent is actually good, only whether it runs. A small set of past problems scored against expected output would tell me something real.

**Untested breadth.** Three courses is not enough to know whether the workflow generalizes to lab-heavy, project-based, or writing-based classes. The CAD case already stretched it, since that course is convention-based rather than derivation-based.

## Stack

Claude Code, VS Code, markdown. No framework, deliberately.