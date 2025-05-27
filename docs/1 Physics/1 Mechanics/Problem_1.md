# Problem 1
Investigating the Range as a Function of the Angle of Projection
1. Theoretical Foundation
Deriving the Governing Equations of Motion
We begin by deriving the governing equations of motion from fundamental principles. We assume a projectile launched from the origin (0,0) with an initial velocity v 
0
​
  at an angle θ with respect to the horizontal. The only force acting on the projectile is gravity, acting downwards. We neglect air resistance.

The acceleration due to gravity is g, and it acts in the negative y direction. Thus, the acceleration vector is:
a

 =(a 
x
​
 ,a 
y
​
 )=(0,−g)

To find the velocity, we integrate the acceleration with respect to time:
v

 (t)=∫ 
a

 dt=(C 
1
​
 ,−gt+C 
2
​
 )

The initial velocity components are:
v 
0x
​
 =v 
0
​
 cosθ

v 
0y
​
 =v 
0
​
 sinθ

At t=0,  
v

 (0)=(v 
0x
​
 ,v 
0y
​
 ). Therefore, C 
1
​
 =v 
0
​
 cosθ and C 
2
​
 =v 
0
​
 sinθ.
So, the velocity components as a function of time are:
v 
x
​
 (t)=v 
0
​
 cosθ

v 
y
​
 (t)=v 
0
​
 sinθ−gt

To find the position, we integrate the velocity with respect to time:
r

 (t)=∫ 
v

 (t)dt=(v 
0
​
 tcosθ+C 
3
​
 ,v 
0
​
 tsinθ− 
2
1
​
 gt 
2
 +C 
4
​
 )

At t=0, the initial position is (0,0). Therefore, C 
3
​
 =0 and C 
4
​
 =0.
So, the position components as a function of time are:
x(t)=v 
0
​
 tcosθ

y(t)=v 
0
​
 tsinθ− 
2
1
​
 gt 
2
 

These are the governing equations of motion for a projectile launched from the origin in a uniform gravitational field.

Family of Solutions and Initial Conditions
The equations above represent a family of solutions, each determined by a specific set of initial conditions:

Initial Velocity (v 
0
​
 ): This parameter determines the magnitude of the initial velocity vector. A larger v 
0
​
  generally leads to a greater range and maximum height.
Angle of Projection (θ): This parameter determines the direction of the initial velocity vector. As we will see, it plays a crucial role in determining the horizontal range.
Gravitational Acceleration (g): This is typically considered constant on Earth, but it can vary on other celestial bodies. A smaller g would result in a longer flight time and greater range for the same initial conditions.
Initial Height (y 
0
​
 ): While our derivation assumed y 
0
​
 =0, the equations can be easily adapted for a launch from a non-zero initial height by setting y(0)=y 
0
​
 . This would add y 
0
​
  to the y(t) equation.
Each unique combination of these parameters defines a distinct trajectory for the projectile.

2. Analysis of the Range
The horizontal range (R) is the total horizontal distance traveled by the projectile when it returns to its initial vertical height (or lands on the ground, assuming flat terrain). Assuming the projectile starts and ends at y=0, we can find the time of flight (T) by setting y(t)=0:

v 
0
​
 Tsinθ− 
2
1
​
 gT 
2
 =0

T(v 
0
​
 sinθ− 
2
1
​
 gT)=0

This gives two solutions: T=0 (the launch instant) and:
v 
0
​
 sinθ− 
2
1
​
 gT=0

T= 
g
2v 
0
​
 sinθ
​
 

Now, substitute this time of flight into the horizontal position equation to find the range:
R=x(T)=v 
0
​
 Tcosθ

R=v 
0
​
 ( 
g
2v 
0
​
 sinθ
​
 )cosθ

R= 
g
2v 
0
2
​
 sinθcosθ
​
 

Using the trigonometric identity sin(2θ)=2sinθcosθ, we can simplify the range equation:
R= 
g
v 
0
2
​
 sin(2θ)
​
 

How the Horizontal Range Depends on the Angle of Projection
From the equation R= 
g
v 
0
2
​
 sin(2θ)
​
 , we can observe the following:

Maximum Range: The range is maximized when sin(2θ) is maximized. The maximum value of sin(2θ) is 1, which occurs when 2θ=90 
∘
 , or θ=45 
∘
 . Thus, for a given initial velocity, the maximum range is achieved at an angle of 45 
∘
 .
Symmetry: The range is the same for angles θ and 90 
∘
 −θ. This is because sin(2θ)=sin(2(90 
∘
 −θ))=sin(180 
∘
 −2θ)=sin(2θ). For example, the range for 30 
∘
  is the same as for 60 
∘
 .
Zero Range: The range is zero when sin(2θ)=0. This occurs when 2θ=0 
∘
  or 2θ=180 
∘
 , meaning θ=0 
∘
  (horizontal launch, lands immediately) or θ=90 
∘
  (vertical launch, goes straight up and down).
Influence of Other Parameters
Initial Velocity (v 
0
​
 ): The range is directly proportional to v 
0
2
​
 . This means that if you double the initial velocity, the range increases by a factor of four. This highlights the significant impact of initial speed on the projectile's trajectory.
Gravitational Acceleration (g): The range is inversely proportional to g. This means that if g decreases (e.g., on the Moon), the range will increase for the same initial velocity and angle. Conversely, if g increases, the range will decrease.
3. Practical Applications
The idealized model of projectile motion is a powerful tool, but it has limitations. However, it forms the foundation for understanding more complex scenarios:

Uneven Terrain: For projectiles launched on uneven terrain, the landing height y 
f
​
  is not necessarily zero. The time of flight would then be determined by solving a quadratic equation for t: y 
f
​
 =v 
0
​
 tsinθ− 
2
1
​
 gt 
2
 . This yields two solutions for t, and the positive one represents the time of flight to the specified height. The horizontal range would then be x(t).
Air Resistance (Drag): In reality, air resistance significantly affects projectile motion. Air resistance is typically proportional to some power of the velocity (linear for low speeds, quadratic for high speeds) and opposes the motion. This introduces a drag force term into the equations of motion, making them non-linear and often requiring numerical solutions. The range will generally be reduced due to air resistance, and the optimal angle for maximum range will be less than 45 
∘
 .
Wind: Wind introduces an additional force component that can either aid or oppose the projectile's horizontal motion. This can be incorporated by adding a constant acceleration term in the x-direction (for a constant wind) or a more complex velocity-dependent force.
Spin: The spin of a projectile (e.g., a golf ball or a soccer ball) can create aerodynamic forces like the Magnus effect, which can significantly alter the trajectory. This adds lift or sideways forces, making the motion three-dimensional and more complex.
Varying Gravity/Atmospheric Density: For very long-range projectiles (e.g., intercontinental ballistic missiles) or objects in space, the variation of gravitational acceleration with altitude and changes in atmospheric density must be considered.
This model serves as a fundamental building block. By adding more terms and considering additional forces, it can be adapted to describe a wide array of real-world situations in sports, engineering, military applications, and astrophysics.

4. Implementation
Below is a Python script that simulates projectile motion and visualizes the range as a function of the angle of projection for different initial conditions.

Python

import numpy as np
import matplotlib.pyplot as plt

def projectile_range(v0, theta_deg, g=9.81):
    """
    Calculates the horizontal range of a projectile.
    
    Args:
        v0 (float): Initial velocity in m/s.
        theta_deg (float): Angle of projection in degrees.
        g (float): Gravitational acceleration in m/s^2.
        
    Returns:
        float: Horizontal range in meters.
    """
    theta_rad = np.deg2rad(theta_deg)
    R = (v0**2 * np.sin(2 * theta_rad)) / g
    return R

def simulate_projectile_path(v0, theta_deg, g=9.81, num_points=100):
    """
    Simulates the trajectory of a projectile.
    
    Args:
        v0 (float): Initial velocity in m/s.
        theta_deg (float): Angle of projection in degrees.
        g (float): Gravitational acceleration in m/s^2.
        num_points (int): Number of points to simulate for the trajectory.
        
    Returns:
        tuple: (x_coords, y_coords) of the trajectory.
    """
    theta_rad = np.deg2rad(theta_deg)
    
    # Calculate time of flight
    T = (2 * v0 * np.sin(theta_rad)) / g
    
    t = np.linspace(0, T, num_points)
    
    x = v0 * t * np.cos(theta_rad)
    y = v0 * t * np.sin(theta_rad) - 0.5 * g * t**2
    
    return x, y

# --- Simulation and Visualization ---

# Parameters
initial_velocities = [10, 20, 30]  # m/s
gravitational_accelerations = [9.81, 1.62]  # Earth and Moon g values
angles_deg = np.linspace(0, 90, 91) # Angles from 0 to 90 degrees

# Plotting Range vs. Angle for different initial velocities on Earth
plt.figure(figsize=(10, 6))
for v0 in initial_velocities:
    ranges = [projectile_range(v0, angle) for angle in angles_deg]
    plt.plot(angles_deg, ranges, label=f'$v_0$ = {v0} m/s')

plt.title('Horizontal Range vs. Angle of Projection (Earth, g=9.81 m/s$^2$)')
plt.xlabel('Angle of Projection (degrees)')
plt.ylabel('Horizontal Range (m)')
plt.grid(True)
plt.legend()
plt.axvline(x=45, color='r', linestyle='--', label='Optimal Angle (45°)')
plt.ylim(bottom=0)
plt.xlim(0, 90)
plt.show()

# Plotting Range vs. Angle for different gravitational accelerations (fixed v0)
plt.figure(figsize=(10, 6))
v0_fixed = 25 # m/s
for g_val in gravitational_accelerations:
    ranges = [projectile_range(v0_fixed, angle, g=g_val) for angle in angles_deg]
    plt.plot(angles_deg, ranges, label=f'g = {g_val} m/s$^2$')

plt.title(f'Horizontal Range vs. Angle of Projection ($v_0$ = {v0_fixed} m/s)')
plt.xlabel('Angle of Projection (degrees)')
plt.ylabel('Horizontal Range (m)')
plt.grid(True)
plt.legend()
plt.axvline(x=45, color='r', linestyle='--', label='Optimal Angle (45°)')
plt.ylim(bottom=0)
plt.xlim(0, 90)
plt.show()

# Visualize some projectile paths
plt.figure(figsize=(12, 8))
v0_example = 30 # m/s
angles_example = [15, 30, 45, 60, 75, 85] # degrees

for angle in angles_example:
    x_coords, y_coords = simulate_projectile_path(v0_example, angle)
    plt.plot(x_coords, y_coords, label=f'$\\theta$ = {angle}°')
    plt.plot(x_coords[-1], y_coords[-1], 'ro') # Mark end point

plt.title(f'Projectile Trajectories ($v_0$ = {v0_example} m/s)')
plt.xlabel('Horizontal Distance (m)')
plt.ylabel('Vertical Distance (m)')
plt.grid(True)
plt.legend()
plt.ylim(bottom=0)
plt.xlim(left=0)
plt.gca().set_aspect('equal', adjustable='box') # Make scales equal for better visualization
plt.show()
Deliverables:
A detailed description of the family of solutions derived from the governing equations.
As discussed in Section 1, the governing equations for projectile motion are:
x(t)=v 
0
​
 tcosθ

y(t)=v 
0
​
 tsinθ− 
2
1
​
 gt 
2
 

These equations represent the position (x,y) of the projectile at any time t. The "family of solutions" refers to the set of all possible trajectories that can be generated by varying the initial conditions:

Initial Velocity (v 
0
​
 ): A higher v 
0
​
  results in a larger, longer trajectory.
Angle of Projection (θ): This dictates the shape and extent of the parabolic path. Angles closer to 45 
∘
  generally lead to larger horizontal ranges (assuming launch from y=0), while angles closer to 90 
∘
  lead to higher vertical travel and angles closer to 0 
∘
  lead to minimal vertical travel.
Gravitational Acceleration (g): A smaller g results in a flatter, longer trajectory for the same v 
0
​
  and θ.
Initial Position (x 
0
​
 ,y 
0
​
 ): While we assumed (0,0), including non-zero initial positions shifts the entire trajectory. For example, x(t)=x 
0
​
 +v 
0
​
 tcosθ and y(t)=y 
0
​
 +v 
0
​
 tsinθ− 
2
1
​
 gt 
2
 .
Each unique combination of these parameters (v 
0
​
 ,θ,g,x 
0
​
 ,y 
0
​
 ) defines a specific and unique parabolic trajectory.

Graphical representations of the range versus angle of projection, highlighting how different parameters influence the curve.
The plots generated by the Python script demonstrate the following:

Range vs. Angle for Different Initial Velocities (Earth):
As v 
0
​
  increases, the maximum range significantly increases (quadratically).
For all v 
0
​
  values, the maximum range occurs at θ=45 
∘
 .
The curves are symmetrical around 45 
∘
 .