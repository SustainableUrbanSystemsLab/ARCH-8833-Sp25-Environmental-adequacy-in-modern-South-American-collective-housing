# datadrivedmethods
Materials developed for Patrick Kastner's course on data-driven methods for sustainable architecture (GeorgiaTech)

File locations:
1 - Spreadsheet with results can be found in the repository's main branch (00 - DAYLIGHT ANALYSIS).
2 - Rhinocero models and ClimateStudio analysis files can be found in the link below (they were not uploaded due to GitHub's storage limitations):
https://1drv.ms/f/c/7f0cd2b9d40f94b7/EnBedykBQtJKjMMBs4RBCX4BkkNnjPTw4YFlKYOVU3Auyg?e=cwm2uE

Required software for running experiment:
Rhinoceros 8, ClimateStudio.

Times chosen for analysis:
1. 09:00 AM
2. 15:00 PM

Dates chosen for analysis:
1. 21 June (Winter solstice)
2. 22 September (Equinox)
3. 21 December (Summer solstice)

Modeling generalizations:
1. Simple walls were modeled with a thickness of 18 centimeters and double or reinforced walls were modeled
with 25 centimeters.
2. Windows were considered to have 120 centimeters of height and a sill height of 105 centimeters.
3. Slabs were considered 15 centimeters thick.
4. Glazing was modeled without thickness.
5. Brise-soleil were modeled using a grasshopper component (appendix A)
6. Musharabya were modeled using a grasshopper component (appendix B)
7. Simulations considered all doors open.
8. Simulations accounted for all floorplate area discounted walls.

Grasshoppper definitions for generating standardized musharabya and brise-soleil are also attached.

Materials used:
1. Matte White Wall
2. Wood Floor
3. Clear-clear glazing
4. Dupont Clay

Ground albedo setting: 0,2

# ☀️ Daylight Analysis in South American Modern Housing (1950–1954)

Welcome to the official repository for the study **“Environmental adequacy in modern South American collective housing: comparative analysis of daylight in six projects (1950–1954)”** by João Navarrete de Almeida. The material was developed for Patrick Kastner's course on Data Driven Methods for Sustainable Architecture at GeorgiaTech. This repository contains all the data, simulation tools, and analysis scripts needed to **replicate or extend** the pilot daylighting study of six modernist housing projects in Rio de Janeiro and Caracas.

## 🏗️ Project Description

This project examines claims made by the 1955 MoMA exhibition *Latin American Architecture Since 1945*, which argued that regional modernism incorporated effective environmental controls. Using computational daylight simulations, this study evaluates **six tropical housing projects** to test those claims empirically.

![Diagram of Study Workflow](images/workflow_diagram.png) <!-- Add your diagram -->

---

## 🧪 Methodology

### 1. 📚 Literature Review
A preliminary review of 150 publications was conducted using the terms:

- `Latin American modern architecture` + `daylight`, `thermal`, `cooling`
- Sources were filtered by title relevance, abstract content, and full review readiness.

> See `data/lit_review_summary.csv` for full screening data.

### 2. 🏛️ Building Selection

From 48 projects in the 1955 MoMA catalog, 6 were selected based on:

- **Program**: collective housing
- **Climate**: Köppen Aw (tropical savanna)

| Project | Architect(s) | City | Year |
|--------|-------------|------|------|
| Pedregulho | Eduardo Affonso Reidy | Rio de Janeiro | 1950 |
| Unidade de Habitação | Guido Bermudez | Caracas | 1954 |
| Multicelulares | Bermudez & Villanueva | Caracas | 1954 |
| Antonio Ceppas | Jorge Machado Moreira | Rio de Janeiro | 1952 |
| Cintra, Bristol & Caledônia | Lúcio Costa | Rio de Janeiro | 1953 |
| Montserrat | Benacerraf & Guinand | Caracas | 1950 |

![Map of Building Locations](images/building_map.png) <!-- Add your map -->

---

### 3. 🖥️ Simulation Procedure

All daylight simulations were performed using **Solemma’s ClimateStudio** with models created in **Rhinoceros 8** + **Grasshopper**. Scripts for facade devices are provided:

- `scripts/brise_soleil.gh`
- `scripts/musharabya.gh`

**Modeling assumptions:**

- Wall thickness: 18–25 cm
- Window height: 120 cm, sill at 105 cm
- No glazing thickness modeled
- Brise-soleil & musharabya treated via parametrized Grasshopper scripts
- All floorplates treated with open door policy
- Floor area excludes walls
- Floor albedo: 0,2

![Example Rhino Model](images/rhino_model_example.png)

---

## 📊 Results

Daylight performance was measured using:

- **Mean & median lux**
- **Annual Sunlight Exposure (ASE)**
- **Spatial Daylight Autonomy (sDA)**
- **Daylight Glare Probability (DGP)**

Key findings:

- Lúcio Costa’s and Jorge Machado’s projects (with well-proportioned brise-soleil and musharabya) perform best.
- Orientation (angle from North) plays a significant role in performance—even without shading devices.
- High ASE and variation = poor environmental adequacy (e.g., Reidy’s Pedregulho).

![Daylight Scatter Plot](images/scatter_ase_orientation.png)

---

## 🛠️ Replication Guide

1. 🧾 **Download Files**
   - Clone this repo or download ZIP.
   - Get `rhino_models/`, `scripts/`, and `data/`.

2. 💻 **Install Tools**
   - Rhino 8 with Grasshopper
   - Solemma ClimateStudio

3. ⚙️ **Run Simulations**
   - Open `.3dm` files and attach appropriate Grasshopper scripts
   - Adjust orientation for each model using Rhino tools
   - Simulate for:
     - June 21 (Summer Solstice)
     - Sept 22 (Equinox)
     - Dec 21 (Winter Solstice)

4. 📈 **Analyze Results**
   - Use `results/data_summary.csv`
   - Refer to `results/plots/` for visualizations
   - Reproduce figures using the provided Python notebooks in `analysis/`

---

## 📁 Repository Structure




