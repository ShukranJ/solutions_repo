# Problem 1
# Gravity

## Problem 1: Orbital Period and Orbital Radius

### Motivation

The relationship between the square of the orbital period and the cube of the orbital radius, known as **Kepler's Third Law**, is a cornerstone of celestial mechanics. This fundamental law enables the prediction of planetary motions and helps us understand gravitational interactions across the universe. By exploring this principle, we connect classical mechanics with observable astrophysical systems, such as satellite trajectories and planetary orbits.

---

### Task

1. **Theoretical Derivation**
   - Derive Kepler's Third Law for circular orbits:
     \[
     T^2 \propto r^3
     \]
     using Newton's Law of Gravitation and centripetal force.

2. **Astronomical Implications**
   - Discuss how this law is used to:
     - Determine planetary masses
     - Estimate distances between celestial bodies
     - Understand orbital stability

3. **Real-World Examples**
   - Analyze orbits such as:
     - The Moon orbiting Earth
     - Planetary orbits in the Solar System
     - Artificial satellites (e.g., GPS, ISS)

4. **Computational Simulation**
   - Implement a Python simulation to:
     - Calculate orbital periods for various radii
     - Visualize circular orbits
     - Plot \( T^2 \) vs \( r^3 \) and verify linearity

---

### Deliverables

- 📄 **Markdown Report**
  - Includes derivation of Kepler’s Third Law from Newtonian mechanics
  - Discussion of astrophysical implications and extensions to elliptical orbits

- 🐍 **Python Script or Jupyter Notebook**
  - Simulates circular orbits using gravitational formulas
  - Computes and plots the relationship between period and radius
  - Validates \( T^2 \propto r^3 \)

- 📊 **Visualizations**
  - Diagrams of orbital paths
  - Log-log or linear plots of \( T^2 \) vs. \( r^3 \)
  - Example comparisons using real astronomical data (e.g., Earth-Moon system)

- 🔍 **Discussion Section**
  - How Kepler's Law holds in elliptical orbits
  - Generalization to systems beyond the Solar System
  - Assumptions and limitations of circular orbit modeling

---

### Hints and Resources

- Use Newton’s Law of Gravitation:
  \[
  F = \frac{G M m}{r^2}
  \]
  and equate it with centripetal force:
  \[
  F = \frac{m v^2}{r}
  \]

- Solve for \( T \) using:
  \[
  T = \frac{2 \pi r}{v}
  \]

- Plot using libraries like Matplotlib and compute with NumPy.

- Use SI units (mass in kg, radius in meters, time in seconds) for consistency.

- Optionally analyze deviations from linearity due to eccentricity or external forces.

---

