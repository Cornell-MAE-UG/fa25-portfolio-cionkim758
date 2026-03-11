---
layout: project
title: Heat Transfer
description: Steady-state heat transfer analysis of a water heater and thin-film heater system
image: /assets/images/HeatT_HW.png
pdf: /assets/HeatT_HW.pdf
---

## Overview

This project analyzes **steady-state heat transfer** in two engineering systems:

1. A **cylindrical electric water heater** losing heat to surrounding air through convection  
2. A **thin-film heater embedded in a wall** transferring heat through conduction and convection  

The objective was to determine:

- Required heating power  
- Effects of insulation  
- Limits imposed by material temperature constraints  

---

## Key Results

- Insulation **significantly reduces heat loss and required power**
- Conduction and convection can be modeled using **thermal resistance networks**
- **Maximum heat flux is limited by allowable heater temperature**
- **Geometry and material properties strongly influence heat transfer**

---

## Full Assignment

<iframe 
  src="{{ '/assets/HeatT_HW.pdf' | relative_url }}" 
  width="100%" 
  height="800px">
</iframe>

---

## Modeling Assumptions

The systems were analyzed using standard steady-state assumptions:

- Steady-state operation  
- Radiation heat transfer neglected  
- Heater wall resistance negligible  
- Heat transfer dominated by **conduction and convection**  
- **One-dimensional heat transfer** through solid layers  

These assumptions allow the system to be modeled using **first-principles heat transfer equations**.

---

## Governing Heat Transfer Equations

### Convection — Newton’s Law of Cooling

**q = hA (Tₛ − T∞)**

Where:

- **h** = heat transfer coefficient  
- **A** = surface area  
- **Tₛ** = surface temperature  
- **T∞** = surrounding fluid temperature  

---

### Conduction — Fourier’s Law

**q = kA (T₁ − T₂) / L**

Where:

- **k** = thermal conductivity  
- **L** = material thickness  

---

### Heat Flux Form

**q'' = k (T₁ − T₂) / L**

**q'' = h (Tₛ − T∞)**

These equations describe heat transfer **per unit surface area**.

---

## Thermal Resistance Model

Thermal systems can be modeled using **resistance networks**.

Conduction resistance:

**R_cond = L / (kA)**

Convection resistance:

**R_conv = 1 / (hA)**

Total resistance:

**R_total = R_cond + R_conv**

Heat transfer rate:

**q = (T_hot − T_cold) / R_total**

---

## Engineering Observations

### Effect of Insulation

Adding insulation increases **conduction resistance**, reducing heat transfer to the environment.

Benefits:

- Reduced heat loss  
- Lower energy consumption  
- Improved system efficiency  

---

### Surface Area Effects

Heat loss from the cylindrical heater occurs through:

- Side wall surface  
- Top surface  

Heat transfer increases with area:

**q ∝ A**

---

### Heater Temperature Limits

The thin-film heater is limited by its **maximum allowable temperature**.

Temperature rise through conduction:

**ΔT = q'' L / k**

Excess heat flux can cause **material failure**.

---

## Design Implications

Possible improvements:

**Increase convection coefficient**

Increasing fluid velocity raises **h**, improving heat removal.

**Use higher conductivity materials**

Higher **k** reduces conduction resistance.

**Reduce wall thickness**

Lower **L** increases heat transfer capability.

---

## Engineering Takeaways

- Insulation dramatically reduces thermal energy losses  
- Thermal resistance networks simplify multi-layer analysis  
- Heat transfer depends strongly on **geometry and material properties**  
- Thermal design must balance **performance, efficiency, and material limits**

---

## Project Reflection

This work demonstrates the ability to:

- Apply **first-principles heat transfer equations**
- Model conduction and convection processes
- Use **thermal resistance methods** for layered systems
- Interpret results in terms of **engineering design decisions**