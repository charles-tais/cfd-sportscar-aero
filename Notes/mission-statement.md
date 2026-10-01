
Mission statement - cfd-sportscar-aero

# Mission Statement - vehicle aerodynamics CFD study

#### Project 1 - Sportscar Aerodynamics & CFD

|          |            |
|:---------|:----------:|
|**Author**|Charles Tais|
|**Date**  |2026-10-01 |
|**Version**|0.2 (draft)|
|**Repository**|cfd-sportscar-aero (GitHub)|

## Version history

|**Version**|**Date**|**Author**|**Changes**|
|:---|:---|:----|:-----|
|0.1|2026-09-30|Charles Tais|Creation of the first draft (objectives, criteria, schedules)|
|0.2|2026-10-01|Charles Tais|Restructured in industry format: requirements table with MoSCoW priorities, risk register, fallback scope, subsections 2.1/3.1, REQ-11 video deliverable, week 8 / MS-6, risk 5.|

## 1. Context and objectives

This project is the first entry of my engineering portfolio targeting internships in the automotive and aeronautical industries. It demonstrates the ability to plan, run, validate and document a CFD study of road-vehicle aerodynamics.

**Objectives:** quantify the effect of two aerodynamic devices — a rear wing and a diffuser — on the drag coefficient (Cd), lift/downforce coefficient (Cl), and drag area (CdA) of a road-vehicle body, in steady-state conditions.

## 2. Scope

|**In Scope**|**Out of Scope**|
|:------|:------|
|External steady-state aerodynamics of a car body|Moving parts (wheels rotation, moving ground)|
|3 configurations vs baseline, at 3 road speeds|Engine, thermal and electrical systems|
|Mesh independence study and validation vs published data|Transient phenomena (overtaking, gusts, aeroelasticity)|
|Full documentation of method and results|Interior flow, HVAC, cooling flows|

### 2.1 Configurations under study:

|**ID**|**Configuration**|
|:----:|:----------------|
|A|Baseline body (no rear wing, no diffuser)|
|B|Baseline + rear wing|
|C|Baseline + diffuser|
|D|Baseline + rear wing + diffuser (optional, stretch goal)|

**Test matrix:** configurations A, B, C (and D if time allows) at 80, 120 and 160 km/h

## 3. Requirements

|**ID**|**Requirement**|**Priority**|**Acceptance criterion**|
|:-:|:---|:---|:---|
|REQ-01|Run steady-state incompressible RANS simulations with the k-omega SST turbulence model|Must|Simulation converges; force coefficients stable over the last 500 iterations|
|REQ-02|Perform a mesh independence study on configuration A at 120 km/h|Must|Cd and Cl vary by less than 5% between the medium and fine meshes (Approx. 1M / 3M / 8M cells)|
|REQ-03|Validate the simulation chain against published reference data|Must|Simulated Cd of the reference case within 5% of the published experimental value|
|REQ-04|Compare each configuration against the baseline|Must|Cd, Cl, CdA reported for every configuration and speed, each with an uncertainty estimate|
|REQ-05|Report only conclusions that exceed the estimated uncertainty|Must|Every stated difference between configurations is larger than the mesh-study uncertainty|
|REQ-06|Deliver a full PDF report (15—25 pages)|Must|Report covers context, method, theory, results, limitations and conclusions|
|REQ-07|Deliver scripts and simulation setups in the repository|Must|A third party can reproduce the results by following the README|
|REQ-08|Provide the meshes used|Should|Meshes available on request; generation settings stored in the repository|
|REQ-09|Study configuration D|Could|Same acceptance criteria as REQ-04|
|REQ-10|Publish a summary on LinkedIn and the portfolio page|Should|Publication online before 2026-11-15|
|REQ-11|Publish a YouTube video summarizing the project|Could|Video published online before 2026-11-22|

### 3.1 Fallback scope (descope plan):
if the schedule slips, remove items in this order - (1) 80 km/h runs, (2) configuration D, (3) 160 km/h runs. The validation case and the mesh study are never descoped. 

## 4. Deliverables

|**#**|**Deliverable**|**Format**|
|:-:|:---|:----|
|1|Project report|PDF, 15—25 pages, English|
|2|Simulations setups and analysis scripts|GitHub repository (/simulations, /scripts)|
|3|Results summary|CSV in the repository (/results)|
|4|Meshes|On request (files too large for the repository)|
|5|Portfolio page and LinkedIn post|Online|

## 5. Validation and quality plan

1. **Verification (mesh study):** 3 mesh levels on configuration A at 120 km/h; validated if the results differ by less than 5% between the different meshes (REQ-02). This value establishes the uncertainty band used everywhere else. 

2. **Validation (benchmark):** Before the main campaign, reproduce the Cd of a published reference case (Ahmed body, slant angle 25°, Cd ≈ 0.30) within 5%.

3. **Significance rule (REQ-05):** A difference between two configurations is only reported as an effect if it exceeds the uncertainty band from step 1.

4. **Documentation:** Journal updated weekly; every result figure stored with date and case ID.

## 6. Schedule and milestones

**Time budget:** 4 h/week (two 1.5 hours work block + one 1 hour documentation block)

|**Week**|**Dates**|**Work package**|**Milestone**|
|:-:|:-:|:--|:--|
|1|2026-10-01 -> 2026-10-07|Tooling (Git/GitHub, SimScale), geometry selection, detailed plan, report template|**MS-1 –** geometry and plan frozen|
|2-3|2026-10-08 -> 2026-10-23|Validation case (Ahmed body) + mesh independence study|**MS-2 –** validation and uncertainty band established|
|4-5|2026-10-24 -> 2026-11-09|Simulation campaign: configurations A/B/C(/D) at 3 speeds|**MS-3 –** all runs complete|
|6|2026-11-09 -> 2026-11-15|Report writing (documented continuously, assembled here)|**MS-4 –** report published|
|7|2026-11-12 -> 2026-11-15|Portfolio page, LinkedIn post|**MS-5 –** project public|
|8|2026-11-15 -> 2026-11-22|YouTube video|**MS-6 –** video uploaded|

## 7. Resources and budget

|**Resource**|**Cost**|
|:-----------|:------:|
|SimScale (student plan) or OpenFOAM|0 R$|
|CAD tools (Fusion360 / Onshape student licence)|0 R$|
|Compute|Cloud (SimScale included)|
|Miscellaneous (export, printing)|≤ 100 R$|
|**Total**|**≤ 100 R$**|

## 8. Risk register

|**#**|**Risk**|**Impact**|**Mitigation**|
|:-:|:---|:---|:---|
|1|SimScale student account compute limits|Campaign delayed|Batch runs early; descope plan (section 3.1)|
|2|Learning curve on tooling (week 1 underestimated)|MS-2 delayed|Fallback: shift one campaign speed; keep validation case|
|3|Geometry licence issues|Restart geometry|Prefer open models (Ahmed body, DrivAer) with published data|
|4|Mesh failures on complex geometry|Lost time|Simplify geometry (remove small features, mirror symmetry plane)|
|5|Lack of computational power|Fall out of budget|Use a university computer|

## 9. Glossary

- **Cd** – drag coefficient (dimensionless)

- **Cl** – lift coefficient (negative Cl = downforce)

- **CdA** – drag area (Cd x frontal area, m^2)

- **RANS / k-omega SST** – steady-state turbulence modeling approach recommended for external aerodynamics

- **Mesh independence** – results no longer change significantly when the mesh is refined

