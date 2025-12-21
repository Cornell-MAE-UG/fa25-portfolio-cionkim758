---
layout: project
title: FEA on Torque Wrench 
description: Advanced CAD and FEA Project
technologies: [Autodesk Fusion, ANSYS]
image: /assets/images/FEA Wrench Strain Energy.png
image: /assets/images/FEA Wrench Total Deformation.png
---

inite Element Analysis of a Torque Wrench

MAE 3270 — Mechanics of Engineering Materials

🔹 One-Screen Summary (Recruiter View)

We analyzed the structural response of a torque wrench under applied loading to evaluate deformation and energy storage.
I led the finite element modeling, boundary condition setup, and result interpretation, connecting FEA outputs to beam theory and strain-energy concepts from mechanics of materials.

Key outcomes:

Identified deformation distribution under applied torque

Used strain energy to locate critical load-carrying regions

Verified FEA trends against expected cantilever behavior

Demonstrated how geometry and constraints dominate stiffness

1. Project Overview (Team)

We performed a static structural finite element analysis of a torque wrench to study how applied loads translate into deformation and internal energy storage. The goal was not just to generate plots, but to understand where the structure stores energy and why.

The analysis focused on:

Total deformation

Strain energy distribution

Load path from handle to fixed support

2. Geometry, Materials, and Constraints (My Scope)

I was responsible for:

Preparing the mechanical model for analysis

Assigning materials and boundary conditions

Interpreting deformation and strain-energy results

Modeling Assumptions

Linear elastic material behavior

Small deformations

Static loading (no inertial effects)

Perfectly fixed constraint at the wrench head

These assumptions align with classical beam and torsion theory used in MAE 3270.

3. Boundary Conditions & Loading (My Contribution)
Fixed Support:
- Applied at the wrench head
- Removes all translational and rotational DOFs

External Load:
- Force applied at the free end of the handle
- Produces bending-dominated response


This setup effectively models the wrench as a cantilever beam, which allows direct comparison to analytical expectations.

4. Governing Theory (Mechanics of Materials)
Normal stress (bending):
σ = M y / I

Deflection (cantilever beam):
δ_max ∝ F L³ / (E I)

Strain energy:
U = ∫ (σ² / 2E) dV


Interpretation:

Deformation scales strongly with length

Strain energy highlights where material is most “engaged”

Maximum energy does not always occur at maximum displacement


5. Total Deformation Results (FEA)
Maximum deformation ≈ 4.07 × 10⁻² m
Minimum deformation ≈ 0 m (fixed support)

![Photo of ANSYS Total Deformation]({{ "/assets/images/FEA Wrench Total Deformation.png" | relative_url }}){: .inline-image-r style="width: 200px"}

Observed behavior:

Deformation increases monotonically from the fixed end

Maximum deflection occurs at the free end, as expected

Deformed shape matches classical cantilever bending theory

This confirms that the boundary conditions and load application are physically consistent.

6. Strain Energy Distribution (My Analysis Focus)
Maximum strain energy ≈ 0.224 J
Total strain energy ≈ 12.2 J


![Photo of ANSYS Strain Engergy]({{ "image: /assets/images/FEA Wrench Strain Energy.png" | relative_url }}){: .inline-image-l}
 
Key insight:

Peak strain energy occurs near the fixed support

This region carries the highest bending moment

High energy density indicates critical structural regions

Strain energy proved more informative than stress alone for understanding load transfer and stiffness.

7. Why Strain Energy Matters (Design Insight)
High deformation ≠ high structural importance
High strain energy = high load responsibility


This distinction is critical in real design:

Reinforcement should target energy-dense regions

Weight reduction should avoid these zones

Fatigue and failure often initiate where energy concentrates

8. Mesh & Result Interpretation

Mesh density was sufficient to capture bending gradients

Smooth contour transitions indicate numerical stability

No singular stress spikes dominated the solution

The results show physics-driven behavior, not numerical artifacts.

9. Engineering Takeaways

We validated theoretical beam behavior using FEA

I demonstrated how to interpret deformation and energy results meaningfully

Strain energy offers deeper insight than displacement alone

FEA is most powerful when paired with analytical intuition

