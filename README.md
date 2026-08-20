# Multidisciplinary Conceptual Sizing, Aerodynamics & 6-DOF Flight Dynamics of a Tactical Stealth UAV (Paninian-AeroX1)

An end-to-end aerospace engineering computational pipeline integrating multi-constraint mission sizing, 3D compressible low-observable drag polar estimation, structural $V\text{-}n$ flight envelopes, and linearized 6-DOF dynamic stability analysis for a tactical stealth Unmanned Aerial Vehicle (UAV).

---

## 📌 Project Overview & Specifications

- **Designation:** Paninian-AeroX1
- **Role:** Tactical Multi-Role Reconnaissance & ISR in Contested Airspace
- **MTOW ($W_0$):** $609.71\text{ kg}$ ($5,979.2\text{ N}$)
- **Wing Loading ($W/S$):** $795.9\text{ N/m}^2$
- **Thrust-to-Weight Ratio ($T/W$):** $0.46$ (Installed Sea-Level Thrust $T = 2,734.5\text{ N}$)
- **Wing Geometry:** Span $b = 6.60\text{ m}$, Aspect Ratio $\text{AR} = 5.80$, Leading-Edge Sweep $\Lambda_{\text{LE}} = 32^\circ$, Taper Ratio $\lambda = 0.35$

---

## 🚀 Key Engineering Modules

### 1. Multi-Constraint Design Space Matching (Mattingly Method)
- Evaluated master constraint boundaries: stall speed limit ($\le 28.0\text{ m/s}$), takeoff ground roll ($S_{\text{TO}} \le 220\text{ m}$), cruise speed ($75\text{ m/s}$ at $5,000\text{ m}$), sea-level climb ($\text{ROC} \ge 12\text{ m/s}$), and sustained combat turn ($3.5g$ at $3,000\text{ m}$).
- Selected optimal design point with a $15\%$ safety margin below stall boundaries.

### 2. 3D Compressible Aerodynamics & Low-Observable Drag Polar
- **Lift-Curve Slope:** Modeled via Helmbold-Diederich formulation ($C_{L\alpha} = 4.045\text{ rad}^{-1}$).
- **Zero-Lift Parasite Drag ($C_{D0} = 0.0141$):** Flat-plate turbulent boundary layer friction with form & interference factors for faceted chined fuselage, cropped-delta wing, and $38^\circ$ canted V-tail ruddervators.
- **Total Parabolic Polar:** $C_D = 0.0141 + 0.0669 C_L^2$ with maximum aerodynamic efficiency $(L/D)_{\max} = 16.29$ at $C_L = 0.46$.

### 3. Flight Performance & Structural Flight Envelope (FAR-23 / MIL-STD)
- **Climb & Ceiling:** Sea-level $\text{ROC}_{\max} = 35.44\text{ m/s}$, Service Ceiling $= 9,200\text{ m}$ ($30,184\text{ ft}$).
- **Field Lengths:** Takeoff ground roll $S_{\text{TO}} = 144.9\text{ m}$, Landing roll $S_{\text{land}} = 164.5\text{ m}$.
- **$V\text{-}n$ Diagram:** Complete $+6.0g / -3.0g$ structural maneuvering and Pratt-gust envelope ($V_A = 73.3\text{ m/s}$, $V_D = 93.8\text{ m/s}$).

### 4. 6-DOF Linearized State-Space Stability Analysis
- **Static Stability:** Stable static margin $\text{SM} = 12.0\%$ MAC ($C_{m\alpha} = -0.4854\text{ rad}^{-1}$).
- **Dynamic Stability (MIL-F-8785C Level 1 Compliance):**
  - **Short-Period Mode:** $\omega_n = 2.885\text{ rad/s}, \zeta = 0.454$ (Rapid pitch damping within $3.5\text{ s}$).
  - **Phugoid Mode:** $\omega_n = 0.192\text{ rad/s}, \zeta = 0.051$ (Period $= 32.7\text{ s}$).
  - **Dutch Roll Mode:** $\omega_n = 1.785\text{ rad/s}, \zeta = 0.028$.
  - **Roll Mode:** $\tau_r = 0.923\text{ s}$ ($\le 1.4\text{ s}$ limit).

### 5. Automated OpenVSP 3D CAD & USAF DATCOM Synthesis
- Automated AngelScript export routine (`uav_stealth_geometry.vspscript`) for programmatic parametric 3D CAD lofting in OpenVSP.
- Direct synthesis of USAF DATCOM aerodynamic verification decks.

---

## 🛠️ Tools & Technologies
- **Programming & Analysis:** MATLAB, Simulink
- **CAD & Aerodynamics:** OpenVSP (AngelScript), USAF DATCOM
- **Standards:** MIL-F-8785C, FAR Part 23
