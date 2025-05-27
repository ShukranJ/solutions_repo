# Problem 2: Investigating the Dynamics of a Forced Damped Pendulum

## Motivation

The forced damped pendulum is a captivating example of a physical system with intricate behavior resulting from the interplay of damping, restoring forces, and external driving forces. By introducing both damping and external periodic forcing, the system demonstrates a transition from simple harmonic motion to a rich spectrum of dynamics, including resonance, chaos, and quasiperiodic behavior.

These phenomena are foundational to understanding complex real-world systems such as:
- Driven oscillators in engineering,
- Mechanical structures under periodic stress,
- Climate systems,
- Electrical RLC circuits.

By systematically varying parameters like the damping coefficient, driving amplitude, and frequency, the pendulum's behavior ranges from regular, synchronized oscillations to chaotic and unpredictable motion. This task aims to analyze and visualize these behaviors through theory and simulation.

---

## 1. Theoretical Foundation

We begin with the governing differential equation of the forced damped pendulum:

\[
\frac{d^2\theta}{dt^2} + \gamma \frac{d\theta}{dt} + \omega_0^2 \sin(\theta) = A \cos(\omega t)
\]

Where:
- \( \theta(t) \) is the angular displacement,
- \( \gamma \) is the damping coefficient,
- \( \omega_0 \) is the natural frequency,
- \( A \) is the driving amplitude,
- \( \omega \) is the driving frequency.

### Small-Angle Approximation

For small angles (\( \theta \ll 1 \)), we approximate \( \sin(\theta) \approx \theta \), leading to a linearized version:

\[
\frac{d^2\theta}{dt^2} + \gamma \frac{d\theta}{dt} + \omega_0^2 \theta = A \cos(\omega t)
\]

This can be solved analytically to explore resonance behavior and energy dynamics.

---

## 2. Analysis of Dynamics

### Parameter Influence
We examine how the following affect the system:
- **Damping coefficient** \( \gamma \)
- **Driving amplitude** \( A \)
- **Driving frequency** \( \omega \)

### Regular vs. Chaotic Motion
- Identify ranges of parameters that result in **periodic**, **quasiperiodic**, and **chaotic** motion.
- Use **phase space** and **Poincaré sections** to visualize transitions between behaviors.

---

## 3. Practical Applications

The forced damped pendulum models real-world systems such as:
- **Energy harvesting** devices (piezoelectric cantilevers),
- **Suspension bridges** subjected to wind or traffic,
- **Driven RLC circuits** in electronics,
- **Biomechanical systems** like human gait under periodic external forces.

---

## 4. Implementation (Python Simulation)

### Simulation Plan
- Use numerical solvers (e.g., **Runge-Kutta 4th order**) to simulate nonlinear motion.
- Vary initial conditions and parameters.
- Plot:
  - Time series \( \theta(t) \),
  - Phase portraits (\( \theta \) vs. \( \dot{\theta} \)),
  - Poincaré sections,
  - Bifurcation diagrams.

### Example Code Snippet
```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp

# Parameters
gamma = 0.5
omega0 = 1.5
A = 1.2
omega = 2.0

def pendulum(t, y):
    theta, dtheta = y
    return [dtheta, -gamma * dtheta - omega0**2 * np.sin(theta) + A * np.cos(omega * t)]

# Initial condition and time span
y0 = [0.1, 0]
t_span = (0, 50)
t_eval = np.linspace(t_span[0], t_span[1], 1000)

# Solve
sol = solve_ivp(pendulum, t_span, y0, t_eval=t_eval)

# Plot
plt.plot(sol.t, sol.y[0])
plt.title('Forced Damped Pendulum: θ(t)')
plt.xlabel('Time (s)')
plt.ylabel('Angle θ (rad)')
plt.grid(True)
plt.show()

# Problem 2: Investigating the Dynamics of a Forced Damped Pendulum

## Motivation

The forced damped pendulum is a captivating example of a physical system with intricate behavior resulting from the interplay of damping, restoring forces, and external driving forces. By introducing both damping and external periodic forcing, the system demonstrates a transition from simple harmonic motion to a rich spectrum of dynamics, including resonance, chaos, and quasiperiodic behavior.

These phenomena are foundational to understanding complex real-world systems such as:
- Driven oscillators in engineering,
- Mechanical structures under periodic stress,
- Climate systems,
- Electrical RLC circuits.

By systematically varying parameters like the damping coefficient, driving amplitude, and frequency, the pendulum's behavior ranges from regular, synchronized oscillations to chaotic and unpredictable motion. This task aims to analyze and visualize these behaviors through theory and simulation.

---

## 1. Theoretical Foundation

We begin with the governing differential equation of the forced damped pendulum:

\[
\frac{d^2\theta}{dt^2} + \gamma \frac{d\theta}{dt} + \omega_0^2 \sin(\theta) = A \cos(\omega t)
\]

Where:
- \( \theta(t) \) is the angular displacement,
- \( \gamma \) is the damping coefficient,
- \( \omega_0 \) is the natural frequency,
- \( A \) is the driving amplitude,
- \( \omega \) is the driving frequency.

### Small-Angle Approximation

For small angles (\( \theta \ll 1 \)), we approximate \( \sin(\theta) \approx \theta \), leading to a linearized version:

\[
\frac{d^2\theta}{dt^2} + \gamma \frac{d\theta}{dt} + \omega_0^2 \theta = A \cos(\omega t)
\]

This can be solved analytically to explore resonance behavior and energy dynamics.

---

## 2. Analysis of Dynamics

### Parameter Influence
We examine how the following affect the system:
- **Damping coefficient** \( \gamma \)
- **Driving amplitude** \( A \)
- **Driving frequency** \( \omega \)

### Regular vs. Chaotic Motion
- Identify ranges of parameters that result in **periodic**, **quasiperiodic**, and **chaotic** motion.
- Use **phase space** and **Poincaré sections** to visualize transitions between behaviors.

---

## 3. Practical Applications

The forced damped pendulum models real-world systems such as:
- **Energy harvesting** devices (piezoelectric cantilevers),
- **Suspension bridges** subjected to wind or traffic,
- **Driven RLC circuits** in electronics,
- **Biomechanical systems** like human gait under periodic external forces.

---

## 4. Implementation (Python Simulation)

### Simulation Plan
- Use numerical solvers (e.g., **Runge-Kutta 4th order**) to simulate nonlinear motion.
- Vary initial conditions and parameters.
- Plot:
  - Time series \( \theta(t) \),
  - Phase portraits (\( \theta \) vs. \( \dot{\theta} \)),
  - Poincaré sections,
  - Bifurcation diagrams.

### Example Code Snippet
```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp

# Parameters
gamma = 0.5
omega0 = 1.5
A = 1.2
omega = 2.0

def pendulum(t, y):
    theta, dtheta = y
    return [dtheta, -gamma * dtheta - omega0**2 * np.sin(theta) + A * np.cos(omega * t)]

# Initial condition and time span
y0 = [0.1, 0]
t_span = (0, 50)
t_eval = np.linspace(t_span[0], t_span[1], 1000)

# Solve
sol = solve_ivp(pendulum, t_span, y0, t_eval=t_eval)

# Plot
plt.plot(sol.t, sol.y[0])
plt.title('Forced Damped Pendulum: θ(t)')
plt.xlabel('Time (s)')
plt.ylabel('Angle θ (rad)')
plt.grid(True)
plt.show()
