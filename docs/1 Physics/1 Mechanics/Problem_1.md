# Problem 1
Projectile Motion: Investigating Range as a Function of Angle of Projection
1. Theoretical Foundation
Derivation of Governing Equations
Projectile motion occurs under constant gravitational acceleration, with no initial forces other than the launch velocity (ignoring air resistance for now). We start with Newton’s second law in two dimensions. Assume the projectile is launched from the origin ((0, 0)) with initial velocity v0v_0v_0
 at an angle θ\theta\theta
 relative to the horizontal. Gravity acts downward with acceleration −g-g-g
.
The acceleration vector is:
a=(0,−g)\mathbf{a} = (0, -g)\mathbf{a} = (0, -g)
Since acceleration is the second derivative of position, we write the differential equations for the (x)- and (y)-coordinates:
d2xdt2=0,d2ydt2=−g\frac{d^2x}{dt^2} = 0, \quad \frac{d^2y}{dt^2} = -g\frac{d^2x}{dt^2} = 0, \quad \frac{d^2y}{dt^2} = -g
x-direction:
Integrate twice:
dxdt=vx(0)=v0cos⁡θ\frac{dx}{dt} = v_x(0) = v_0 \cos\theta\frac{dx}{dt} = v_x(0) = v_0 \cos\theta
x(t)=(v0cos⁡θ)tx(t) = (v_0 \cos\theta) tx(t) = (v_0 \cos\theta) t
y-direction:
dydt=vy(0)−gt=v0sin⁡θ−gt\frac{dy}{dt} = v_y(0) - g t = v_0 \sin\theta - g t\frac{dy}{dt} = v_y(0) - g t = v_0 \sin\theta - g t
y(t)=(v0sin⁡θ)t−12gt2y(t) = (v_0 \sin\theta) t - \frac{1}{2} g t^2y(t) = (v_0 \sin\theta) t - \frac{1}{2} g t^2
Initial Conditions:
At t=0t = 0t = 0
, x(0)=0x(0) = 0x(0) = 0
, y(0)=0y(0) = 0y(0) = 0
 (launch from origin).

Initial velocity components: vx(0)=v0cos⁡θv_x(0) = v_0 \cos\thetav_x(0) = v_0 \cos\theta
, vy(0)=v0sin⁡θv_y(0) = v_0 \sin\thetav_y(0) = v_0 \sin\theta
.

These equations describe a parabolic trajectory, parameterized by time (t). The family of solutions depends on the free parameters v0v_0v_0
, θ\theta\theta
, and (g). Variations in these parameters yield different trajectories:
v0v_0v_0
: Scales the trajectory’s size (higher velocity, longer range, and height).

θ\theta\theta
: Alters the shape (steep vs. flat trajectory).

(g): Affects the vertical compression (stronger gravity shortens time of flight).

Range Derivation
The range (R) is the horizontal distance traveled when the projectile returns to y=0y = 0y = 0
. Set y(t)=0y(t) = 0y(t) = 0
:
(v0sin⁡θ)t−12gt2=0(v_0 \sin\theta) t - \frac{1}{2} g t^2 = 0(v_0 \sin\theta) t - \frac{1}{2} g t^2 = 0
t(v0sin⁡θ−12gt)=0t (v_0 \sin\theta - \frac{1}{2} g t) = 0t (v_0 \sin\theta - \frac{1}{2} g t) = 0
Solutions: t=0t = 0t = 0
 (launch) or t=2v0sin⁡θgt = \frac{2 v_0 \sin\theta}{g}t = \frac{2 v_0 \sin\theta}{g}
 (landing). The time of flight is:
T=2v0sin⁡θgT = \frac{2 v_0 \sin\theta}{g}T = \frac{2 v_0 \sin\theta}{g}
Substitute into (x(t)):
R=x(T)=(v0cos⁡θ)⋅2v0sin⁡θg=v02sin⁡(2θ)gR = x(T) = (v_0 \cos\theta) \cdot \frac{2 v_0 \sin\theta}{g} = \frac{v_0^2 \sin(2\theta)}{g}R = x(T) = (v_0 \cos\theta) \cdot \frac{2 v_0 \sin\theta}{g} = \frac{v_0^2 \sin(2\theta)}{g}
Using the identity sin⁡(2θ)=2sin⁡θcos⁡θ\sin(2\theta) = 2 \sin\theta \cos\theta\sin(2\theta) = 2 \sin\theta \cos\theta
, the range is:
R(θ)=v02sin⁡(2θ)gR(\theta) = \frac{v_0^2 \sin(2\theta)}{g}R(\theta) = \frac{v_0^2 \sin(2\theta)}{g}
This equation shows the range depends on θ\theta\theta
, v0v_0v_0
, and (g).
2. Analysis of the Range
Dependence on Angle of Projection
The term sin⁡(2θ)\sin(2\theta)\sin(2\theta)
 determines the angular dependence. Since sin⁡(2θ)\sin(2\theta)\sin(2\theta)
 has a maximum value of 1 at 2θ=90∘2\theta = 90^\circ2\theta = 90^\circ
, or θ=45∘\theta = 45^\circ\theta = 45^\circ
, the maximum range occurs at:
Rmax=v02gatθ=45∘R_{\text{max}} = \frac{v_0^2}{g} \quad \text{at} \quad \theta = 45^\circR_{\text{max}} = \frac{v_0^2}{g} \quad \text{at} \quad \theta = 45^\circ
Key observations:
Symmetry: sin⁡(2θ)=sin⁡(180∘−2θ)\sin(2\theta) = \sin(180^\circ - 2\theta)\sin(2\theta) = \sin(180^\circ - 2\theta)
, so angles θ\theta\theta
 and 90∘−θ90^\circ - \theta90^\circ - \theta
 yield the same range (e.g., 30∘30^\circ30^\circ
 and 60∘60^\circ60^\circ
).

Extremes: At θ=0∘\theta = 0^\circ\theta = 0^\circ
 or 90∘90^\circ90^\circ
, sin⁡(2θ)=0\sin(2\theta) = 0\sin(2\theta) = 0
, so R=0R = 0R = 0
 (no horizontal motion).

Influence of Other Parameters
Initial Velocity (v0v_0v_0
): Range scales with v02v_0^2v_0^2
. Doubling v0v_0v_0
 quadruples the range.

Gravitational Acceleration ((g)): Range is inversely proportional to (g). On a planet with lower (g), the range increases.

Launch Height: If launched from height (h), the time to reach y=0y = 0y = 0
 changes. Solve:

h+(v0sin⁡θ)t−12gt2=0h + (v_0 \sin\theta) t - \frac{1}{2} g t^2 = 0h + (v_0 \sin\theta) t - \frac{1}{2} g t^2 = 0
t=v0sin⁡θ+(v0sin⁡θ)2+2ghgt = \frac{v_0 \sin\theta + \sqrt{(v_0 \sin\theta)^2 + 2 g h}}{g}t = \frac{v_0 \sin\theta + \sqrt{(v_0 \sin\theta)^2 + 2 g h}}{g}
Then, R=(v0cos⁡θ)tR = (v_0 \cos\theta) tR = (v_0 \cos\theta) t
. Higher (h) increases (T), thus increasing (R), and shifts the optimal θ\theta\theta
 slightly below 45∘45^\circ45^\circ
.
3. Practical Applications
The idealized model applies to:
Sports: Trajectories of balls in soccer, golf, or basketball. Optimal angles vary due to air resistance or spin.

Engineering: Artillery or rocket launches, where initial velocity and angle are critical for targeting.

Astrophysics: Simplified models for orbits or comet paths (with modified gravity).

Real-World Adaptations:
Uneven Terrain: Adjust the landing condition (e.g., y=f(x)y = f(x)y = f(x)
) and solve numerically.

Air Resistance: Introduce a drag force, Fd∝−v2F_d \propto -v^2F_d \propto -v^2
, turning the equations into non-linear differential equations, solved numerically.

Wind: Add a velocity-dependent force, altering the trajectory asymmetrically.

4. Implementation
Below is a Python script to simulate projectile motion and visualize the range as a function of θ\theta\theta
 for various v0v_0v_0
 and (g).
python

import numpy as np
import matplotlib.pyplot as plt

# Parameters
v0_values = [10, 20, 30]  # Initial velocities (m/s)
g_values = [9.81, 3.71]   # Gravity: Earth, Mars (m/s^2)
theta = np.linspace(0, 90, 100)  # Angles from 0 to 90 degrees
theta_rad = np.deg2rad(theta)

# Range function
def range_projectile(v0, theta_rad, g):
    return (v0**2 * np.sin(2 * theta_rad)) / g

# Plotting
plt.figure(figsize=(10, 6))
for v0 in v0_values:
    for g in g_values:
        R = range_projectile(v0, theta_rad, g)
        plt.plot(theta, R, label=f'v0={v0} m/s, g={g} m/s²')

plt.xlabel('Angle of Projection (degrees)')
plt.ylabel('Range (m)')
plt.title('Range vs. Angle of Projection')
plt.legend()
plt.grid(True)
plt.show()

# Trajectory simulation for specific case
def trajectory(v0, theta_deg, g, h=0):
    theta_rad = np.deg2rad(theta_deg)
    # Time of flight (adjusted for height)
    t_flight = (v0 * np.sin(theta_rad) + np.sqrt((v0 * np.sin(theta_rad))**2 + 2 * g * h)) / g
    t = np.linspace(0, t_flight, 100)
    x = v0 * np.cos(theta_rad) * t
    y = h + (v0 * np.sin(theta_rad)) * t - 0.5 * g * t**2
    return x, y

# Plot trajectories for different angles
v0 = 20
g = 9.81
angles = [30, 45, 60]
plt.figure(figsize=(10, 6))
for theta_deg in angles:
    x, y = trajectory(v0, theta_deg, g)
    plt.plot(x, y, label=f'θ={theta_deg}°')
plt.xlabel('x (m)')
plt.ylabel('y (m)')
plt.title(f'Trajectories (v0={v0} m/s, g={g} m/s²)')
plt.legend()
plt.grid(True)
plt.ylim(bottom=0)
plt.show()

Output Description
First Plot: Shows R(θ)R(\theta)R(\theta)
 for different v0v_0v_0
 and (g). Each curve peaks at θ=45∘\theta = 45^\circ\theta = 45^\circ
, with higher v0v_0v_0
 or lower (g) increasing the range.

Second Plot: Displays trajectories for θ=30∘,45∘,60∘\theta = 30^\circ, 45^\circ, 60^\circ\theta = 30^\circ, 45^\circ, 60^\circ
, showing the parabolic paths and confirming that 45∘45^\circ45^\circ
 maximizes range.

5. Limitations and Extensions
Limitations:
No Air Resistance: Real projectiles experience drag, reducing range and altering the optimal angle.

Flat Terrain: The model assumes landing at y=0y = 0y = 0
. Uneven terrain requires numerical solutions.

Constant Gravity: In astrophysical contexts, (g) may vary with altitude.

Extensions:
Drag: Solve d2rdt2=−gj^−k∣v∣v\frac{d^2\mathbf{r}}{dt^2} = -g \hat{j} - k |\mathbf{v}| \mathbf{v}\frac{d^2\mathbf{r}}{dt^2} = -g \hat{j} - k |\mathbf{v}| \mathbf{v}
, using numerical methods like Runge-Kutta.

Wind: Add a term like Fwind=mawind\mathbf{F}_{\text{wind}} = m \mathbf{a}_{\text{wind}}\mathbf{F}_{\text{wind}} = m \mathbf{a}_{\text{wind}}
.

Spin: Model Magnus effect for spinning objects (e.g., soccer balls).

Terrain: Use a function y=f(x)y = f(x)y = f(x)
 for the ground and solve for the intersection numerically.

Conclusion
The range of a projectile depends strongly on the angle of projection, peaking at 45∘45^\circ45^\circ
 in the idealized case. Parameters like v0v_0v_0
 and (g) scale the range, while launch height or external forces introduce complexity. The model is versatile, applicable to sports, engineering, and astrophysics, but requires extensions like numerical solvers for real-world accuracy. The provided simulations visualize these dependencies, offering a foundation for further exploration.

