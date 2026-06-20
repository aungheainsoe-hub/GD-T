# 1. Fundamentals
## What is Geometric Dimensioning and Tolerancing (GD&T)?
GD&T is a standardized way for a designer/mechanical engineer to communicate exactly how a part must be made. Instead of relying on simple plus or minus dimensions, which different people can read differently, it defines the allowable variation in a part's form, orientation and location and ties it to clear reference point called datums. This removes any ambiguity between designer and manufacturer so the parts are produced accurately and fit together as intended and can be produced cost effectively.

Using GD&T bring clear practical advantages: 
- **Cost-effective:** it allows the widest manufacturing tolerance a part can have while still working correctly, so fewer parts are rejected and production is cheaper.
- **Reduced lead time:** clear, standardized drawings remove ambiguity, which cuts the back-and-forth between the designer and the manufacturer and reduces errors and rework.
- **Reliable assembly:** by controlling how features relate to each other, parts are guaranteed to fit and function as intended.
- **Consistent inspection:** everyone measures the part the same way, so results are repeatable.

## The 14 geometric characteristics

| Category | Characteristics | Datum needed? |
|---|---|---|
| **Form** | Straightness, Flatness, Circularity, Cylindricity | No |
| **Orientation** | Perpendicularity, Parallelism, Angularity | Yes |
| **Location** | Position, Concentricity, Symmetry | Yes |
| **Profile** | Profile of a line, Profile of a surface | Optional |
| **Runout** | Circular runout, Total runout | Yes |
<img width="897" height="601" alt="table-gd" src="https://github.com/user-attachments/assets/3c0cdd80-ba93-4f9d-bea1-269d3491bfbc" />

### Drawing Architecture Breakdown

### 1. View Projections
* **Orthographic Views:** Front and Side projections detailing nominal limits, thickness, and functional features via First Angle Projection.
* **Isometric View:** 3D pictorial reference provided for rapid part morphology interpretation.

### 2. Administrative & Control Zones
* **Title Block:** Standardized boundary containing metadata (Drawn by: Aung Heain Soe), material specifications (`Alloy Steel`), and default tolerance blocks.
* **Revision Table:** Located in the upper right corner to guarantee engineering change traceability.

### 3. GD&T Implementation
* **Primary Datum A:** Establishes orientation perpendicularity.
* **Secondary & Tertiary Datums (B, C):** Constraint alignment edges locking down translation axes.
* **Feature Control Frame:** Restricts the $\varnothing 40.00$ internal feature center axis to a cylindrical tolerance zone of $\varnothing 0.01\text{ mm}$ at Maximum Material Condition (MMC).


<img width="1162" height="817" alt="label1" src="https://github.com/user-attachments/assets/86146b0f-97a3-45d3-8c9b-5a32a7d64b59" />




## Feature Control Frame (FCF)
Feature Control Frame is the main component of GD&T. It provides the instructions regarding the features that need to be controlled such as form, orientation, location and runout. 
<img width="712" height="365" alt="Screenshot 2026-06-20 114300" src="https://github.com/user-attachments/assets/0fa1f7c1-afb5-42e6-97cd-7c7e10e8a1f6" />

## Material condition modifiers

| Modifier | Meaning | Effect |
|---|---|---|
| **MMC** Ⓜ | Maximum Material Condition (largest pin / smallest hole) | Grants **bonus tolerance** as the feature departs from MMC |
| **LMC** Ⓛ | Least Material Condition | Protects minimum wall / edge distance |
| **RFS** | Regardless of Feature Size (default) | No bonus; tolerance is fixed at the stated value |

**Bonus tolerance** is the practical payoff of MMC. As a hole is drilled larger than
its smallest allowed size (its MMC), the position tolerance effectively grows, because
a bolt will still pass and the parts still assemble. That extra tolerance is free yield
for manufacturing.

## The two rules

### 1. ASME Y14.5 — The Envelope Principle (Rule #1)
Under the ASME standard, **"size controls form"** by default. 

* **The Rule:** A regular feature of size must have **perfect form at MMC** (Maximum Material Condition). As the physical part departs from MMC toward LMC (Least Material Condition), it dynamically earns that much form tolerance (straightness, flatness, circularity) for free.
* **Engineering Intent:** You only add a separate form callout (like flatness or straightness) when the design requires a boundary **tighter** than what the size limits already guarantee.

---

### 2. ISO GPS — The Principle of Independency
Under the international ISO standard, size and form are completely decoupled by default.

* **The Rule:** A size tolerance controls **local linear cross-sections only**. It does not limit form deviations (e.g., a pin can be bent or warped but still legally pass inspection if its local diameters measure within spec).
* **The Solution:** To enforce the envelope requirement on an ISO-governed drawing, you must explicitly add the **Envelope Modifier Symbol** $\mathrm{(E)}$ directly next to the dimension limits.

$$\text{ISO Specification Example: }\ \varnothing 20 \pm0.1\ \mathrm{(E)}$$


**Rule #2 — RFS by default.** Every geometric tolerance applies regardless of feature
size unless Ⓜ or Ⓛ is stated. Bonus tolerance only exists when you ask for it with a
modifier.

*(Plus the screw-thread convention: tolerances and datums on threaded features default
to the pitch diameter unless MAJOR DIA or MINOR DIA is noted.)*
