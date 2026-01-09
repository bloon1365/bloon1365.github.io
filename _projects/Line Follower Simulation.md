---
layout: page
title: Line Follower Simulation
description: A 2D physics simulaton of a robot to test line following algorithms. Personal Project
img: assets/img/Line Follower Simulation/1.png
importance: 1
category: 
  - Software
related_publications:
---

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

<h2>Project Overview</h2> 
This project is a 2D physics-based simulation of a differential-drive line-following robot. The goal was to validate embedded line-following firmware without building physical hardware, effectively acting as a low-cost Hardware-in-the-Loop (HIL) test environment. The simulation communicates with a real microcontroller over USB serial, allowing the exact same firmware used on hardware to run unmodified against simulated sensors and actuators.

<h2>System Architecture</h2> 
<ol> 
  <li><strong>Physics & Kinematics Simulation:</strong><br> 
  A custom robot model simulates linear and angular motion using force-based dynamics, including motor back-EMF behavior, friction, mass, and rotational inertia. Wheel forces are derived from PWM commands, allowing realistic acceleration, turning behavior, and instability if the controller is poorly tuned.</li> 
  <li><strong>Sensor Simulation:</strong><br> 
  Three forward-facing reflective sensors are simulated by sampling pixel brightness from a map image. Sensor values are computed by averaging grayscale values within a radius and inverted so dark lines register as high intensity, closely matching real IR line sensors.</li> 
  <li><strong>Serial HIL Interface:</strong><br> 
  Sensor data is streamed to the microcontroller as formatted serial packets, while motor PWM commands are read back asynchronously. This allows the embedded controller to behave as if it were connected to real sensors and motors.</li> 
  <li><strong>Real-Time Visualization:</strong><br> 
  Pygame is used to render the robot, wheel orientation, heading, sensor positions, and track layout. Multiple maps can be cycled dynamically to test controller robustness across different path geometries.</li> 
  <li><strong>Live Telemetry Plotting:</strong><br> 
  A parallel Matplotlib thread plots sensor values and motor PWM outputs in real time, enabling rapid debugging and controller tuning without relying on firmware-level logging.</li> 
</ol> 

<h2>Key Technical Challenges</h2> 
<ol> 
  <li><strong>Real-Time Synchronization:</strong><br> 
  The simulation, serial communication, rendering loop, and plotting all run concurrently. Thread-safe buffering and non-blocking serial reads were required to prevent latency and dropped commands.</li> 
  <li><strong>Stable Physics Modeling:</strong><br> 
  Naive kinematic models were insufficient. A force-based approach with friction and torque limits was required to prevent unrealistic behavior and expose controller weaknesses that would appear on real hardware.</li> 
  <li><strong>Sensor Noise & Realism:</strong><br> 
  Averaging pixel regions instead of single-point sampling reduced aliasing and produced smoother, more realistic sensor readings, closer to physical reflectance sensors.</li> 
</ol> 

<h2>Results</h2> 
<p>The simulation successfully runs embedded line-following firmware in real time without modification. Controllers can be tuned, stress-tested, and debugged before deployment to physical hardware, significantly reducing development time and risk. Poorly tuned control loops visibly destabilize the robot, while robust algorithms generalize across multiple track layouts. </p> 

<h2>Conclusion</h2> 
<p>This project provided a practical HIL testing environment using only Python and consumer hardware. It bridges the gap between purely theoretical control design and real-world deployment, and mirrors the workflow used in professional robotics and automotive validation environments. </p>

{% include youtube.html id="1k2yg1OTats" %}
