# 🌊 Waves — Interference Patterns on a Water Surface

## 🔍 Problem 1: Interference Patterns on a Water Surface

### 🧠 **Motivation**
Interference occurs when waves from different sources overlap, creating new patterns. On a water surface, this is seen when ripples from different points meet, forming areas where waves reinforce or cancel each other out. 

This experiment helps us visually understand key concepts in wave physics, such as coherence, phase difference, and constructive/destructive interference.

---

## 🎯 Task

Analyze the interference patterns formed on the water surface due to the superposition of waves emitted from point sources placed at the vertices of a **regular polygon**.

---

## 🛠️ Steps to Follow

### 1. Select a Regular Polygon
We choose a **square** with 4 point sources at the vertices.

### 2. Position the Sources
The sources are placed evenly on a circle (radius = 3 units), forming a square.

### 3. Wave Equation
Each wave from a source \((x_i, y_i)\) is given by:

\[
\psi_i(x, y, t) = A \cdot \cos(k r_i - \omega t + \phi)
\]

Where:
- \( A \): amplitude
- \( k = \frac{2\pi}{\lambda} \): wave number
- \( \omega = 2\pi f \): angular frequency
- \( r_i = \sqrt{(x - x_i)^2 + (y - y_i)^2} \): distance from source to point
- \( \phi \): initial phase (same for all sources)

### 4. Superposition of Waves

\[
\psi_{\text{total}}(x, y, t) = \sum_{i=1}^{N} \psi_i(x, y, t)
\]

### 5. Analyze Interference
We visualize the total wave field \(\psi_{\text{total}}(x, y, t)\) to identify constructive and destructive interference regions.

---

## 🐍 Python Simulation Code

```python
import numpy as np
import matplotlib.pyplot as plt

# Wave parameters
A = 1.0            # Amplitude
wavelength = 1.0   # Wavelength λ
frequency = 1.0    # Frequency f
phi = 0            # Initial phase
N = 4              # Number of sources (square)
radius = 3         # Radius of the polygon

# Derived parameters
k = 2 * np.pi / wavelength  # Wave number
omega = 2 * np.pi * frequency  # Angular frequency

# Define polygon vertices
angles = np.linspace(0, 2 * np.pi, N, endpoint=False)
sources = [(radius * np.cos(a), radius * np.sin(a)) for a in angles]

# Create grid
x = np.linspace(-6, 6, 500)
y = np.linspace(-6, 6, 500)
X, Y = np.meshgrid(x, y)
t = 0  # Snapshot at t=0

# Superposition of waves
Z = np.zeros_like(X)
for (x0, y0) in sources:
    r = np.sqrt((X - x0)**2 + (Y - y0)**2)
    Z += A * np.cos(k * r - omega * t + phi)

# Visualization
plt.figure(figsize=(8, 6))
plt.contourf(X, Y, Z, levels=100, cmap='RdBu')
plt.colorbar(label='Wave Displacement')
plt.title('Interference Pattern from 4 Point Sources (Square)')
plt.xlabel('x')
plt.ylabel('y')
plt.axis('equal')
plt.show()
