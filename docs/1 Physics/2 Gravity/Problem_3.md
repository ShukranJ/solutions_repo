# Problem 3: Trajectories of a Freely Released Payload Near Earth

## Motivation
When an object is released from a moving rocket near Earth, its trajectory depends on initial conditions and gravitational forces. This scenario is critical for understanding orbital mechanics, with applications in space mission planning, satellite deployment, and reentry scenarios.

## Task
1. **Analyze** possible trajectories (parabolic, hyperbolic, elliptical) of a payload released near Earth.
2. **Perform** numerical analysis to compute the payload's path based on initial conditions (position, velocity, altitude).
3. **Discuss** how trajectories relate to orbital insertion, reentry, or escape scenarios.
4. **Develop** a computational tool to simulate and visualize the payload's motion under Earth's gravity.

## Explanation of Subjects
The motion of a payload near Earth is governed by **Newton's Law of Gravitation**:

\[ F = \frac{G M m}{r^2} \]

where:
- \( G \) is the gravitational constant (\( 6.67430 \times 10^{-11} \, \text{m}^3 \text{kg}^{-1} \text{s}^{-2} \)),
- \( M \) is Earth's mass (\( 5.972 \times 10^{24} \, \text{kg} \)),
- \( m \) is the payload's mass,
- \( r \) is the distance from Earth's center.

The trajectory depends on the **specific mechanical energy** (\( \epsilon \)):

\[ \epsilon = \frac{v^2}{2} - \frac{\mu}{r} \]

where:
- \( v \) is the payload's velocity,
- \( \mu = G M \) is Earth's gravitational parameter (\( 3.986 \times 10^{14} \, \text{m}^3 \text{s}^{-2} \)),
- \( r \) is the radial distance.

The trajectory type is determined by the **eccentricity** (\( e \)) of the orbit:
- **Elliptical** (\( e < 1 \)): Closed orbit, e.g., satellite in low Earth orbit.
- **Parabolic** (\( e = 1 \)): Escape trajectory with zero residual energy.
- **Hyperbolic** (\( e > 1 \)): Escape trajectory with excess energy.

**Applications**:
- **Orbital insertion**: Achieving a stable elliptical orbit (e.g., for satellites).
- **Reentry**: Elliptical or parabolic trajectories that intersect Earth's atmosphere.
- **Escape**: Hyperbolic trajectories for interplanetary missions.

## Python Implementation
The following Python script simulates the payload's motion using numerical integration (Runge-Kutta 4 method) and visualizes trajectories for different initial velocities. It assumes a 2D plane for simplicity and neglects atmospheric drag.

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp

# Constants
G = 6.67430e-11  # Gravitational constant (m^3 kg^-1 s^-2)
M = 5.972e24     # Earth's mass (kg)
mu = G * M       # Gravitational parameter (m^3 s^-2)
R_earth = 6.371e6  # Earth's radius (m)

# Equations of motion for 2D orbit
def equations_of_motion(t, state):
    x, y, vx, vy = state
    r = np.sqrt(x**2 + y**2)
    ax = -mu * x / r**3
    ay = -mu * y / r**3
    return [vx, vy, ax, ay]

# Compute specific energy and eccentricity
def compute_orbit_params(r, v):
    r_mag = np.sqrt(r.dot(r))
    v_mag = np.sqrt(v.dot(v))
    energy = v_mag**2 / 2 - mu / r_mag
    h = np.cross(r, v)  # Specific angular momentum (2D: scalar)
    e = np.sqrt(1 + (2 * energy * h**2) / mu**2)
    return energy, e

# Simulate trajectory
def simulate_trajectory(initial_altitude, initial_velocity, angle_deg, t_span, t_eval):
    # Initial conditions
    r0 = [R_earth + initial_altitude, 0]  # Start at (x, 0)
    angle = np.radians(angle_deg)
    v0 = [initial_velocity * np.cos(angle), initial_velocity * np.sin(angle)]
    
    # Compute initial orbit parameters
    energy, eccentricity = compute_orbit_params(np.array(r0), np.array(v0))
    
    # Integrate equations of motion
    state0 = r0 + v0
    sol = solve_ivp(equations_of_motion, t_span, state0, t_eval=t_eval, method='RK45')
    
    return sol, energy, eccentricity

# Plotting function
def plot_trajectory(sol, energy, eccentricity, label):
    x, y = sol.y[0], sol.y[1]
    plt.plot(x / 1e6, y / 1e6, label=f'{label}, e={eccentricity:.2f}, ε={energy:.2e} J/kg')
    
    # Plot Earth
    theta = np.linspace(0, 2 * np.pi, 100)
    x_earth = (R_earth / 1e6) * np.cos(theta)
    y_earth = (R_earth / 1e6) * np.sin(theta)
    plt.fill(x_earth, y_earth, 'b', alpha=0.3, label='Earth')
    
# Simulation parameters
initial_altitude = 200e3  # 200 km altitude
t_span = [0, 3600]  # 1 hour simulation
t_eval = np.linspace(0, 3600, 1000)

# Test different initial velocities for circular, elliptical, parabolic, and hyperbolic orbits
v_circular = np.sqrt(mu / (R_earth + initial_altitude))  # Circular orbit velocity
v_escape = np.sqrt(2 * mu / (R_earth + initial_altitude))  # Escape velocity
velocities = [
    (v_circular, 'Circular', 90),  # Circular orbit (tangential)
    (v_circular * 0.9, 'Elliptical', 90),  # Sub-circular (elliptical)
    (v_escape, 'Parabolic', 90),  # Escape velocity (parabolic)
    (v_escape * 1.2, 'Hyperbolic', 90)  # Above escape (hyperbolic)
]

# Plot setup
plt.figure(figsize=(10, 8))
for v, label, angle in velocities:
    sol, energy, eccentricity = simulate_trajectory(initial_altitude, v, angle, t_span, t_eval)
    plot_trajectory(sol, energy, eccentricity, label)

# Finalize plot
plt.xlabel('X (Mm)')
plt.ylabel('Y (Mm)')
plt.title('Payload Trajectories Near Earth')
plt.legend()
plt.grid(True)
plt.axis('equal')
plt.show()

