Problem 3: Trajectories of a Freely Released Payload Near Earth

1. Background & Physics Principles

Newton's Law of Gravitation
The gravitational force acting on the payload near Earth is:

F
=
−
G
M
m
r
2
r
^
F=− 
r 
2
 
GMm
​	
  
r
^
 
where

G
=
6.67430
×
10
−
11
 
m
3
k
g
−
1
s
−
2
G=6.67430×10 
−11
 m 
3
 kg 
−1
 s 
−2
  is the gravitational constant,
M
=
5.972
×
10
24
 
k
g
M=5.972×10 
24
 kg is Earth's mass,
m
m is the payload mass,
r
r is the distance from Earth's center,
r
^
r
^
  is the unit vector from Earth’s center to the payload.
The acceleration due to Earth's gravity is:

a
=
−
G
M
r
3
r
a=− 
r 
3
 
GM
​	
 r
Equations of Motion
The motion of the payload under gravity satisfies:

d
2
r
d
t
2
=
−
G
M
r
3
r
dt 
2
 
d 
2
 r
​	
 =− 
r 
3
 
GM
​	
 r
Given initial conditions 
r
0
r 
0
​	
  and 
v
0
v 
0
​	
 , the trajectory is computed numerically.

2. Types of Trajectories

The shape of the trajectory depends on the total specific mechanical energy 
E
E:

E
=
v
2
2
−
G
M
r
E= 
2
v 
2
 
​	
 − 
r
GM
​	
 
Elliptical orbit: 
E
<
0
E<0 (bound orbit),
Parabolic trajectory: 
E
=
0
E=0 (escape velocity),
Hyperbolic trajectory: 
E
>
0
E>0 (unbound, escape path).
3. Numerical Simulation Method

We solve the second-order ODE using numerical integration (e.g., RK4):

Initial conditions: 
r
0
r 
0
​	
 , 
v
0
v 
0
​	
 ,
Update position and velocity at each timestep 
Δ
t
Δt,
Continue until simulation time ends or payload hits Earth.
4. Python Implementation

import numpy as np
import matplotlib.pyplot as plt

# Constants
G = 6.67430e-11           # m^3 kg^-1 s^-2
M = 5.972e24              # kg
R_earth = 6371e3          # Earth radius in meters

# Simulation parameters
dt = 1.0                  # time step in seconds
t_max = 20000             # max simulation time in seconds

# Initial conditions
altitude = 500e3          # 500 km above Earth surface
r0 = np.array([R_earth + altitude, 0.0])  # initial position (x,y)
v_circular = np.sqrt(G * M / np.linalg.norm(r0))  # circular orbit velocity

# Set initial velocity: 10% faster than circular velocity (example)
v0 = np.array([0.0, 1.1 * v_circular])

# Initialize state variables
r = r0.copy()
v = v0.copy()

positions = []
velocities = []
times = []

def acceleration(r):
    r_norm = np.linalg.norm(r)
    return -G * M * r / r_norm**3

t = 0
while t < t_max:
    # Record data
    positions.append(r.copy())
    velocities.append(v.copy())
    times.append(t)
    
    # RK4 integration steps
    a1 = acceleration(r)
    k1v = a1 * dt
    k1r = v * dt
    
    a2 = acceleration(r + 0.5 * k1r)
    k2v = a2 * dt
    k2r = (v + 0.5 * k1v) * dt
    
    a3 = acceleration(r + 0.5 * k2r)
    k3v = a3 * dt
    k3r = (v + 0.5 * k2v) * dt
    
    a4 = acceleration(r + k3r)
    k4v = a4 * dt
    k4r = (v + k3v) * dt
    
    # Update velocity and position
    v += (k1v + 2*k2v + 2*k3v + k4v) / 6
    r += (k1r + 2*k2r + 2*k3r + k4r) / 6
    
    # Stop if payload hits Earth's surface
    if np.linalg.norm(r) <= R_earth:
        print(f"Payload hit Earth surface at t={t:.2f} seconds")
        break
    
    t += dt

positions = np.array(positions)
velocities = np.array(velocities)
times = np.array(times)

# Plot trajectory
plt.figure(figsize=(8,8))
earth = plt.Circle((0,0), R_earth, color='b', alpha=0.3)
plt.gca().add_patch(earth)
plt.plot(positions[:,0], positions[:,1], label="Payload Trajectory")
plt.scatter([r0[0]], [r0[1]], color='green', label='Initial Position')
plt.axis('equal')
plt.xlabel('x (m)')
plt.ylabel('y (m)')
plt.title('Payload Trajectory Near Earth')
plt.legend()
plt.grid()
plt.show()

# Plot energy over time
speeds = np.linalg.norm(velocities, axis=1)
radii = np.linalg.norm(positions, axis=1)
energy = 0.5 * speeds**2 - G * M / radii

plt.figure()
plt.plot(times, energy)
plt.xlabel('Time (s)')
plt.ylabel('Specific Mechanical Energy (J/kg)')
plt.title('Energy vs Time (should be roughly constant)')
plt.grid()
plt.show()
5. Interpretation of Results

When initial velocity 
v
0
<
v
e
s
c
a
p
e
=
2
G
M
/
r
0
v 
0
​	
 <v 
escape
​	
 = 
2GM/r 
0
​	
 
​	
 , the payload remains in elliptical orbit around Earth.
At exactly escape velocity 
v
0
=
v
e
s
c
a
p
e
v 
0
​	
 =v 
escape
​	
 , the trajectory becomes parabolic, allowing the payload to escape Earth's gravity.
If 
v
0
>
v
e
s
c
a
p
e
v 
0
​	
 >v 
escape
​	
 , the trajectory is hyperbolic and the payload escapes Earth entirely.
The simulation allows visualization of these trajectories and energy conservation checks.

6. Real-World Applications

Orbital insertion: Satellites released from rockets must achieve proper velocity vectors to orbit Earth stably.
Reentry: Payloads returning to Earth need controlled velocities and angles to avoid burning up or skipping the atmosphere.
Escape trajectories: Missions aiming for Moon, Mars, or beyond require trajectories above escape velocity.