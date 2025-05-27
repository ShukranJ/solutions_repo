# Problem 1
 Interference Patterns on a Water Surface
1. Chosen Polygon
We'll use a square (4-point sources) as an example. You can easily switch to a triangle, pentagon, etc.

2. Wave Equation
For each source at position 
(
𝑥
𝑖
,
𝑦
𝑖
)
(x 
i
​
 ,y 
i
​
 ), the wave at a point 
(
𝑥
,
𝑦
)
(x,y) and time 
𝑡
t is:

𝜓
𝑖
(
𝑥
,
𝑦
,
𝑡
)
=
𝐴
⋅
cos
⁡
(
𝑘
𝑟
𝑖
−
𝜔
𝑡
+
𝜙
)
ψ 
i
​
 (x,y,t)=A⋅cos(kr 
i
​
 −ωt+ϕ)
Where:

𝐴
A: amplitude (same for all)

𝑘
=
2
𝜋
𝜆
k= 
λ
2π
​
 : wave number

𝜔
=
2
𝜋
𝑓
ω=2πf: angular frequency

𝑟
𝑖
=
(
𝑥
−
𝑥
𝑖
)
2
+
(
𝑦
−
𝑦
𝑖
)
2
r 
i
​
 = 
(x−x 
i
​
 ) 
2
 +(y−y 
i
​
 ) 
2
 
​
 : distance from source 
𝑖
i

𝜙
ϕ: initial phase (same for all sources due to coherence)

3. Superposition
Total displacement:

𝜓
total
(
𝑥
,
𝑦
,
𝑡
)
=
∑
𝑖
=
1
𝑁
𝜓
𝑖
(
𝑥
,
𝑦
,
𝑡
)
ψ 
total
​
 (x,y,t)= 
i=1
∑
N
​
 ψ 
i
​
 (x,y,t)

Python Code Outline
import numpy as np
import matplotlib.pyplot as plt

# Parameters
A = 1.0         # amplitude
wavelength = 1  # wavelength (λ)
frequency = 1   # frequency (f)
phi = 0         # initial phase
N = 4           # number of sources (square)
radius = 3      # radius of the polygon

# Derived parameters
k = 2 * np.pi / wavelength
omega = 2 * np.pi * frequency

# Create the polygon vertices
angles = np.linspace(0, 2 * np.pi, N, endpoint=False)
sources = [(radius * np.cos(a), radius * np.sin(a)) for a in angles]

# Grid setup
x = np.linspace(-6, 6, 500)
y = np.linspace(-6, 6, 500)
X, Y = np.meshgrid(x, y)
t = 0  # fixed time

# Compute the total wave
Z = np.zeros_like(X)
for (x0, y0) in sources:
    r = np.sqrt((X - x0)**2 + (Y - y0)**2)
    Z += A * np.cos(k * r - omega * t + phi)

# Plot
plt.figure(figsize=(8, 6))
plt.contourf(X, Y, Z, levels=100, cmap='RdBu')
plt.colorbar(label='Wave Displacement')
plt.title('Interference Pattern from 4 Point Sources (Square)')
plt.xlabel('x')
plt.ylabel('y')
plt.axis('equal')
plt.show()
Explanation of Interference Patterns
Constructive Interference occurs where the crests (or troughs) from multiple sources align, resulting in higher amplitude.

Destructive Interference happens where crests meet troughs, cancelling out the displacement.

The pattern reflects the symmetry of the polygon, and periodic regions of constructive and destructive interference form.