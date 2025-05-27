# Problem 1
Investigating the Range as a Function of the Angle of Projection
1. Theoretical Foundation
We begin with a classical model of projectile motion assuming:

Constant gravitational field 
𝑔
g

No air resistance

Flat launch and landing height

Initial speed 
𝑣
0
v 
0
​
 

Launch angle 
𝜃
θ

Equations of Motion
Breaking down the initial velocity:

𝑣
0
𝑥
=
𝑣
0
cos
⁡
𝜃
v 
0x
​
 =v 
0
​
 cosθ

𝑣
0
𝑦
=
𝑣
0
sin
⁡
𝜃
v 
0y
​
 =v 
0
​
 sinθ

Position as a function of time:

𝑥
(
𝑡
)
=
𝑣
0
cos
⁡
𝜃
⋅
𝑡
x(t)=v 
0
​
 cosθ⋅t

𝑦
(
𝑡
)
=
𝑣
0
sin
⁡
𝜃
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
 sinθ⋅t− 
2
1
​
 gt 
2
 

Time of Flight (until 
𝑦
(
𝑡
)
=
0
y(t)=0):
0
=
𝑣
0
sin
⁡
𝜃
⋅
𝑡
−
1
2
𝑔
𝑡
2
⇒
𝑡
=
2
𝑣
0
sin
⁡
𝜃
𝑔
0=v 
0
​
 sinθ⋅t− 
2
1
​
 gt 
2
 ⇒t= 
g
2v 
0
​
 sinθ
​
 
Range (Horizontal Distance):
𝑅
=
𝑥
(
𝑡
)
=
𝑣
0
cos
⁡
𝜃
⋅
2
𝑣
0
sin
⁡
𝜃
𝑔
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
R=x(t)=v 
0
​
 cosθ⋅ 
g
2v 
0
​
 sinθ
​
 = 
g
v 
0
2
​
 sin(2θ)
​
 
This is the classic range formula.

2. Analysis of the Range
Dependence on Angle:
Maximum range occurs at 
𝜃
=
45
∘
θ=45 
∘
  since 
sin
⁡
(
2
𝜃
)
sin(2θ) is maximal at 
90
∘
90 
∘
 .

The function is symmetric around 
45
∘
45 
∘
 : 
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

Influence of Other Parameters:
Initial velocity: Range is proportional to 
𝑣
0
2
v 
0
2
​
 

Gravitational acceleration: Range is inversely proportional to 
𝑔
g

3. Practical Applications
In real-world cases:

Uneven terrain: Final height 
ℎ
≠
0
h

=0 requires solving a quadratic in 
𝑡
t

Air resistance: Adds drag force 
𝐹
𝑑
=
−
𝑘
𝑣
F 
d
​
 =−kv, making equations nonlinear

Ballistics, sports, rocketry: All involve tuning angle/velocity to maximize distance or accuracy

4. Implementation (Python Script)
python
Copy
Edit
import numpy as np
import matplotlib.pyplot as plt

def compute_range(v0, g, theta_deg):
    theta_rad = np.radians(theta_deg)
    return (v0**2 * np.sin(2 * theta_rad)) / g

# Parameters
v0 = 30  # m/s
g = 9.81  # m/s²
angles = np.linspace(0, 90, 500)
ranges = [compute_range(v0, g, angle) for angle in angles]

# Plot
plt.figure(figsize=(10, 6))
plt.plot(angles, ranges, label=f'v₀ = {v0} m/s, g = {g} m/s²')
plt.title('Projectile Range vs. Angle of Projection')
plt.xlabel('Angle (degrees)')
plt.ylabel('Range (meters)')
plt.grid(True)
plt.legend()
plt.show()
5. Limitations & Extensions
Limitations:
Assumes no air resistance

Launch and landing heights are equal

Ignores wind, spin, or terrain

Extensions:
Air drag model: Use numerical integration (e.g., Runge-Kutta)

Non-flat terrain: Include different landing height

Wind or spin: Add lateral forces

6. Conclusion
This analysis shows the elegance of projectile motion and its strong dependence on projection angle. While idealized, the model is foundational for many applied physics problems, from sports to aerospace.