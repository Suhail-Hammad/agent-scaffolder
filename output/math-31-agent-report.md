# MATH 31 (SJSU – Calculus II) Study Agent Report

## 1. Subject Overview

- MATH 31 is SJSU's **Calculus II** course (4 units).
- Prerequisite: MATH 30 or 30P with a grade of C- or better.
- Focus: integral calculus techniques and applications, plus infinite sequences/series and their use in representing functions.
- Standard textbook: *Calculus: Early Transcendentals* by James Stewart (7th/8th ed.) — chapters 5–8 and 11, plus Appendix H.
- Total instructional time: ~60 hours across 5 major units.

## 2. Key Topics & Standard Structure

**Unit 1 — Integration Fundamentals** (Ch. 5, ~10 hrs)
- Definite and indefinite integrals
- The Fundamental Theorem of Calculus
- Integration by substitution

**Unit 2 — Applications of Integration** (Ch. 6, ~8 hrs)
- Area between curves
- Volumes (disk/washer and cylindrical shell methods)
- Work problems

**Unit 3 — Integration Techniques** (Ch. 7, ~10 hrs)
- Integration by parts
- Trigonometric integrals and trigonometric substitution
- Partial fractions
- Approximate (numerical) integration
- Improper integrals

**Unit 4 — More Applications** (Ch. 8, ~6 hrs)
- Arc length
- Surface area of revolution
- Physics/engineering applications

**Unit 5 — Sequences & Series** (Ch. 11, ~18 hrs — largest unit)
- Sequences and convergence
- Series convergence tests (comparison, ratio, root, integral, alternating series)
- Power series
- Taylor and Maclaurin series

**Supplementary — Complex Numbers** (Appendix H, ~2 hrs)

## 3. Core Equations/Concepts

*Equations are written in LaTeX — open this file in VS Code's Markdown Preview (Ctrl+Shift+V) to render them.*

- **Fundamental Theorem of Calculus:** $\displaystyle\int_a^b f(x)\,dx = F(b) - F(a)$, where $F'(x) = f(x)$
- **u-substitution:** $\displaystyle\int f(g(x))g'(x)\,dx = \int f(u)\,du$
- **Integration by parts:** $\displaystyle\int u\,dv = uv - \int v\,du$
- **Disk/washer volume:** $\displaystyle V = \pi \int_a^b \left[R(x)^2 - r(x)^2\right] dx$
- **Shell method volume:** $\displaystyle V = 2\pi \int_a^b x\,f(x)\,dx$
- **Arc length:** $\displaystyle L = \int_a^b \sqrt{1 + [f'(x)]^2}\,dx$
- **Geometric series:** $\displaystyle\sum_{n=0}^\infty ar^n = \frac{a}{1-r}$ for $|r| < 1$
- **Taylor series:** $\displaystyle f(x) = \sum_{n=0}^\infty \frac{f^{(n)}(a)}{n!}(x-a)^n$
- **Convergence tests:** ratio test, root test, integral test, comparison test, alternating series test

## 4. Recommended Agent Capabilities

Tied to your intended uses — homework/problem-solving, concept explanation, and exam prep:

- **Step-by-step problem walkthroughs**: given an integral or series problem, show the method choice (why substitution vs. parts vs. partial fractions) and each algebraic step.
- **Jargon-free concept explainer**: explain "why" behind convergence tests, FTC, etc. in plain language before formalizing notation.
- **Method selector**: help decide which integration technique or convergence test applies to a given problem (a common Calc II pain point).
- **Practice problem generator**: produce practice sets by unit (e.g., "5 partial fractions problems") with answer keys.
- **Exam review mode**: summarize a chapter's key formulas/theorems and quiz the student on them.
- **Error-checking**: given a student's worked solution, identify the step where an error occurred rather than just giving the right answer.

## 5. Agent Design Notes

- **Persona/tone**: patient tutor, not a solution dispenser — nudge toward the method before revealing full steps; avoid unnecessary formal notation until the student is comfortable.
- **Example prompts** the agent should handle well:
  - "Walk me through why I'd use partial fractions here instead of trig substitution."
  - "Explain the ratio test like I've never seen infinite series before."
  - "Check my work on this arc length problem — where did I go wrong?"
  - "Give me 3 practice problems on Taylor series with solutions."
- **Context the agent needs**: current unit/chapter the student is on, which textbook edition (Stewart 7th/8th differ slightly in numbering), and whether they want full derivations or shortcuts.

## 6. Key Takeaways & Recommended Next Steps

- MATH 31 has 5 core units; **Sequences & Series (Ch. 11) is the largest and typically hardest** — worth extra agent emphasis.
- Course structure maps directly onto Stewart's *Calculus: Early Transcendentals*, chapters 5–8 and 11.
- Next steps:
  - Confirm with your specific professor whether they use 7th or 8th edition Stewart (section numbers can shift slightly).
  - Build the agent starting with the "method selector" and "step-by-step walkthrough" capabilities first, since those map to your top two intended uses.
  - Revisit this report once you're mid-semester to add student-pain-point notes (e.g., series convergence tests are commonly the hardest topic) if you want the agent tuned further.

## 7. Sources

- [SJSU Catalog — MATH 31 Calculus II](https://catalog.sjsu.edu/preview_course_nopop.php?catoid=10&coid=41229)
- [SJSU Department of Mathematics — MATH 031 official course outline](https://www.sjsu.edu/math/docs/math031.doc)
- [Spring 2015 MATH 31 Syllabus (M. Vartanian, SJSU)](https://www.sjsu.edu/people/michael.vartanian/courses/math31_S15/Syllabus_M31_S15.pdf)
