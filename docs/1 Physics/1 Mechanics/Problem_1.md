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
Observations
The function 
𝑅
(
𝜃
)
R(θ) is symmetric about 45°.

The range is maximum at 
𝜃
=
45
∘
θ=45 
∘
 .

Increasing the initial velocity 
𝑣
0
v 
0
​
  increases the range quadratically.

Limitations and Extensions
Limitations:

Assumes no air resistance.

Flat launch and landing surfaces.

Extensions:

Include initial height 
ℎ
h.

Model air drag or wind.

Simulate real-world applications (e.g., soccer kicks, rocket launches).

Deliverables
A Markdown or Jupyter Notebook including:

Theoretical derivation.

Python script for simulation.

Graphs of range vs angle.

Discussion on model limitations and extensions.
