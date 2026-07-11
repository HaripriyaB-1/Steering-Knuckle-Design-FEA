# Automotive Steering Knuckle — Parametric Design, FEA & Optimisation

**Author:** Haripriya B | Mechanical Engineering, SSN College of Engineering  
**Tools:** CATIA V5 R21 · ANSYS Mechanical · Python · Streamlit  
**Status:**  In Progress — Week 1 of 7  
**Started:** [today's date]

---

## Project Overview
Parametric design, multi-load structural FEA, topology optimisation, 
fatigue life analysis, and GD&T manufacturing documentation of a 
front steering knuckle for a 1,400 kg double wishbone suspension platform.

Designed to meet BMW/Mercedes passenger car durability targets.

---

## Vehicle Platform & Load Cases
| Load Case | Force | Direction |
|-----------|-------|-----------|
|-----------|-------|-----------|
| Bump (2.5g) | 10,300 N | Vertical |
| Braking (1.2g) | 4,945 N | Fore-aft |
| Cornering (1.5g) | 6,181 N | Lateral |
| Combined (worst-case) | 13,007 N | Resultant |

**Material:** Aluminium 7075-T6 (σ_y = 503 MPa, σ_endurance = 159 MPa)  
**Design target:** Fatigue life ≥ 200,000 km (≈ 1.06 × 10⁸ cycles at 80 km/h)

---

## Deliverables
- [ ] CATIA V5 parametric model (.CATPart + STEP)
- [ ] Load case derivation document
- [ ] ANSYS static FEA — 4 load cases + mesh sensitivity study
- [ ] Fatigue analysis — design life validation
- [ ] Topology optimisation + redesigned geometry
- [ ] GD&T engineering drawing (5 functional callouts)
- [ ] ML surrogate model + Streamlit tool
- [ ] Full engineering report (12 pages)

## Results (updated weekly)
*To be populated as analysis progresses*

---

## Daily Progress Log
See [daily_logs/](./daily_logs/) for detailed day-by-day documentation.
