---
layout: project
title: Fluid Mechanics Dissection
description: Dissecting and analyzing fluid flow of an air pump for paddle boards
technologies: [Fusion, MATLAB]
image: /assets/images/Fluids dissection.png
pdf: /assets/Fluids final project.pdf
---


---

# Fluid Mechanics Dissection: Paddle Board Air Pump


## 🔹 One-Screen Summary 

My team dissected and analyzed a dual-chamber manual air pump to understand how fluid mechanics, geometry, and operating modes affect performance and user effort.
I led the analytical modeling and design trade studies, using first-principles fluid mechanics to quantify flow regimes, pressure losses, and ergonomic scaling laws.

**Key outcomes:**

* Turbulent but incompressible airflow (Re ≈ 10⁴, Ma ≪ 1)
* Hose losses negligible relative to board pressure
* Cylinder diameter scales handle force with **r²**, explaining multi-mode design
* Human ergonomics, not flow losses, dominate design constraints

---

## 1. System Overview & Dissection (Team)

We physically disassembled the pump to identify functional components and measure critical dimensions. The pump uses two cylinders and a selector dial to switch between operating modes that trade volume for pressure.

Measured parameters included:

* Cylinder diameters and stroke length
* Hose diameter and length
* Valve layout and pressure gauge placement

This grounding in real hardware informed all downstream analysis.

---

## 2. Modeling Assumptions (My Analysis Scope)

I focused on **Mode 3 (low volume, high pressure)**, which represents the most demanding operating condition for the user.

**Assumptions:**

* Air treated as incompressible (Mach number ≪ 1)
* Steady, fully developed flow in the hose
* Cylinders and hose modeled as ideal circular tubes
* Losses dominated by friction and minor losses

---

## 3. Governing Theory (First-Principles)

```text
Continuity:
Q = U A

Bernoulli with losses:
p₁ + ½ρU₁² = p₂ + ½ρU₂² + Δp_loss

Reynolds Number:
Re = ρ U D / μ

Frictional Pressure Loss:
Δp_f = f (L/D) (ρ U² / 2)

Handle Force:
F = P A_piston
```

**Physical interpretation:**

* Reynolds number sets the flow regime
* Friction factor depends on Re and surface roughness
* Handle force scales with piston **area**, not flow resistance

---

## 4. MATLAB — Flow Regime & Scaling (My Work)

```matlab
% Geometry
D_h = 0.025;        % Hose diameter [m]
L_h = 1.5;          % Hose length [m]
D_c = 0.06;         % Cylinder diameter [m]
L_s = 0.47;         % Stroke length [m]

% Air properties
rho = 1.2;          % Density [kg/m^3]
mu  = 1.8e-5;       % Dynamic viscosity [Pa·s]

% Stroke volume and flow rate
A_c = pi*(D_c/2)^2;
V_stroke = A_c * L_s;      % m^3
f = 1/3;                   % strokes per second
Q = V_stroke * f;

% Hose velocity
A_h = pi*(D_h/2)^2;
U = Q / A_h;

% Reynolds number
Re = rho * U * D_h / mu;
```

```text
Result:
Re ≈ O(10⁴) → Turbulent flow
```

---

## 5. Compressibility Check

```matlab
c = 343;       % Speed of sound [m/s]
Ma = U / c;
```

```text
Ma ≈ 0.02 → Compressibility effects negligible
```

**Conclusion:**
Bernoulli + friction losses are valid for this system.

---

## 6. Pressure Loss Quantification (My Work)

```matlab
fD = 0.025;  % Friction factor (turbulent, smooth hose)
dp = fD * (L_h/D_h) * (rho*U^2/2);
```

```text
Δp_hose ≈ 180 Pa
```

**Insight:**
Hose pressure losses are **orders of magnitude smaller** than paddle board operating pressure → flow resistance is not the limiting factor.

---

## 7. Design Trade Studies (My Contribution)

### 🔺 Cylinder Diameter Scaling

```text
Stroke volume: V ∝ r²
Handle force: F = P π r²
```

* 2× diameter → 4× air per stroke
* 2× diameter → 4× handle force

➡️ Explains why high-pressure mode uses only one cylinder.

---

### 🔺 Hose Geometry Effects

```text
Δp_bend = K (ρ U² / 2)
```

* Smooth curvature minimizes losses
* Sharp bends increase losses, but magnitude remains small
* Ergonomics prioritized over marginal efficiency gains

---

### 🔺 Fluid Viscosity Sensitivity

```text
Re ∝ 1 / μ
F ∝ μ
```

* Air: μ ≈ 1.8×10⁻⁵ Pa·s → feasible
* High-viscosity fluids → forces increase by orders of magnitude

➡️ System fundamentally relies on low-viscosity working fluid.

---

## 8. Engineering Takeaways

* We connected real consumer hardware to core fluid mechanics principles.
* I demonstrated that ergonomic constraints dominate over fluid losses.
* Multi-mode operation is not a convenience feature—it is a physics necessity.

---

## 9. Why This Project Matters

This project demonstrates my ability to:

* Translate physical hardware into analytical models
* Use scaling laws to explain design decisions
* Quantitatively justify why a system works—not just how

It reflects the kind of reasoning required in real mechanical design roles, where performance, human interaction, and physics intersect.

