Problem 1: Investigating the Range as a Function of the Angle of Projection
Motivation
Projectile motion, while seemingly simple, provides a rich framework for exploring core principles of classical mechanics. The goal of this problem is to analyze how the range of a projectile depends on its angle of projection.

Despite the apparent simplicity of launching an object into the air, the underlying physics involves a delicate interplay between vertical and horizontal motion, governed by both linear and quadratic relationships. These relationships are influenced by parameters such as:

Initial velocity 
𝑣
0
v 
0
​
 

Gravitational acceleration 
𝑔
g

Launch height 
ℎ
h

These variables result in a wide variety of possible trajectories, modeling real-world phenomena such as the arc of a soccer ball or the path of a rocket.
Theoretical Background
Assume an object is launched from flat ground at velocity 
𝑣
0
v 
0
​
  and angle 
𝜃
θ (above the horizontal). Neglecting air resistance:

Equations of Motion:
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
 
Time of flight when the projectile returns to the ground 
(
𝑦
(
𝑡
)
=
0
)
(y(t)=0):

𝑡
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
t= 
g
2v 
0
​
 sin(θ)
​
 
Range Equation:
𝑅
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
R=v 
0
​
 cos(θ)⋅t= 
g
v 
0
2
​
 sin(2θ)
​
 
Python Simulation Example
python
Copy
Edit
import numpy as np
import matplotlib.pyplot as plt

# Parameters
v0 = 20  # initial velocity (m/s)
g = 9.81  # gravity (m/s^2)

# Angle range (0 to 90 degrees)
angles_deg = np.linspace(0, 90, 100)
angles_rad = np.radians(angles_deg)

# Compute range
ranges = (v0**2 * np.sin(2 * angles_rad)) / g

# Plotting
plt.figure(figsize=(10, 6))
plt.plot(angles_deg, ranges, color='blue', label=f'Initial Velocity = {v0} m/s')
plt.title('Projectile Range vs Angle of Projection')
plt.xlabel('Launch Angle (degrees)')
plt.ylabel('Range (meters)')
plt.grid(True)
plt.legend()
plt.show()
📈 Expected Output and Discussion
The maximum range occurs at 
𝜃
=
45
∘
θ=45 
∘
 .

The function 
𝑅
(
𝜃
)
R(θ) is symmetric about 45°, i.e., 
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
 −θ).

Higher initial velocities result in longer ranges.

This model assumes no air resistance and launch/landing at equal heights.

 Limitations and Extensions
Limitations:

No air drag or wind.

Assumes flat terrain.

Possible Extensions:

Add launch height 
ℎ
h: modifies the time of flight.

Include air resistance for a more realistic model.

Simulate launch and landing at different heights or sloped surfaces.

 Deliverables
A Markdown or Jupyter Notebook including:

Theoretical derivations and equations.

Python script implementing simulation.

Graphs of range vs angle under varying parameters.

Discussion of model limitations and possible improvements.

