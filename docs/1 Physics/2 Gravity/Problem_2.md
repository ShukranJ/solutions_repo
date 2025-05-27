# Problem 2: Escape Velocities and Cosmic Velocities

## Motivation

Escape velocity is a fundamental concept in celestial mechanics and space exploration. It determines the minimum velocity needed for an object to overcome a planet's or star's gravitational field. Expanding on this, the three **cosmic velocities** mark critical thresholds in orbital mechanics:

- **First Cosmic Velocity**: Required for circular orbital motion near the surface.
- **Second Cosmic Velocity**: Required to escape the gravitational influence of a planet.
- **Third Cosmic Velocity**: Required to escape the gravitational pull of the entire star system.

These velocities are essential in planning missions for satellites, interplanetary probes, and future interstellar spacecraft.

---

## Definitions

### First Cosmic Velocity (Orbital Velocity)
The minimum speed required for a circular orbit just above the surface of a celestial body:

\[
v_1 = \sqrt{\frac{G M}{r}}
\]

Where:
- \( G \) is the gravitational constant \( \approx 6.674 \times 10^{-11} \, \text{Nm}^2/\text{kg}^2 \)
- \( M \) is the mass of the celestial body
- \( r \) is the radius from the center of mass (usually the surface radius)

---

### Second Cosmic Velocity (Escape Velocity)
The speed required to escape a planet’s gravitational field without additional propulsion:

\[
v_2 = \sqrt{2} \cdot v_1 = \sqrt{\frac{2GM}{r}}
\]

---

### Third Cosmic Velocity (Stellar Escape Velocity)
The velocity needed to escape the Sun’s gravitational influence from Earth’s orbit:

\[
v_3 = \sqrt{\frac{2 G M_{\odot}}{r_{\text{Earth orbit}}}} \approx 42.1 \, \text{km/s}
\]

This is a simplified model assuming a direct escape path and no planetary assists.

---

## Derivations and Mathematical Background

From Newton’s Law of Universal Gravitation:

\[
F = \frac{G M m}{r^2}
\]

Using Newton's second law and equating gravitational force to centripetal force for circular orbit:

\[
\frac{m v^2}{r} = \frac{G M m}{r^2} \Rightarrow v_1 = \sqrt{\frac{GM}{r}}
\]

For escape velocity (conservation of energy):

\[
\frac{1}{2}mv^2 = \frac{GMm}{r} \Rightarrow v_2 = \sqrt{\frac{2GM}{r}}
\]

The third cosmic velocity depends on the body’s position relative to the Sun and is often computed based on heliocentric energy conditions.

---

### Planetary Data

```python
import numpy as np
import matplotlib.pyplot as plt

# Gravitational constant
G = 6.674e-11  # N·m²/kg²

# Planetary mass (kg) and radius (m)
bodies = {
    "Earth":   {"M": 5.972e24, "r": 6.371e6},
    "Mars":    {"M": 6.39e23,  "r": 3.39e6},
    "Jupiter": {"M": 1.898e27, "r": 6.99e7}
}

results = {}

# Compute v1 and v2 for each body
for body, data in bodies.items():
    M = data["M"]
    r = data["r"]
    v1 = np.sqrt(G * M / r)            # First Cosmic Velocity (orbital)
    v2 = np.sqrt(2 * G * M / r)        # Second Cosmic Velocity (escape)
    results[body] = {
        "v1 (km/s)": v1 / 1000,
        "v2 (km/s)": v2 / 1000
    }

# Print results
for body in results:
    print(f"{body} - First Cosmic Velocity: {results[body]['v1 (km/s)']:.2f} km/s")
    print(f"{body} - Second Cosmic Velocity: {results[body]['v2 (km/s)']:.2f} km/s\n")

## Sample Output (Approximate)

| Body     | v₁ (km/s) | v₂ (km/s) |
|----------|------------|------------|
| Earth    | 7.91       | 11.2       |
| Mars     | 3.55       | 5.03       |
| Jupiter  | 42.1       | 59.5       |

- **v₁** = First Cosmic Velocity (orbital speed at surface level)
- **v₂** = Second Cosmic Velocity (escape speed from surface)

---

## Discussion and Applications

### Real-World Uses

- **First Cosmic Velocity**  
  Used to place satellites into **Low Earth Orbit (LEO)** and other orbital paths around a planet.

- **Second Cosmic Velocity**  
  Required for **lunar and interplanetary missions**, such as going to Mars, Venus, or outer planets.

- **Third Cosmic Velocity**  
  Needed to **leave the solar system**, used by **Voyager 1 and 2** and other deep-space probes.

### Engineering Considerations

- **Atmospheric Drag**  
  In real-world conditions, launch velocities must account for **air resistance**, which is neglected in idealized models.

- **Planetary Rotation**  
  Launching near the **equator** takes advantage of the planet’s rotational speed to reduce fuel consumption.

- **Gravity Assists**  
  **Slingshot maneuvers** around planets are commonly used to achieve higher velocities for **interplanetary or interstellar travel**.

---

## Limitations and Extensions

- **Ideal Assumptions**  
  The basic model assumes:
  - Vacuum (no atmospheric drag)
  - Spherical, uniform mass distributions
  - Non-rotating bodies

- **Relativistic Effects**  
  Near very **massive bodies** (e.g., black holes), **general relativity** replaces Newtonian gravity.

- **Advanced Propulsion**  
  Reaching the **third cosmic velocity** and beyond requires:
  - **Ion thrusters**
  - **Solar sails**
  - **Nuclear propulsion**

---

## Conclusion

Cosmic velocities define the **minimum energy requirements** for various classes of space missions:
- From launching satellites and exploring planets
- To escaping Earth’s gravity entirely
- And ultimately, traveling beyond the solar system

Understanding these velocities helps engineers and scientists **design feasible missions**, optimize fuel efficiency, and explore the **limits of human space exploration**. Through both **analytical equations** and **numerical simulations**, we gain powerful insights into the physics that govern motion in our universe.


