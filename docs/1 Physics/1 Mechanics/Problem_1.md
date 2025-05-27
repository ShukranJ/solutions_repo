# Problem 1: Investigating the Range as a Function of the Angle of Projection

## Motivation

Projectile motion, while seemingly simple, provides a rich framework for exploring core principles of physics.

Despite the apparent simplicity of launching an object into the air, the underlying physics involves various interacting parameters:

- **Initial velocity**: \( v_0 \)
- **Gravitational acceleration**: \( g \)
- **Launch angle**: \( \theta \)

These variables result in a wide variety of possible trajectories, modeling real-world phenomena from sports to spacecraft dynamics.

---

## Theoretical Background

Assume an object is launched from flat ground with an initial velocity \( v_0 \) at an angle \( \theta \) above the horizontal, and neglect air resistance.

### Equations of Motion

- **Horizontal position**:  
  \[
  x(t) = v_0 \cos(\theta) \cdot t
  \]

- **Vertical position**:  
  \[
  y(t) = v_0 \sin(\theta) \cdot t - \frac{1}{2} g t^2
  \]

### Time of Flight

The projectile returns to the ground when \( y(t) = 0 \):

\[
T = \frac{2 v_0 \sin(\theta)}{g}
\]

### Range Equation

Substitute time of flight into the horizontal equation to find range:

\[
R = v_0 \cos(\theta) \cdot T = \frac{v_0^2 \sin(2\theta)}{g}
\]

This expression defines a **family of solutions** depending on:
- \( v_0 \): launch speed
- \( \theta \): launch angle
- \( g \): local gravity

Maximum range is achieved when \( \theta = 45^\circ \), since \( \sin(2\theta) \) reaches its maximum of 1.

---

## Analysis of Range Behavior

### Parameter Influence

- **Velocity**: \( R \propto v_0^2 \) → doubling speed quadruples the range.
- **Gravity**: \( R \propto \frac{1}{g} \) → lower gravity increases range.

### Symmetry

The range is symmetric around \( \theta = 45^\circ \). Angles \( \theta \) and \( 90^\circ - \theta \) yield the same range.

---

## Practical Applications

This model applies to real-world phenomena such as:

- **Sports**: Ball trajectories in football, basketball, etc.
- **Engineering**: Calculations in artillery or construction.
- **Astrophysics**: Trajectories of planetary probes and landers.

### Extensions

- Uneven launch and landing heights.
- Air resistance (drag).
- Wind and rotational effects (e.g., Coriolis force).

---
## Python Simulation

```python
import numpy as np
import matplotlib.pyplot as plt

# --- Constants ---
g = 9.81             # Acceleration due to gravity (m/s²)
v0 = 30              # Initial velocity (m/s)

# --- Angles from 0 to 90 degrees ---
angles_deg = np.linspace(0, 90, 500)       # 500 points from 0° to 90°
angles_rad = np.radians(angles_deg)        # Convert to radians for computation

# --- Range Calculation ---
R = (v0**2) * np.sin(2 * angles_rad) / g   # R = (v₀² * sin(2θ)) / g

# --- Plotting ---
plt.figure(figsize=(10, 6))
plt.plot(angles_deg, R, color='navy', label=f'v₀ = {v0} m/s')
plt.axvline(45, color='red', linestyle='--', label='Maximum at 45°')
plt.title('Range vs Angle of Projection')
plt.xlabel('Angle (degrees)')
plt.ylabel('Range (meters)')
plt.grid(True)
plt.legend()
plt.show()

---

### ✅ Explanation:
- `np.linspace(0, 90, 500)`: Generates 500 evenly spaced angles between 0° and 90°.
- `np.radians(...)`: Converts degrees to radians since `np.sin()` expects radians.
- `R = (v0**2) * np.sin(2 * θ) / g`: Formula for range of projectile on flat ground.
- `plt.axvline(45, ...)`: Highlights the theoretical maximum range at 45°.

Let me know if you’d like:
- The version with launch height,
- A notebook file (.ipynb),
- Or explanations included as comments for educational purposes.

