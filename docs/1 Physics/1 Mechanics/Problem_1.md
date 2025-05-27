# Problem 1: Investigating the Range as a Function of the Angle of Projection

## Motivation

Projectile motion, while seemingly simple, provides a rich framework for exploring core principles of classical mechanics. The goal of this problem is to analyze how the **range** of a projectile depends on its **angle of projection**.

Despite the apparent simplicity of launching an object into the air, the underlying physics involves a delicate interplay between vertical and horizontal motion, governed by both linear and quadratic relationships. These relationships are influenced by parameters such as:

- **Initial velocity**: \( v_0 \)
- **Gravitational acceleration**: \( g \)
- **Launch height**: \( h \)

These variables result in a wide variety of possible trajectories, modeling real-world phenomena such as the arc of a soccer ball or the path of a rocket.

---

## Theoretical Background

Assume an object is launched from flat ground with an initial velocity \( v_0 \) at an angle \( \theta \) (above the horizontal). Neglecting air resistance:

### Equations of Motion

- **Horizontal position**:
  $$
  x(t) = v_0 \cos(\theta) \cdot t
  $$

- **Vertical position**:
  $$
  y(t) = v_0 \sin(\theta) \cdot t - \frac{1}{2} g t^2
  $$

### Time of Flight

The projectile returns to the ground when \( y(t) = 0 \). Solving:

$$
t = \frac{2 v_0 \sin(\theta)}{g}
$$

### Horizontal Range

The horizontal range \( R \) is:

$$
R = v_0 \cos(\theta) \cdot t = \frac{v_0^2 \sin(2\theta)}{g}
$$

> 📌 **Maximum range** occurs at \( \theta = 45^\circ \)

---

## Python Simulation Example

```python
import numpy as np
import matplotlib.pyplot as plt

# Parameters
v0 = 20  # initial velocity in m/s
g = 9.81  # gravity in m/s^2

# Angle range
angles_deg = np.linspace(0, 90, 100)
angles_rad = np.radians(angles_deg)

# Calculate range
ranges = (v0**2 * np.sin(2 * angles_rad)) / g

# Plot
plt.figure(figsize=(10, 6))
plt.plot(angles_deg, ranges, label=f'Initial Velocity = {v0} m/s', color='blue')
plt.title('Projectile Range vs Angle of Projection')
plt.xlabel('Launch Angle (degrees)')
plt.ylabel('Range (meters)')
plt.grid(True)
plt.legend()
plt.show()
## Observations

From the analytical expression:

\[
R = \frac{v_0^2 \sin(2\theta)}{g}
\]

We observe the following:

- The range is **maximum at** \( \theta = 45^\circ \), since \( \sin(90^\circ) = 1 \).
- The function \( \sin(2\theta) \) is **symmetric** about \( \theta = 45^\circ \), meaning:
  \[
  R(\theta) = R(90^\circ - \theta)
  \]
- **Doubling** the initial velocity \( v_0 \) results in **quadrupling** the range, due to the \( v_0^2 \) term.
- **Gravitational acceleration** \( g \) is inversely proportional to the range; lower gravity (e.g., on the Moon) results in longer ranges.
- For small and large angles (close to \( 0^\circ \) or \( 90^\circ \)), the range is very short due to \( \sin(2\theta) \approx 0 \).

---

## Limitations

While the ideal projectile motion model is insightful, it has several simplifying assumptions:

- **No air resistance**: Real-world projectiles experience drag forces that reduce range.
- **Flat terrain**: The model assumes launch and landing occur at the same height.
- **No wind**: External forces such as wind or spin are not considered.
- **No rotational effects**: The projectile is treated as a point mass.

These simplifications may result in discrepancies when comparing theoretical and experimental outcomes.

---

## Extensions and Real-World Applications

The basic model can be extended to account for more complex and realistic situations:

- **Initial Height**: If the projectile is launched from a height \( h \), the total flight time and range change significantly.
- **Air Resistance**: Incorporating drag introduces nonlinear differential equations, which typically require numerical methods.
- **Uneven Terrain**: Modeling launch and landing at different elevations reflects real-life applications like ballistic launches.
- **Wind Effects**: Adding wind velocity vectors changes both the range and trajectory shape.
- **Rotational Dynamics**: For spinning objects (e.g., balls), lift forces like the Magnus effect may alter the motion.

These extensions make the model applicable in fields such as:

- **Sports Physics** (e.g., soccer, basketball, golf)
- **Aerospace and Ballistics**
- **Robotics and Engineering Trajectory Planning**

---

## Deliverables Summary

Your submission should include:

- 📄 A **Markdown document** or **Jupyter Notebook** containing:
  - ✅ Derivation of theoretical equations
  - ✅ Simulation using Python
  - ✅ Graphical analysis (e.g., range vs. angle)
  - ✅ Discussion on assumptions, limitations, and real-world extensions
