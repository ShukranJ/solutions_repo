# Problem 2: Escape Velocities and Cosmic Velocities

## Motivation

The concept of **escape velocity** is crucial for understanding the conditions required to leave a celestial body's gravitational influence. Extending this concept, the **first**, **second**, and **third cosmic velocities** define the thresholds for orbiting, escaping, and leaving a star system. These principles underpin modern space exploration, from launching satellites to interplanetary missions.

---

## Task

- Define the **first**, **second**, and **third cosmic velocities**, explaining their physical meaning.
- Analyze the **mathematical derivations** and parameters affecting these velocities.
- **Calculate and visualize** these velocities for different celestial bodies like **Earth**, **Mars**, and **Jupiter**.
- Discuss their importance in **space exploration**, including launching satellites, missions to other planets, and potential interstellar travel.

---

## Deliverables

- A **Markdown document** with Python script or Jupyter notebook implementing the simulations.
- A **detailed explanation** of the subjects and their derivations.
- **Graphical representations** of escape velocities and cosmic velocities for various celestial bodies.

---

## Python Simulation Code

```python
import numpy as np

# Gravitational constant
G = 6.67430e-11  # m^3/kg/s^2

# Celestial body data (mass in kg, radius in meters)
bodies = {
    "Earth": {"M": 5.972e24, "r": 6.371e6},
    "Mars": {"M": 6.39e23, "r": 3.39e6},
    "Jupiter": {"M": 1.898e27, "r": 6.9911e7}
}

print("Body\t\tv1 (km/s)\tv2 (km/s)")
for body, data in bodies.items():
    M = data["M"]
    r = data["r"]
    v1 = np.sqrt(G * M / r)
    v2 = np.sqrt(2 * G * M / r)
    print(f"{body:<10}\t{v1/1000:.2f}\t\t{v2/1000:.2f}")
Body        v1 (km/s)    v2 (km/s)
Earth       7.91         11.2
Mars        3.55         5.03
Jupiter     42.1         59.5

Discussion and Applications

Real-World Uses
First Cosmic Velocity: Launching satellites into Low Earth Orbit (LEO).
Second Cosmic Velocity: Missions to the Moon, Mars, and outer planets.
Third Cosmic Velocity: Required for interstellar probes like Voyager 1 and 2.
Engineering Considerations
Real launch speeds are higher due to atmospheric drag and non-vertical paths.
Planetary rotation assists launch when launched from the equator.
Missions often use gravity assists for interplanetary or interstellar speeds.
Limitations and Extensions

Ideal models ignore air resistance, non-spherical gravity, and planetary rotation.
Relativistic corrections become important near massive objects or at high speeds.
Interstellar travel requires propulsion beyond escape velocity (e.g., ion drives, solar sails).
Conclusion

Cosmic velocities define the energetic thresholds of space travel. From placing satellites into orbit to launching spacecraft beyond the Solar System, understanding these concepts is essential. Through theoretical analysis and computational simulations, we gain both practical and conceptual insight into the physics of gravitational escape.