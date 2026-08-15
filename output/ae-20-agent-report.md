# AE 20 – Computer-Aided Design for Aerospace Engineers — Subject Report

**Scope note:** Aligned to the actual Fall 2025/2026 SJSU syllabus (Instructor:) and assigned textbook, not a generic CAD course.

## 1. Subject Overview

- AE 20 is a 2-unit, letter-graded intro course: 1 hr lecture + 3 hr lab per week.
- Software: Autodesk Inventor Pro (2027 version), Windows-only — a Windows PC is required for work outside lab.
- Course pairs two skill tracks: (a) **print reading / technical drafting conventions** (from the textbook) and (b) **hands-on 3D CAD modeling** (in lab, graded via file-based rubrics).
- Grading: Homework + Labs + Quizzes 30%, Project + Presentation 10%, Midterm Exams 30%, Final Exam 30% — exams are 60% of the grade, and by the CLOs/rubrics they test drafting conventions and print-reading more than software mechanics.

## 2. Key Topics & Standard Structure

Matches the syllabus's approximate weekly schedule, cross-referenced to the textbook's chapter structure.

- **Weekly progression (syllabus):**
  - Introduction to CAD
  - Creating sketches
  - Creating parts (2 weeks)
  - Creating features (2 weeks)
  - Basic drafting standards (2 weeks)
  - Creating drawings (2 weeks)
  - Creating assemblies (2 weeks)
  - Creating exploded views
  - Advanced sketching, constraining, and modeling techniques (2 weeks)
  - Final project due
- **Textbook structure** (*Print Reading for Industry*, 12th ed., Brown & Brown): Prints as the language of industry; line conventions & lettering; title blocks & parts lists; geometric terms & construction; multiview drawings; section views; auxiliary views; screw thread representation; dimensioning; tolerancing; machining specs/drawing notes; surface texture symbols; GD&T; drawing revision systems; detail drawings; assembly drawings; fasteners/springs; gears/splines; cams; plastic/sheet-metal parts; welding prints; instruction/control drawings — plus appendices on applied math, measurement tools, and pictorial sketching.
- **Where they overlap** (this is the practical core of the course):
  - Sketching → multiview drawings, geometric construction
  - Parts/features → dimensioning, tolerancing, GD&T, screw threads
  - Drawings → title blocks, line conventions, detail drawings, drafting standards
  - Assemblies/exploded views → assembly drawings, BOM/balloon conventions

## 3. Core Equations/Concepts

*Note: write this section's math using LaTeX (`$...$` inline, `$$...$$` display) — VS Code's Markdown Preview (Ctrl+Shift+V) renders it, plain chat does not.*

This course is mostly **convention-based** (drafting rules, standards, terminology), not derivation-heavy. The few quantitative rules worth formalizing:

- **Limit dimensioning** — upper and lower bounds on an acceptable size:
$$D_{max} = D_{nominal} + T^{+}, \quad D_{min} = D_{nominal} - T^{-}$$
- **Bilateral tolerance** — variation allowed in both directions from nominal:
$$D = D_{nominal} \pm T$$
- **Unilateral tolerance** — variation allowed in only one direction:
$$D = D_{nominal}{}^{+T}_{\;\,0} \quad \text{or} \quad D = D_{nominal}{}^{\;\,0}_{-T}$$
- **Drawing scale ratio** — drawn size vs. real size:
$$\text{Scale} = \frac{\text{Drawing size}}{\text{Actual size}} \quad (\text{e.g. } 1:2 \text{ or } 2:1)$$
- **Isometric axis geometry** — the three isometric axes are spaced $120^\circ$ apart, which is why isometric sketches use a consistent 30° angle off horizontal for the two receding axes.
- **Projection conventions (not an equation, but a fixed rule to memorize):** in third-angle projection (US standard), the top view is placed above the front view and the right-side view to the right; first-angle projection (common outside the US) places them oppositely.

## 4. Recommended Agent Capabilities

Tied to the confirmed intended use: homework/lab support, concept explanation, and exam prep (exams = 60% of grade).

- **Print-reading / homework helper** — given a described or uploaded view set, help identify/derive the missing view, check dimensioning placement, or explain why a dimension/tolerance is written a certain way.
- **CAD workflow coach** — walk through the sketch → part → feature → drawing → assembly → exploded-view pipeline conceptually (not a substitute for Inventor itself), explaining *why* a step is done (e.g., why constrain a sketch fully before extruding).
- **Concept/terminology explainer** — plain-language explanations of drafting terms (auxiliary view, section view, GD&T callouts, screw thread notation) tied back to the textbook's chapter structure.
- **Exam prep drills** — practice questions on view identification, dimensioning/tolerancing rules, and drafting standards, since exams weight is high and lab rubrics already cover hands-on file grading.
- **Lab rubric self-check** — help the student sanity-check a model/drawing/assembly/exploded-view file against the syllabus's own grading rubric criteria (e.g., "sketches turned off," "iProperties filled out," "parts constrained properly") before submission.

## 5. Agent Design Notes

- **Persona/tone:** patient drafting-lab tutor — plain-language, jargon explained on first use, visual/spatial descriptions (since this subject is inherently visual) rather than dense text.
- **Nudge-before-revealing style** applies in Walkthrough mode specifically (see `workflows/problem-solving-mode.md` in the new agent) — which mode applies to a given problem is decided there, not assumed by default.
- **Example prompts this agent should handle well:**
  - "Here's a part sketch — what view am I missing?"
  - "Why does this hole need a tolerance callout instead of just a dimension?"
  - "Walk me through building this bracket: sketch, extrude, then a fillet."
  - "Quiz me on first-angle vs third-angle projection before the midterm."
- **Context the agent would need:** the syllabus/CLOs (already captured here), the textbook's chapter list (for terminology alignment), and ideally the specific lab assignment prompt or rubric row the student is working against, since grading is file/rubric-based rather than numeric-answer-based.

## 6. Key Takeaways & Recommended Next Steps

- AE 20 is a drafting-standards-and-CAD-workflow course, not a math/derivation course — the agent should prioritize visual/conceptual clarity over equation manipulation.
- Exams carry 60% of the grade and (per CLOs) test print-reading/drafting knowledge — exam-prep drilling on view types, dimensioning, and tolerancing is high-value.
- Labs are graded by rubric against specific file criteria — a "check my work against the rubric" capability is worth building early.
- Next steps: approve this report, then scaffold the sibling AE 20 agent (Step G) with this report copied into its `resources/` folder for ongoing reference.

## 7. Sources

- AE 20 Fall 2025 Syllabus (Concourse), provided by user
- [Print Reading for Industry, 12th Edition – Goodheart-Willcox](https://www.g-w.com/print-reading-for-industry-2026)
- [Print Reading for Industry 12th Edition Write-In Text (sample front matter/TOC)](https://www.g-w.com/assets/files/pdf/sampchap/9798891188181_fm.pdf)
- [First vs Third Angle – Orthographic Views | GD&T Basics](https://www.gdandtbasics.com/first-vs-third-angle-orthographic-views/)
- [Types of Projection in Engineering Drawing Explained](https://karpagamtech.ac.in/types-of-projection-in-engineering-drawing/)
- [ASME Y14.5-2018: GD&T Dimensioning & Tolerancing Guide](https://enggtools.in/standards/asme-y-14-5)
- [Formatting Tolerances – Engineering Essentials](http://engineeringessentials.com/ege5/files/ege/tol/tol_page9.htm)
- [Constrain assembly components in Inventor – Autodesk](https://www.autodesk.com/learn/ondemand/tutorial/constrain-assembly-components-in-inventor)
- [Inventor 2026 Help | To Create Extruded Features – Autodesk](https://help.autodesk.com/view/INVNTOR/2026/ENU/?guid=GUID-B0CFA8E7-D3F5-48A9-BE6F-C8DF668301BD)
- [SOLIDWORKS Drawings – Ballooning Exploded Views (general assembly-drawing/BOM convention reference)](https://www.cati.com/blog/solidworks-drawings-ballooning-exploded-views/)
