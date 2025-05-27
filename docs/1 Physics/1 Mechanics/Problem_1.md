# Problem 1
📘 Problem 1: Investigating the Range as a Function of the Angle of Projection
1. 🧠 Theoretical Foundation
Equations of Motion
From Newtonian mechanics, assume:

No air resistance

Launch from ground level

Constant acceleration due to gravity 
𝑔
g

Initial speed 
𝑣
0
v 
0
​
 

Launch angle 
𝜃
θ

The position of a projectile at time 
𝑡
t is given by:

𝑥
(
𝑡
)
=
𝑣
0
cos
⁡
(
𝜃
)
⋅
𝑡
x(t)=v 
0
​
 cos(θ)⋅t

𝑦
(
𝑡
)
=
𝑣
0
sin
⁡
(
𝜃
)
⋅
𝑡
−
1
2
𝑔
𝑡
2
y(t)=v 
0
​
 sin(θ)⋅t− 
2
1
​
 gt 
2
 

The time of flight 
𝑇
T is determined when 
𝑦
(
𝑇
)
=
0
y(T)=0:

𝑇
=
2
𝑣
0
sin
⁡
(
𝜃
)
𝑔
T= 
g
2v 
0
​
 sin(θ)
​
 
The range 
𝑅
R is then:

𝑅
(
𝜃
)
=
𝑣
0
cos
⁡
(
𝜃
)
⋅
𝑇
=
𝑣
0
2
sin
⁡
(
2
𝜃
)
𝑔
R(θ)=v 
0
​
 cos(θ)⋅T= 
g
v 
0
2
​
 sin(2θ)
​
 
Family of Solutions
Varying 
𝜃
θ generates a family of parabolic trajectories.

Maximum range occurs when 
𝜃
=
45
∘
θ=45 
∘
 .

2. 📊 Analysis of the Range
Influence of Parameters
Initial velocity 
𝑣
0
v 
0
​
 : Proportional to the square of the velocity.

Gravity 
𝑔
g: Inversely proportional to the gravitational field strength.

Angle 
𝜃
θ: Drives a sinusoidal pattern 
sin
⁡
(
2
𝜃
)
sin(2θ).

Symmetry
𝑅
(
𝜃
)
=
𝑅
(
90
∘
−
𝜃
)
R(θ)=R(90 
∘
 −θ)
3. 🌍 Practical Applications
Sports (soccer, basketball)

Ballistics and military applications

Launch trajectories in aerospace

Realistic conditions may require accounting for:

Air resistance

Uneven terrain

Variable gravity

4. 💻 Python Simulation
Here's a simple simulation script:

python
Copy
Edit
import numpy as np
import matplotlib.pyplot as plt

# Constants
v0 = 50  # Initial speed in m/s
g = 9.81  # Gravity in m/s^2

# Angle array from 0 to 90 degrees
angles_deg = np.linspace(0, 90, 500)
angles_rad = np.radians(angles_deg)

# Compute range for each angle
ranges = (v0**2) * np.sin(2 * angles_rad) / g

# Plotting
plt.figure(figsize=(10, 6))
plt.plot(angles_deg, ranges)
plt.title("Projectile Range vs Angle of Projection")
plt.xlabel("Angle (degrees)")
plt.ylabel("Range (meters)")
plt.grid(True)
plt.axvline(45, color='red', linestyle='--', label='Maximum Range')
plt.legend()
plt.show()
5. 🔍 Limitations & Extensions
Limitations
Assumes no air resistance

Launch and landing at same height

No Coriolis effect or wind

Extensions
Use numerical integration to include drag

Simulate for varied terrain elevations

Monte Carlo simulations for uncertainty

