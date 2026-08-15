# PHYS 50 (SJSU – General Physics I: Mechanics) Study Agent Report

## 1. Subject Overview

- PHYS 50 is SJSU's **General Physics I: Mechanics** — the first semester of calculus-based University Physics for science and engineering majors.
- Prerequisite: MATH 30/30P; strong familiarity with algebra, trigonometry, geometry, and calculus is essential.
- Includes mandatory lab and workshop components alongside lecture.
- Primary textbook: *University Physics* by Young & Freedman (Addison-Wesley). Secondary references some instructors use: *Physics* by Halliday & Resnick, and Feynman's *Lectures on Physics*.
- Grading (typical, varies by instructor): homework ~10%, quizzes ~10%, lab (pass/fail requirement), 2 midterms ~25% each, final ~30%. Online homework commonly via Mastering Physics.

## 2. Key Topics & Standard Structure

**Unit 1 — Foundations**
- Historical context (pre-Newtonian physics), Galileo
- Units and measurement
- Vector algebra, right-hand coordinate systems

**Unit 2 — Kinematics**
- Equations of motion (constant acceleration)
- Free fall
- Projectile motion
- Relative velocity

**Unit 3 — Dynamics & Forces**
- Newton's three laws of motion
- Normal force, friction
- Circular motion, centripetal/centrifugal force

**Unit 4 — Energy & Momentum**
- Kinetic energy, work-energy theorem
- Potential energy, conservation of energy
- Impulse, conservation of momentum
- Elastic and inelastic collisions

**Unit 5 — Rotational Motion**
- Moment of inertia
- Rotational kinetic energy
- Torque
- Center of mass, mechanical equilibrium

**Unit 6 — Waves & Sound**
- Wave properties, transverse waves
- Sound, Doppler effect, shock waves
- Interference, resonance, harmonics
- Applied examples: guitar strings, air pipes/musical instruments

**Unit 7 — Fluid Mechanics**
- Pressure, Archimedes' principle, buoyancy
- Bernoulli's equation, fluid dynamics
- Applications: airplane lift, sailboats

## 3. Core Equations/Concepts

*Equations are written in LaTeX — open this file in VS Code's Markdown Preview (Ctrl+Shift+V) to render them.*

PHYS 50 is calculus-based, so most "algebra" formulas below are actually special cases (constant acceleration, constant force) of an underlying calculus definition. The calculus form is what lets you handle variable acceleration/force problems and is the basis for derivation questions.

**Kinematics**
- Fundamental definitions (calculus): $v(t) = \dfrac{dx}{dt}$, $a(t) = \dfrac{dv}{dt}$ — velocity is the derivative of position, acceleration the derivative of velocity
- Constant-acceleration case (algebra, derived by integrating $a(t) = \text{const}$): $v = v_0 + at$; $x = x_0 + v_0 t + \tfrac{1}{2}at^2$; $v^2 = v_0^2 + 2a(x-x_0)$

**Dynamics**
- **Newton's Second Law:** $\Sigma F = ma$, or more generally $\Sigma F = \dfrac{dp}{dt}$ (needed when mass varies, e.g. rockets)
- **Friction:** $f \leq \mu N$
- **Centripetal acceleration:** $a_c = \dfrac{v^2}{r}$

**Energy & Momentum**
- **Work (general, variable force):** $\displaystyle W = \int F(x)\,dx$ — reduces to $W = Fd$ only when $F$ is constant
- **Work-Energy Theorem:** $W_{net} = \Delta KE = \tfrac{1}{2}mv^2 - \tfrac{1}{2}mv_0^2$
- **Conservation of Energy:** $KE_1 + PE_1 = KE_2 + PE_2$ (no non-conservative work)
- **Impulse-Momentum Theorem:** $\displaystyle J = \int F\,dt = \Delta p$ — reduces to $J = F\Delta t$ only when $F$ is constant
- **Conservation of Momentum:** $\Sigma p_{before} = \Sigma p_{after}$

**Rotational Motion**
- **Center of mass (continuous body):** $\displaystyle x_{cm} = \frac{1}{M}\int x\,dm$
- **Moment of inertia (continuous body):** $\displaystyle I = \int r^2\,dm$ — this is why different shapes (rod, disk, sphere) have different $I$ formulas
- **Torque:** $\vec{\tau} = \vec{r} \times \vec{F}$
- **Rotational analog of Newton's 2nd law:** $\tau_{net} = I\alpha$, or more generally $\tau_{net} = \dfrac{dL}{dt}$
- **Rotational kinetic energy:** $KE_{rot} = \tfrac{1}{2}I\omega^2$

**Waves, Sound & Fluids**
- **Wave speed:** $v = f\lambda$
- **Doppler effect:** $\displaystyle f_{observed} = f_{source}\cdot\frac{v \pm v_{observer}}{v \mp v_{source}}$
- **Archimedes' Principle:** $F_{buoyant} = \rho_{fluid} V_{displaced}\, g$
- **Bernoulli's Equation:** $P + \tfrac{1}{2}\rho v^2 + \rho g h = \text{constant}$ (derivable from the work-energy theorem applied to a fluid element)

## 4. Recommended Agent Capabilities

Tied to your intended uses — homework/problem-solving, concept explanation, exam prep, and equation derivation:

- **Step-by-step problem walkthroughs**: given a mechanics problem, identify the relevant conservation law or Newton's-law setup, draw out the free-body-diagram logic in words, then solve step by step.
- **Jargon-free concept explainer**: explain "why" behind concepts (e.g., why momentum is conserved but kinetic energy isn't in inelastic collisions) before formalizing with equations.
- **Derivation walkthroughs**: derive key formulas (e.g., work-energy theorem from Newton's 2nd law, rotational KE from summing particle KEs) since this was explicitly requested.
- **Unit/vector sanity-checking**: catch common first-semester-physics mistakes — unit mismatches, sign errors on vector components, mixing up radians/degrees.
- **Practice problem generator**: produce practice sets by unit (e.g., "5 rotational equilibrium problems") with answer keys.
- **Exam review mode**: summarize a unit's key formulas and quiz the student on when to apply which one.

## 5. Agent Design Notes

- **Persona/tone**: patient tutor — build physical intuition first (what's happening physically), then introduce the equation, not the reverse.
- **Example prompts** the agent should handle well:
  - "Derive the work-energy theorem from F = ma."
  - "Why does angular momentum matter here if we're not using it explicitly?"
  - "Check my free-body diagram for this inclined-plane friction problem."
  - "Give me 3 practice problems on elastic collisions with worked solutions."
- **Context the agent needs**: current unit/topic, whether the student wants a full derivation or just the applied formula, and awareness that labs/workshops may introduce problems not in the main lecture sequence.

## 6. Key Takeaways & Recommended Next Steps

- PHYS 50 has 7 core units, following a fairly standard intro mechanics sequence: kinematics → dynamics → energy/momentum → rotation → waves/sound → fluids.
- Course maps to *University Physics* (Young & Freedman) but exact chapter numbers weren't confirmed for a specific edition/instructor — worth checking your syllabus.
- Next steps:
  - Confirm with your specific professor which edition of Young & Freedman is used, and whether Halliday & Resnick supplements are required or optional.
  - Since equation derivation was one of your priorities, prioritize building the "derivation walkthroughs" capability early.
  - Revisit this report once labs/workshops start, since those often introduce applied problems (e.g., experimental error analysis) not captured here.

## 7. Sources

- [SJSU Catalog — PHYS 50 General Physics I: Mechanics](https://catalog.sjsu.edu/preview_course_nopop.php?catoid=10&coid=40939)
- [PHYS 50 — Green Sheet (R. Kwok, SJSU)](https://www.sjsu.edu/people/raymond.kwok/courses/physics/phys50/green/)
- [PHYS 50 — Topics (R. Kwok, SJSU)](https://www.sjsu.edu/people/raymond.kwok/courses/physics/phys50/topics/)
