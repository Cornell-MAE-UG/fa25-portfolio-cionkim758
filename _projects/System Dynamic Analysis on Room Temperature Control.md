---
layout: project
title: System Dynamic Analysis on Room Temperature Control
description: Setting up and Analyzing the PID control for closed loop and open loop models
technologies: [Matlab]
image: /assets/images/System Dynamics Modeling.png
pdf: /assets/System Dynamics Final Report.pdf
---


# Room Temperature Control — Dynamic Modeling & Control

---

## 🔹 One-Screen Summary 

We modeled and controlled the thermal dynamics of a room to study how heating input, environmental losses, and feedback control affect temperature regulation.
I owned the **first-principles modeling**, deriving the governing ODE, state-space representation, and block-diagram structure used for both open-loop analysis and closed-loop controller design.

**Key outcomes:**

* Derived a physically grounded first-order thermal model
* Built state-space and transfer-function representations
* Identified how thermal resistance and capacitance shape system response
* Provided the plant model used for PI controller design and simulation

---

## 1. System Overview (Team)

We studied room temperature regulation as a dynamic system that balances heat input from a heater and heat loss to the environment. The system is simple enough to model analytically, yet rich enough to demonstrate key concepts in dynamics and control.

The full project included:

* Thermal modeling (my role)
* Open-loop behavior and parameter estimation
* Closed-loop PI control design
* MATLAB and Simulink simulation

---

## 2. Physical Modeling & Assumptions (My Contribution)

I developed the core thermal model using **energy conservation** and lumped-parameter assumptions.

**System interpretation:**

* The room is treated as a single thermal mass
* Heat enters via warm air from a heater
* Heat exits through walls/windows modeled as an equivalent thermal resistance

**Key assumptions:**

* Uniform room temperature (well-mixed air)
* Constant air properties
* Linear heat transfer through the building envelope
* First-order dynamics dominate system behavior

---

## 3. Governing Energy Balance (First Principles)

```text
Energy stored in room = Heat in − Heat out
```

### Heat Flow Terms

```text
Heater input:
Q̇_heater = ṁ c (T_h − T_r)

Heat loss to outside:
Q̇_loss = (T_r − T_out) / R_eq
```

### Energy Balance ODE

```text
C dT_r/dt = ṁ c (T_h − T_r) − (T_r − T_out)/R_eq
```

Rearranged into standard form:

```text
dT_r/dt = −(ṁc/C + 1/(C R_eq)) T_r
          + (ṁc/C) T_h
          + (1/(C R_eq)) T_out
```

This equation forms the **plant model** for all later analysis and control design.

---

## 4. State-Space Representation (My Contribution)

```text
State:
x = T_r

Inputs:
u₁ = T_h   (heater outlet temperature)
u₂ = T_out (outside temperature)

Output:
y = T_r
```

### State-Space Form

```text
ẋ = a x + b₁ u₁ + b₂ u₂
y = x
```

Where:

```text
a  = −(ṁc/C + 1/(C R_eq))
b₁ = ṁc / C
b₂ = 1 / (C R_eq)
```

This representation allowed the system to be analyzed consistently in:

* Open-loop form
* Transfer-function form
* Closed-loop feedback configurations

---

## 5. Physical Interpretation of Parameters

```text
C  → Thermal capacitance (thermal inertia)
R  → Thermal resistance (insulation quality)
ṁc → Heater coupling strength
```

**Insights:**

* Larger **C** → slower temperature response
* Larger **R** → higher steady-state temperature
* Larger **ṁc** → faster response, stronger heater influence

These relationships directly explain real-world heating behavior.

---

## 6. Open-Loop System Behavior (Context)

Using the derived model, the system behaves as a **first-order low-pass system**:

```text
τ = 1 / (ṁc/C + 1/(C R))
```

From the chosen parameters:

* Time constant ≈ **100 seconds**
* Steady-state temperature ≈ **20°C**

This means the room:

* Responds slowly to changes
* Filters out high-frequency disturbances
* Is dominated by thermal inertia rather than heater dynamics

---

## 7. Why Modeling Matters Here (My Role)

**I** ensured the model:

* Preserved physical meaning
* Used measurable parameters
* Scaled correctly with insulation, heater strength, and environment

Because of this, the same model could be:

* Used for open-loop prediction
* Converted to transfer functions
* Embedded directly into Simulink
* Controlled using classical PI methods

The controller design only works **because the plant model is correct**.

---

## 8. Engineering Takeaways

* **We** demonstrated how everyday systems map cleanly to control theory
* **I** translated physics → ODE → state-space → block diagram
* Thermal systems are slow, stable, and dominated by energy storage
* Feedback improves regulation, but passive design (R and C) sets the limits

---

## 9. Why This Project Belongs in My Portfolio

This project highlights my ability to:

* Build models from conservation laws
* Identify states, inputs, and disturbances correctly
* Create control-ready representations of physical systems
* Bridge theory, simulation, and real-world intuition

It reflects the exact modeling mindset required in mechanical systems, energy systems, and control-adjacent engineering roles.

