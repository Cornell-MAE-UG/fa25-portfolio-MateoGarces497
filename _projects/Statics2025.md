---
layout: project
title: 2D Lifting Mechanism Project
description: Optimized Lifting Mechanism Design
technologies: Pencil and Paper
image: /assets/images/Diagram.png
---

For ENGRD2020: Statics and Mechanics of Solids, we were asked to design a frame/mechanism to lift the maximum possible weight to the highest possible height, given a 2D design space of 150 cm long and 50 cm tall, a bar of fixed length, three pin supports (two of which must be mounted on the ground), and a linear actuator selected from a manufacturer catalog. The project involved sketching, CAD modeling, and mechanical analysis to create an optimized lifting system.

---

## Step 1 – Rigid Bar Mechanism

### Problem definition

The design problem can be summarized as:

> *Configure a planar mechanism within a 150 cm × 50 cm design window so that a bar, driven by a linear actuator and supported by pin joints, can lift the largest possible weight to the highest possible height.*

In **Step 1**, the bar is treated as **rigid**. The actuator, supports, and bar are assumed perfectly rigid and joined by ideal pin connections.

### Constraints and objectives

**Geometric and kinematic constraints**

- 2D design space: **150 cm long × 50 cm tall**
- Bar length: a rigid **1.5 m lever**
- Three pin supports available, with **two on the ground**
- All joints modeled as **ideal pins** (no friction, no play)
- Mechanism motion must remain inside the 150 cm × 50 cm window

**Specific geometry used in my design**

- Lever ground pin at **x = 0 m** on the floor  
- Load applied at the **free end of the lever**, 1.5 m from the ground pin  
- Actuator ground pin at **x = 0.05 m** on the floor  
- Actuator–lever pin located **0.013 m from the base of the lever** along the bar  

In this configuration, both the actuator and the lever are free to rotate about their ground pins, creating a simple but highly leveraged system in which the actuator’s moment about the ground pin opposes the moment from the applied load.

**Actuator constraint**

For this mechanism, I selected a **Tolomatic IMA55 integrated actuator** with:

- Roller-nut screw and 3-stack motor  
- Maximum peak thrust of approximately **2300 N**

I checked the physical dimensions and stroke so that the actuator fits inside the 150 cm × 50 cm design window throughout its motion.

**Design objectives**

1. **Maximize the lifted weight** \(W\) that the mechanism can support.  
2. **Maximize the lift height** of the load, subject to the 50 cm vertical limit.  
3. Respect the actuator’s maximum force and geometric constraints.

### Design degrees of freedom

The main design degrees of freedom (DOFs) in this mechanism are:

- **Bar angle (theta)**  
  - The 1.5 m lever rotates about the ground pin at `x = 0`.  
  - The vertical position of the load is set by the bar angle. In simplified form, the height can be written as  
    `h(theta) = L * sin(theta)`  
    with `L = 1.5 m`.

- **Actuator configuration**  
  - Ground pin location at `x = 0.05 m`.  
  - Lever attachment point at `a = 0.013 m` from the pivot along the bar.  
  - Actuator stroke length, which determines the range of angles `theta` the mechanism can reach.


- **Operating range of motion**  
  - A “start” angle where the lever is nearly horizontal.  
  - A “final” angle just before the load would leave the 50 cm height limit or the actuator would reach the end of its stroke.

Within these DOFs, my design choices aimed to maximize the achievable lift height while still allowing the actuator to overcome the load.

### Static analysis with the bar treated as rigid

To size the mechanism and estimate its lifting capacity, I performed a **moment balance about the lever’s ground pin** using a rigid-bar model.

#### Free-body description

Treating the bar as rigid:

- The lever is pinned at the ground at point \(O\) (x = 0 m).  
- A load \(W\) acts vertically downward at the free end of the 1.5 m lever.  
- The actuator applies a force \(F\) along its own axis at the lever–actuator pin, 0.013 m from the pivot.  
- Ground reactions at the pin support the bar but do not enter the moment balance about that pin.

#### Moment balance

Because the actuator is a **two-force member**, it can only exert a force along its axis. For a given configuration, the line of action of the actuator is set by the two pins (ground pin at `x = 0.05 m` and the bar pin `0.013 m` from the pivot).

Taking moments about the lever ground pin:

- The **load** creates a moment of magnitude  
  `M_W = W * L * cos(theta)`  
  where `theta` is the angle of the lever measured from the horizontal. The `cos(theta)` factor comes from the component of the weight that is perpendicular to the bar.

- The **actuator** creates a moment  
  `M_F = F * d_perp(theta)`  
  where `d_perp(theta)` is the perpendicular distance from the ground pin to the actuator’s line of action.

At the limiting condition (just before the actuator would fail to lift the load), the bar is in static equilibrium, so the moments balance:

`sum M_O = 0  -->  M_F = M_W`

Using the expressions above, this becomes:

`F_max * d_perp(theta) = W * L * cos(theta)`

Solving for the maximum liftable weight:

`W_max(theta) = (F_max * d_perp(theta)) / (L * cos(theta))`

I used this relation to explore how the maximum liftable weight varies with the bar angle `theta` and with the exact geometry of the actuator pins.

#### Limiting configuration and maximum weight

The **failure point** of the mechanism occurs when the projection of the weight onto the actuator’s line of action is smallest—this corresponds to the actuator being nearly fully contracted and almost aligned with the load direction. In this orientation, the effective moment arm `d_perp(theta)` is smallest, and thus the maximum supported weight is also smallest.

For a simplified estimate, I considered a near-horizontal bar (`theta ≈ 0`, so `cos(theta) ≈ 1`) and approximated the actuator’s perpendicular moment arm by the lever–actuator distance `a = 0.013 m`. Using the actuator’s peak thrust:

`W_max ≈ (F_max * a) / L`

With the values used here:

`W_max ≈ (2300 N * 0.013 m) / 1.5 m ≈ 20 N`

This corresponds to lifting roughly a **2 kg mass** at the end of the 1.5 m lever in the worst-case configuration. At more favorable angles (where `d_perp(theta)` is larger or the bar angle changes the moment arm), the mechanism could temporarily support a slightly larger load, but the limiting configuration sets the safe design load.

This moment balance analysis allowed me to:

- Quantify how the load and actuator geometry interact,  
- Identify the worst-case orientation, and  
- Choose a design load that the mechanism can reliably lift throughout its motion.

### Final rigid-bar mechanism

The final rigid-bar mechanism consists of:

- A **1.5 m rigid lever** pinned to the ground at x = 0 m,  
- A **load** applied 1.5 m away at the end of the lever,  
- A **Tolomatic IMA55 actuator**, pinned to the ground at x = 0.05 m and to the lever 0.013 m from the pivot.

The actuator’s extension and retraction rotate the lever, lifting the load along an arc within the 150 cm × 50 cm design space.

<p style="text-align: center;">
  <img src="{{ '/assets/images/Diagram.png' | relative_url }}" alt="Shaded rendering of mechanism" style="width: 200px;">
</p>

---

## Step 2 – Flexible Beam and Deflection

In **Step 2**, the bar is no longer assumed perfectly rigid. Instead, it is modeled as a **beam** that bends under the combined action of:

- The **weight \(W\)** at its free end, and  
- The **actuator force**, acting near the base.

Only the **components of these forces transverse to the beam** contribute to bending.

### 2(a) Maximum deflection – assumptions and model

To estimate the deflection, I made the following assumptions:

1. The bar behaves as a **prismatic Euler–Bernoulli beam** of length `L = 1.5 m`.  
2. Material behavior is **linear elastic**, with Young’s modulus `E`.  
3. For deflection calculations, the ground pin is approximated as a **fixed end**, so the bar is modeled as a **cantilever** (this is conservative for tip deflection).  
4. The dominant contribution to vertical deflection comes from the **load at the free end**. The actuator force is applied very close to the base (0.013 m from the pivot), so its contribution to **tip deflection** is much smaller and is neglected for a first-order estimate.  
5. The design load is taken as the limiting value obtained from the rigid-bar analysis:  
   `W_design ≈ 20 N`

For a cantilever beam of length `L` with a point load `W_design` at the free end, the maximum vertical deflection at the tip is:

`delta_max = (W_design * L^3) / (3 * E * I)`

where `I` is the second moment of area of the beam’s cross-section.

The assignment requirement is that the vertical tip deflection is less than **2% of the beam length**:

`delta_max / L <= 0.02`,  

which can also be written as  

`delta_max <= 0.02 * L = 0.03 m`.

Rearranging the deflection formula gives a minimum required `I`:

`I_min = (W_design * L^3) / (3 * E * delta_max)`

Using:

- `W_design ≈ 20 N`  
- `L = 1.5 m`  
- `E ≈ 69e9 Pa` (typical for 6061-T6 aluminum)  
- `delta_max = 0.03 m`

gives:

`I_min ≈ 1.1e-8 m^4`

Any beam cross-section with `I >= I_min` will keep the tip deflection under 2% of the length for this load.

---

### 2(b) Mass-efficient beam design

To be **mass-efficient**, I wanted a beam that:

- Meets the stiffness requirement (`I >= I_min`), and  
- Uses as little material (and thus mass) as possible.

Rather than using a solid bar, I chose a **thin-walled circular tube**, which is known to be efficient in bending because it places material away from the neutral axis.

**Material**

- **6061-T6 aluminum**  
  - Young’s modulus `E ≈ 69 GPa`  
  - Density `rho ≈ 2700 kg/m^3`

**Cross-section**

I selected the following tube geometry:

- Outer diameter: `D_out = 32 mm`  
- Wall thickness: `t = 1 mm`  
- Outer radius: `r_o = 0.016 m`  
- Inner radius: `r_i = 0.015 m`

For a circular tube:

- Second moment of area:  
  `I = (pi / 4) * (r_o^4 - r_i^4)`  

- Cross-sectional area:  
  `A = pi * (r_o^2 - r_i^2)`

Using the dimensions above:

- Second moment of area:  
  `I ≈ 1.17e-8 m^4`  

  which is slightly larger than the required `I_min ≈ 1.1e-8 m^4`.

- Cross-sectional area:  
  `A ≈ 9.7e-5 m^2`

- Beam mass:  
  `m = rho * A * L ≈ 2700 * 9.7e-5 * 1.5 ≈ 0.39 kg`

**Deflection check**

Using the chosen `I` and the cantilever formula:

`delta_max = (W_design * L^3) / (3 * E * I)`

With `W_design ≈ 20 N`, `L = 1.5 m`, `E = 69 GPa`, and `I ≈ 1.17e-8 m^4`, the maximum tip deflection is:

`delta_max ≈ 0.028 m`

so

`delta_max / L ≈ 0.0186 < 0.02`

This satisfies the requirement that the deflection remain below 2% of the beam length.

**Stress check**

The maximum bending moment at the base of a cantilever with an end load is:

`M_max = W_design * L ≈ 20 * 1.5 = 30 N*m`

The maximum bending stress occurs at the outer surface at a distance `c = r_o` from the neutral axis:

`sigma_max = (M_max * c) / I`

Using `M_max = 30 N*m`, `c = 0.016 m`, and `I ≈ 1.17e-8 m^4`:

`sigma_max ≈ 41 MPa`

This is well below t


### 2(c) Final beam design

The final flexible-beam mechanism can be illustrated with two views:

1. A **side view** of the mechanism (same geometry as in Step 1), but with the lever labeled as a bending beam and the deflected shape exaggerated.  
2. A **cross-sectional view** of the 32 mm × 1 mm aluminum tube, showing the inner and outer diameters.


<p style="text-align: center;">
  <img src="{{ '/assets/images/Diagram2.png' | relative_url }}" alt="Shaded rendering of mechanism" style="width: 200px;">
</p>
