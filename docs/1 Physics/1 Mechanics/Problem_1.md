# Investigating the Range as a Function of the Angle of Projection

## 1. Theoretical Foundation

### 1.1 Deriving the Equations of Motion

Consider a projectile launched from the origin at an initial speed \( v_0 \) and angle \( \theta \) above the horizontal. The acceleration due to gravity is \( g \) downward.

- **Horizontal motion:**

\[
x(t) = v_0 \cos\theta \cdot t
\]

- **Vertical motion:**

\[
y(t) = v_0 \sin\theta \cdot t - \frac{1}{2} g t^2
\]

These come from integrating the acceleration \( \vec{a} = (0, -g) \) twice, with initial velocity components \( v_0 \cos\theta \) and \( v_0 \sin\theta \).

### 1.2 Family of Solutions

The time of flight \( T \) is found by setting \( y(T) = 0 \) (returns to launch height):

\[
v_0 \sin\theta \cdot T - \frac{1}{2} g T^2 = 0 \quad \Rightarrow \quad T = \frac{2 v_0 \sin\theta}{g}
\]

The horizontal range \( R \) is:

\[
R = x(T) = v_0 \cos\theta \cdot T = \frac{v_0^2}{g} \sin 2\theta
\]

The family of solutions depends on \( v_0 \), \( g \), and \( \theta \). Changing these parameters alters the shape and extent of the projectile’s trajectory.

## 2. Analysis of the Range

The range \( R \) is maximal when:

\[
\sin 2\theta = 1 \quad \Rightarrow \quad 2\theta = 90^\circ \quad \Rightarrow \quad \theta = 45^\circ
\]

**Influence of parameters:**

- Increasing \( v_0 \) increases \( R \) quadratically.
- Increasing \( g \) decreases \( R \) inversely.
- The angle \( \theta \) controls the shape of the sine function, shifting the range.

## 3. Practical Applications and Limitations

### Real-world adjustments:

- Launch height different from zero modifies the time of flight and range.
- Air resistance reduces range and alters trajectory shape.
- Uneven terrain complicates impact points.

### Extensions:

- Include drag force proportional to velocity.
- Model wind as horizontal acceleration.
- Use numerical integration for non-constant acceleration.
import numpy as np
import matplotlib.pyplot as plt

# Constants
g = 9.81  # gravity (m/s^2)
v0 = 20.0  # initial velocity (m/s)

# Range calculation function
def projectile_range(v0, theta_deg, g=9.81):
    theta = np.radians(theta_deg)
    return (v0**2 / g) * np.sin(2 * theta)

# Generate angles from 0 to 90 degrees
angles = np.linspace(0, 90, 500)
ranges = projectile_range(v0, angles)

# Plot range vs angle
plt.figure(figsize=(8,5))
plt.plot(angles, ranges, label=f'v0 = {v0} m/s')
plt.xlabel('Angle of Projection (degrees)')
plt.ylabel('Range (meters)')
plt.title('Projectile Range as a Function of Angle')
plt.legend()
plt.grid(True)
plt.show()
