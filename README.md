# Automotive Steering Knuckle — Parametric Design, FEA & AI-Driven Optimisation

**Author:** Haripriya B | Mechanical Engineering, SSN College of Engineering  
**Tools:** PTC Creo Parametric · ANSYS Mechanical · Python · scikit-learn · Streamlit  

---

## Project Overview
Parametric design, multi-load structural FEA, topology optimisation, 
fatigue life analysis, and GD&T manufacturing documentation of a 
front steering knuckle for a 1,400 kg double wishbone suspension platform —
with an AI/ML surrogate model for rapid stress prediction across geometry 
variations, replacing repeated FEA runs.

Designed to automotive OEM durability standards relevant to 
Caterpillar, Bosch, and BMW chassis engineering practice.

---

## Vehicle Platform & Load Cases

| Load Case | Force | Direction |
|-----------|-------|-----------|
| Bump (2.5g) | 10,300 N | Vertical |
| Braking (1.2g) | 4,945 N | Fore-aft |
| Cornering (1.5g) | 6,181 N | Lateral |
| Combined (worst-case) | 13,007 N | Resultant |

**Material:** Aluminium 7075-T6 (E = 71,700 MPa, σ_y = 503 MPa,  
σ_endurance = 159 MPa, ρ = 2.81e-9 tonne/mm³)  
**Baseline mass:** 0.839 kg  
**Design target:** Fatigue life ≥ 200,000 km (≈ 1.06 × 10⁸ cycles at 80 km/h)

---

## Mechanical Engineering Foundation

### Component Context
The steering knuckle is the structural hub of the wheel corner in a 
double wishbone suspension system. It simultaneously interfaces with:
- **Wheel hub bearing** — carries all wheel loads into the structure
- **Upper ball joint** — suspension geometry constraint (UBJ bore: 22mm)
- **Lower ball joint** — primary vertical load path (LBJ bore: 28mm)
- **Tie rod** — steering force input (bore: 16mm)
- **Brake caliper** — braking torque reaction (bolt: 12mm)

Every road load — bump, braking, cornering — enters the vehicle 
chassis through this component. It is one of the most 
structurally complex components in the suspension system.

### Parametric CAD Model
Built in PTC Creo Parametric with a 12-parameter design table:

| Parameter | Value | Controls |
|-----------|-------|----------|
| HUB_BORE_DIA | 60mm | Wheel bearing seat |
| HUB_BORE_DEPTH | 45mm | Bearing engagement depth |
| UBJ_BORE_DIA | 22mm | Upper ball joint pin |
| LBJ_BORE_DIA | 28mm | Lower ball joint pin |
| OVERALL_HEIGHT | 220mm | UBJ to LBJ centre distance |
| OVERALL_WIDTH | 140mm | Knuckle body width |
| WALL_THICKNESS | 8mm | Minimum structural wall |
| CALIPER_PCD | 90mm | Caliper bolt pitch circle |
| CALIPER_BOLT_DIA | 12mm | Caliper mounting bolt |
| TIEROD_BORE_DIA | 16mm | Tie rod end bore |
| FILLET_RADIUS_MAIN | 5mm | Boss base fillets |
| FILLET_RADIUS_BORE | 2mm | Bore entry fillets |

All geometry is driven by this parameter table — any design 
change propagates automatically through the entire model.

### FEA Methodology
Four independent load cases derived from vehicle dynamics 
first principles — not assumed or textbook-lifted:

- **Load case derivation:** vehicle mass × g-factor × axle distribution
- **Mesh sensitivity study:** 4 mesh densities, convergence confirmed 
  within 2% change between final two refinements
- **Hand-calculation validation:** beam theory estimate vs FEA 
  result — target agreement within 20%
- **Fatigue analysis:** S-N curve input for Al 7075-T6, 
  fully-reversed loading (R = -1), life in km at 80 km/h

### Material Selection Rationale
Aluminium 7075-T6 chosen over cast iron and mild steel because:
- Specific strength (σ_y/ρ) = 179 MPa·cm³/g vs 60 for cast iron
- Standard material for BMW, Mercedes, and Audi suspension components
- Enables meaningful mass reduction vs conventional materials
- Fatigue endurance limit (159 MPa) sufficient for target load cases

---

## AI/ML Integration — Core Project Layer

### 1. ML Surrogate Model (scikit-learn)
- ANSYS FEA run across 15–20 geometry variations 
  (wall thickness, fillet radius, boss diameter)
- Results used to train a Random Forest regression model
- Predicts peak Von Mises stress for any geometry input 
  in milliseconds — replacing a full FEA run
- Target accuracy: R² ≥ 0.92
- Validates University of Michigan AI for Engineers 
  (Coursera) methodology with a real engineering implementation

### 2. Automated Analysis Pipeline (Python)
- Python scripts read ANSYS result CSVs automatically
- Auto-generate mesh convergence plots, stress summaries, 
  and safety factor comparisons
- Eliminates manual post-processing — engineering workflow automation

### 3. Deployed Streamlit Tool
- Input: vehicle mass, load factors, safety factor requirement, 
  material selection
- Output: derived load cases, minimum wall thickness, 
  material comparison table, predicted stress via surrogate model
- Live deployed URL — accessible to any engineer, anywhere

---

## Deliverables

- [x] Creo parametric model — 12-parameter table, all interfaces
- [x] STEP export for ANSYS (baseline mass: 0.839 kg)
- [ ] Load case derivation — hand calculations documented
- [ ] ANSYS static FEA — 4 load cases + mesh sensitivity
- [ ] Fatigue analysis — 200,000 km life validation
- [ ] Topology optimisation + redesigned geometry
- [ ] ML surrogate model (R² target ≥ 0.92)
- [ ] Automated Python analysis pipeline
- [ ] Streamlit tool — live deployed URL
- [ ] GD&T drawing — 5 functional callouts with reasoning
- [ ] Engineering report — 12 pages, industry format

---

## Results

| Metric | Baseline | Optimised |
|--------|----------|-----------|
| Mass | 0.839 kg | TBD |
| Peak Von Mises stress | TBD | TBD |
| Min safety factor | TBD | TBD |
| Fatigue life | TBD | TBD |
| Surrogate model R² | TBD | — |

---

## Tools & Software

| Task | Tool |
|------|------|
| Parametric CAD | PTC Creo Parametric |
| Structural FEA | ANSYS Mechanical |
| Fatigue analysis | ANSYS Fatigue Tool |
| Topology optimisation | ANSYS |
| ML surrogate model | Python — scikit-learn, pandas, NumPy |
| Analysis automation | Python — matplotlib, CSV parsing |
| Web deployment | Streamlit |
| GD&T drawing | Creo Drawing |
| Version control | Git / GitHub |

---

## Daily Progress Log
See [daily_logs/](./daily_logs/) for day-by-day documentation 
of design decisions, iterations, and technical learnings.
