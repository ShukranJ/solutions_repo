# Problem 1
Theoretical Foundation

Equations of Motion: A Fundamental Approach

Projectile motion is analyzed by decomposing it into horizontal and vertical components, applying Newton's Second Law:



Where:

$F$ is force

$m$ is mass

$a$ is acceleration

Horizontal Motion (Constant Velocity)

No force acts horizontally (ignoring air resistance), so:



The horizontal displacement is:



Vertical Motion (Under Gravity)

Gravity causes a constant downward acceleration:



The vertical displacement is:



Time of Flight

The projectile hits the ground when $y(t) = 0$. Solving:



Horizontal Range

Substitute time of flight into horizontal displacement:



Key Insights

Maximum Range: Achieved at $\theta = 45^\circ$

Symmetry: Angles $\theta$ and $90^\circ - \theta$ yield equal ranges

Initial Velocity: $R \propto v_0^2$ — doubling $v_0$ quadruples the range

Gravity: $R \propto \frac{1}{g}$ — stronger gravity shortens range

Python Simulation: Range vs. Launch Angle

import numpy as np
import matplotlib.pyplot as plt

# Constants
g = 9.81  # Acceleration due to gravity (m/s^2)
v0 = 20.0  # Initial velocity (m/s)

# Angle values from 0 to 90 degrees
angles_deg = np.linspace(0, 90, 500)
angles_rad = np.radians(angles_deg)

# Range equation
ranges = (v0**2 * np.sin(2 * angles_rad)) / g

# Find maximum range and optimal angle
max_range = np.max(ranges)
optimal_angle = angles_deg[np.argmax(ranges)]

# Plotting
plt.figure(figsize=(10, 6))
plt.plot(angles_deg, ranges, label=f'v₀ = {v0} m/s', color='royalblue')
plt.axvline(optimal_angle, color='red', linestyle='--', label=f'Max at {optimal_angle:.1f}°')
plt.title('Projectile Range vs Launch Angle')
plt.xlabel('Launch Angle (degrees)')
plt.ylabel('Range (meters)')
plt.grid(True)
plt.legend()
plt.tight_layout()
plt.show()

Assumptions of the Ideal Model

Flat terrain (initial and final heights are equal)

Constant gravitational acceleration

No air resistance or wind

Realistic Considerations

Air Resistance

Real projectiles face drag:



Where:

$C_d$: drag coefficient

$\rho$: air density

$A$: cross-sectional area

$v$: velocity

Including drag requires numerical methods (e.g., Euler or Runge-Kutta).

Wind Effects

Tailwind increases range

Headwind decreases range

Uneven Terrain

If landing height $\neq$ launch height, solve using:



Find when $y(t) = y_{target}$ and substitute into $x(t)$ for the range.

Conclusion

Projectile motion offers a simple yet deep model for physics education and applications. This investigation helps students understand:

The impact of different parameters

The balance between analytical solutions and computational simulations

The transition from idealized models to real-world physics