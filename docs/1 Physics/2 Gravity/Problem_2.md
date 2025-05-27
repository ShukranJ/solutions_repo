# Problem 2
# Gravity

## Problem 2: Escape Velocities and Cosmic Velocities

### Motivation

The concept of **escape velocity** is fundamental in understanding how objects can overcome gravitational pull. Expanding this idea, the **first, second, and third cosmic velocities** describe the thresholds for:
- Achieving stable orbit,
- Escaping a planet’s gravity,
- Leaving a star system altogether.

These velocities form the backbone of **modern space missions**, helping design trajectories for satellites, planetary probes, and future interstellar exploration.

---

### Task

1. **Definition and Physical Meaning**
   - Define:
     - **First Cosmic Velocity**: Minimum speed for a circular orbit near the surface.
     - **Second Cosmic Velocity**: Speed needed to escape the gravitational field.
     - **Third Cosmic Velocity**: Speed to escape the gravity of the entire star system.
   - Explain the physical interpretation of each velocity in the context of Newtonian mechanics.

2. **Mathematical Derivation**
   - Derive the expressions:
     - \( v_1 = \sqrt{\frac{G M}{r}} \)
     - \( v_2 = \sqrt{2} \cdot v_1 = \sqrt{\frac{2GM}{r}} \)
     - \( v_3 \) (approximation depending on solar system escape conditions)
   - Explore the variables that affect these velocities: mass \( M \), radius \( r \), gravitational constant \( G \)

3. **Computation and Visualization**
   - Calculate these velocities for celestial bodies:
     - Earth
     - Mars
     - Jupiter
   - Create comparative visualizations (bar charts or line plots)

4. **Applications in Space Missions**
   - Discuss how these velocities relate to:
     - Low Earth orbit satellites
     - Interplanetary spacecraft (e.g., Mars rovers)
     - Potential missions beyond the solar system

---

### Deliverables

- 📄 **Markdown Report**
  - Definitions and theoretical background of cosmic velocities
  - Derivations from Newton’s Law of Gravitation and Energy Conservation
  - Explanation of how velocity thresholds relate to mission design

- 🐍 **Python Script or Jupyter Notebook**
  - Function to calculate \( v_1 \), \( v_2 \), and approximate \( v_3 \)
  - Simulation and plots comparing escape velocities of different planets

- 📊 **Visualizations**
  - Bar charts of escape velocities for Earth, Mars, Jupiter
  - Annotations to show physical implications (e.g., why it's easier to launch from Mars)

- 🚀 **Discussion Section**
  - Relevance to real space missions (e.g., Voyager, Artemis, SpaceX launches)
  - Limitations of classical models (neglecting atmosphere, rotation)
  - Extensions to relativistic and multi-body gravitational systems

---

### Hints and Resources

- Use the gravitational constant:
  \[
  G = 6.674 \times 10^{-11} \, \text{N·m}^2/\text{kg}^2
  \]
- Use mass and radius values of:
  - Earth: \( M = 5.972 \times 10^{24} \, \text{kg}, \, r = 6.371 \times 10^6 \, \text{m} \)
  - Mars: \( M = 6.39 \times 10^{23} \, \text{kg}, \, r = 3.39 \times 10^6 \, \text{m} \)
  - Jupiter: \( M = 1.898 \times 10^{27} \, \text{kg}, \, r = 6.99 \times 10^7 \, \text{m} \)

- Reference:
  - Newton’s Law of Universal Gravitation
  - Kinetic and potential energy equivalence for escape velocity
  - Space mission data from NASA/JPL

---

