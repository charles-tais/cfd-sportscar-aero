# Project Journal — cfd-sportscar-aero

Append-only work log. One entry per work session, newest first, dated ISO 8601.  
Past entries are never edited or deleted — mistakes are part of the record.

Copy the template below for each new session:

```
## YYYY-MM-DD — <short session title>

**Done**
-

**Decisions**
-

**Issues & learnings**
-

**Next**
-

---
```
## 2026-10-06 — SimScale Tutorial

**Done**
- I finished my first ever CFD simulation in my entire life
- the results I obtained:
    - Cd $\approx 0.41$ 
    - Cl $\approx -0.33$
    - convergence: residuals down to $10^{-4} - 10^{-5}$, Cd and Cl plateau over the last iterations (REQ-01 criterion)
- Mesh generated: 6.8 M cells
- Run: 33min, 35.08 core hours
- Restructured the project files

**Decisions**
- I didn't have to take any decisions for the tutorial, I only followed what the SimScale documentation was saying
- After the tutorial, I didn't know where to archive the screenshots and tutorial results. I took the decision to create a more structured, precise file system

**Issues & learnings**
- How to set-up and select the analysis type of the simulation
    - CAD refinings
    - create saved selections
- Set up the simulation
    - Select the material
    - Assign boundary conditions
    - Set up the simulation controls
    - Set up the result controls
- Mesh configurations
    - Base meshing configuration
    - Addition of a Far field and Close field to refine the meshing
    - Refining of the mesh on the surface of the wheels
- Post processing
    - how to visualize pressure around the car
    - how to visualize turbulent kinetic energy around the car
    - how to visualize velocity magnitude of air around the car
    - how to visualize the velocity magnitude in the form of a particle trace
    - first interactions with cutting planes
    - Reducing the scale gives a better visualization and finer results

**Next**
- Taking the decision for the body geometry I'm going to use along this project

---

## 2026-10-01 — Project setup, mission statement v0.2, SimScale

**Done**

- Restructured the mission statement into industry format (v0.2): added the version history, context and objectives, scope, requirements (REQ-01 -> REQ-11), fallback scope, deliverables, validation and quality plan, restructured the planning and added important milestones to it, resources and budget, risk register and the glossary at the end.
- Applied a full proofreading pass; committed and pushed the first version of the document
- Created a SimScale account with the university email; applied to the Academic Program, and got accepted

**Decisions**

- Version stays 0.2 (no bump to 0.3): the previous state was never committed, so the history line now describes the full delta from 0.1
- Plain-text symbols (Cd, Cl, CdA) chosen over LaTeX for consistency across the document
- University email used for SimScale to be eligible for the Academic Plan verification

**Issues &amp; learnings**

- Proofreading my own text is harder than writing it
- Adopted Conventional Commits from day one (`docs:`, `feat:`, `fix:`)

**Next**

- Run the SimScale vehicle aerodynamics tutorial while the Academic request is pending
- Compare Ahmed body vs. DrivAer and freeze the geometry — MS-1, due 2026-10-07
- Detail the week 2–3 plan into the kanban

---

## 2026-09-30 — Mission statement first draft

**Done**

- Wrote the first draft of the mission statement (v0.1): objectives, success criteria, schedule, time budget
- Created GitHub repository `cfd-sportscar-aero`, cloned locally, set up VS Code with `.gitignore`

**Decisions**

- Objective fixed at 3 configurations × 3 speeds, drag and downforce as measured quantities
- Took the decision to alocate 4 hours per week of work for this project, and the did a first draft of the planning knowing the time budget

**Issues &amp; learnings**

- I had troubles deciding what and what not to do during this project. I learned about the In scope vs. Out of scope table and the importance of it to avoid getting stuck in a never ending project

**Next**

- Restructure the draft into an industry-friendly format