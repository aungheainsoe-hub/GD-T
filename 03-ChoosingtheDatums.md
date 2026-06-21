## Choosing the Datums Effectively

When establishing a Datum Reference Frame (DRF), selecting datums based on **mating function and design intent** is critical to preventing tolerance stack-up and keeping manufacturing costs low. 

### Case Study: Shaft Support Plate Assembly
Consider the assembly below consisting of a precision alignment backing block (red) and a shaft mounting plate (grey):

* **Functional Intent:** The plate mounts flat against a rigid backing block. Two parallel shafts pass through the larger central holes and must rotate perfectly smoothly without binding. 
* **The Interlock Mechanism:** Two small alignment pins locate the plate precisely to prevent it from shifting or rotating under the dynamic loads of the shafts.

| Assembly Alignment View | Front Functional Alignment |
| :---: | :---: |
| <img width="1282" height="822" alt="Screenshot 2026-06-21 104248" src="https://github.com/user-attachments/assets/3c6d0d99-faa6-440f-b868-8b627c0594ae" /> | <img width="946" height="612" alt="Screenshot 2026-06-21 113445" src="https://github.com/user-attachments/assets/3195cb4f-8a06-42c9-b015-630f860f244a" /> |


---

### Step-by-Step Functional Datum Hierarchy

To capture this design intent on our manufacturing drawing, we establish our primary, secondary, and tertiary datums based on the physical sequence of mating contact:
```text
┌─────────────────────────────────────────┐
│   PRIMARY DATUM A: Flat Back Surface    │ ───► Locks 3 Degrees of Freedom (1 Translation, 2 Rotation)
└─────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────┐
│ SECONDARY DATUM B: First Alignment Hole │ ───► Locks 2 Degrees of Freedom (2 Translation Axes)
└─────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────┐
│ TERTIARY DATUM C: Second Alignment Slot │ ───► Locks 1 Degree of Freedom (Rotational Clocking)
└─────────────────────────────────────────┘
└─────────────────────────────────────────┘ 
```
#### 1. Primary Datum A (The 3-Point Touch)
* **What it is:** The large, flat back surface of the grey plate that mates face-to-face with the red bracket.
* **Geometric Function:** It acts as a 3-point contact boundary, completely stopping translation along the perpendicular axis ($Z$-axis) and preventing rocking/tilting (pitch and yaw rotation).
* **Control Requirement:** To ensure it sits perfectly flat without rocking, it is held to a flatness tolerance of `0.03 mm`.

#### 2. Secondary Datum B (The 2-Point Location Center)
* **What it is:** The internal axis of the small alignment hole on the far left.
* **Geometric Function:** Once the plate is flat against Datum A, the first alignment pin presses into this hole. This locks the absolute $X$ and $Y$ translation center coordinates on the plate (2 degrees of freedom).
* **Control Requirement:** It is held to an strict perpendicularity tolerance of `⌀ 0.01 mm (M)` relative strictly to **Datum A** to ensure the pin goes in straight.

#### 3. Tertiary Datum C (The 1-Point Clocking Slot)
* **What it is:** The internal axis of the second alignment hole/slot on the far right.
* **Geometric Function:** With the plate flat (Datum A) and pinned on the left (Datum B), the plate can still pivot or spin like a clock hand. The second pin slips into this feature to stop this rotation (clocking), locking the last remaining degree of freedom.
* **Control Requirement:** It is held to a position tolerance of `⌀ 0.01 mm (M)` relative to **A** and **B** to lock its orientation.

---

### Why Controlling the Shaft Holes relative to [A|B|C] Matters

Look at the Feature Control Frame for the two large functional shaft holes in our study drawing:
<img width="1147" height="795" alt="Screenshot 2026-06-21 113217" src="https://github.com/user-attachments/assets/82bf1977-9d05-4f91-a88b-6a277154f051" />


