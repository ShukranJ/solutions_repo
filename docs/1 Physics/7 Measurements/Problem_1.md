# Problem 1  
## Measuring Earth's Gravitational Acceleration with a Pendulum

### Motivation

The acceleration $g$ due to gravity is a fundamental constant that influences a wide range of physical phenomena. Measuring $g$ accurately is crucial for understanding gravitational interactions, designing structures, and conducting experiments in various fields. One classic method for determining $g$ is through the oscillations of a simple pendulum, where the period of oscillation depends on the local gravitational field.

---

### Task

Measure the acceleration $g$ due to gravity using a pendulum and analyze in detail the uncertainties in the measurements.

This exercise emphasizes rigorous measurement practices, uncertainty analysis, and their role in experimental physics.

---

### Procedure

#### 1. Materials:
- A string (1 or 1.5 meters long)
- A small weight (e.g., bag of coins, bag of sugar, key chain) mounted on the string
- Stopwatch (or smartphone timer)
- Ruler or measuring tape

#### 2. Setup:
- Attach the weight to the string and fix the other end to a sturdy support.
- Measure the length of the pendulum, $L$, from the suspension point to the center of the weight using a ruler or measuring tape.  
- Record the resolution of the measuring tool and calculate the uncertainty as half the resolution, $u_L = \frac{\text{resolution}}{2}$.

#### 3. Data Collection:
- Displace the pendulum slightly (<15°) and release it.
- Measure the time for 10 full oscillations ($T_{10}$) and repeat this process 10 times. Record all 10 measurements.
- Calculate the mean time for 10 oscillations ($\bar{T}_{10}$) and the standard deviation ($s$).
- Determine the uncertainty in the mean time as:  
$$
u_{\bar{T}_{10}} = \frac{s}{\sqrt{10}}
$$

---

### Calculations

#### 1. Calculate the period $T$:  
$$
T = \frac{\bar{T}_{10}}{10} \quad,\quad u_T = \frac{u_{\bar{T}_{10}}}{10}
$$

#### 2. Determine $g$:  
$$
g = \frac{4\pi^2 L}{T^2}
$$

#### 3. Propagate uncertainties:  
$$
u_g = g \sqrt{\left(\frac{u_L}{L}\right)^2 + \left(2 \frac{u_T}{T}\right)^2}
$$

---

### Sample Data

| Trial # | $T_{10}$ (s) |
|---------|--------------|
| 1       | 20.15        |
| 2       | 20.20        |
| 3       | 20.10        |
| 4       | 20.18        |
| 5       | 20.22        |
| 6       | 20.25        |
| 7       | 20.17        |
| 8       | 20.19        |
| 9       | 20.13        |
| 10      | 20.21        |

---

### Example Calculations

- Mean time for 10 oscillations:  
$$
\bar{T}_{10} = \frac{1}{10} \sum_{i=1}^{10} T_{10,i} = 20.18 \text{ s}
$$

- Standard deviation:  
$$
s = \sqrt{\frac{1}{9} \sum_{i=1}^{10} (T_{10,i} - \bar{T}_{10})^2} = 0.05 \text{ s}
$$

- Uncertainty in mean time:  
$$
u_{\bar{T}_{10}} = \frac{s}{\sqrt{10}} = \frac{0.05}{3.16} \approx 0.016 \text{ s}
$$

- Period and uncertainty:  
$T = \frac{\bar{T}_{10}}{10} = 2.018$ s, and  
$u_T = \frac{u_{\bar{T}_{10}}}{10} = 0.0016$ s

- Pendulum length and uncertainty:  
$L = 1.00$ m,  
$u_L = \frac{0.01}{2} = 0.005$ m

- Calculate $g$:  
$$
g = \frac{4\pi^2 L}{T^2} = \frac{4 \times (3.1416)^2 \times 1.00}{(2.018)^2} \approx 9.70 \, m/s^2
$$

- Propagate uncertainty:  
$$
u_g = g \sqrt{\left(\frac{u_L}{L}\right)^2 + \left(2 \frac{u_T}{T}\right)^2} = 9.70 \times \sqrt{(0.005)^2 + \left(2 \times \frac{0.0016}{2.018}\right)^2} \approx 0.05 \, m/s^2
$$

---

### Discussion

- The measured value $g = 9.70 \pm 0.05 \, m/s^2$ is close to the standard $9.81 \, m/s^2$, with slight deviations likely due to experimental uncertainties.
- Measurement resolution for length ($\pm 0.005$ m) contributes less uncertainty compared to timing.
- Timing variability significantly impacts the uncertainty in $g$, as timing uncertainty enters the formula squared.
- Assumptions include small oscillation angles (<15°) and neglecting air resistance and friction.
- Limitations include manual stopwatch reaction times and difficulty precisely measuring the pendulum length to the center of mass.

