---
layout: page
title: Drone
description: A drone developed as part of my high school capstone project. Personal Project
img: assets/img/Drone/1.jpg
importance: 2
category: 
  - Mechanical
  - Electrical
related_publications:
---

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

<h2>Project Overview</h2>

The goal of this project is to design and construct a custom drone capable of stable flight and maneuverability. To achieve this, a combination of laser-cut and 3D-printed components will be utilized, along with commercially available flight control and radio systems. The drone will be designed to be lightweight yet durable, with the ability to handle various environmental conditions.

<div class="row">
  <div class="col-sm mt-3 mt-md-0">   
    {% include figure.html path="assets/img/Drone/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<h2>Parts Selection</h2>
<ol>
  <li><strong>Laser Cut Frame:</strong><br>
    The frame of the drone will be cut using a laser cutter. This ensures accuracy and consistency in the frame's dimensions, resulting in a sturdy yet lightweight structure. The material chosen for the frame will be wood for its strength-to-weight ratio and it's ease of cutting with a laser. </li>
  <li><strong>Custom 3D Printed Propellers:</strong><br>
    Propellers are critical components of any drone, as they directly influence lift and thrust generation. Custom 3D printing allows for precise control over the design and optimization of propeller geometry, enabling efficient performance and reduced noise levels. The material will be PLA because of it's convenience despite it's unfavorable material properties
    <div class="row">
      <div class="col-sm mt-3 mt-md-0">   
      {% include figure.html path="assets/img/Drone/2.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
      </div>
    </div>
  </li>
  <li><strong>Store Bought Flight Controller:</strong><br>
    To ensure stable flight and reliable control, a commercial flight controller will be integrated into the drone's electronics system. These controllers feature advanced algorithms for stabilization and navigation, providing a smooth flying experience. The selected flight controller will be compatible with various communication protocols and will interface with the selected motor controllers.</li>
  <li><strong>Flysky Radio/Receiver:</strong><br>
    The radio transmitter and receiver are essential for piloting the drone remotely. The Flysky radio system offers robust signal transmission and user-friendly interface, allowing precise control over flight maneuvers. Compatibility with the chosen flight controller and ease of setup where key factors in selecting the radio system.</li>
  <li><strong>Brush-less Motors/Motor Controllers:</strong><br>
    Brush-less motors provide the necessary power for lift and propulsion in the drone. Paired with efficient motor controllers, they offer high torque and responsiveness, essential for dynamic flight performance. Selection criteria include motor size, KV rating, and compatibility with the frame and propellers chosen for the project.</li>
</ol>

<h2>Project Milestones</h2>
<ol>
  <li><strong>Design Phase:</strong><br>
    - Successfully completed the Visual Line of Sight (VLOS) drone license exam, demonstrating proficiency in drone operation and safety protocols required by regulatory authorities.<br>
    - Registered the drone with the federal government in compliance with regulatory requirements, ensuring adherence to airspace regulations and facilitating identification and traceability of the drone.<br>
    - CAD modeling of the drone frame and components.<br>
    - Propeller design optimization for efficiency and stability.<br>
    - Selection and procurement of flight controller, radio system, motors, and motor controllers.</li>
  <li><strong>Fabrication Phase:</strong><br>
    - Laser cutting of frame components.<br>
    - 3D printing of custom propellers.<br>
    - Assembly of electronics and integration with the frame.<br>
    - Building a power supply to charge the LiPO<br>
    <div class="row">
      <div class="col-sm mt-3 mt-md-0">   
      {% include figure.html path="assets/img/Drone/3.png" title="example image" class="img-fluid rounded z-depth-1" %}
      </div>
    </div>
  </li>
  <li><strong>Testing and Calibration:</strong><br>
    - Correcting of motor positions and propeller directions.<br>
    - Initial flight tests to assess stability and control.<br>
    - Range and endurance testing to evaluate battery life and signal integrity.</li>
  <li><strong>Refinement and Optimization:</strong><br>
    - Iterative improvements based on test results.<br>
    - Fine-tuning of design and component selection for enhanced performance.<br>
    - Documentation of lessons learned and best practices for future projects.</li>
</ol>

<h2>Additional Improvements and Future Plans</h2>
<ol>
  <li><strong>3D Printed Propellers:</strong><br>
     - Addressed vibration and efficiency issues caused by unbalanced propellers by implementing a more precise printing process or post-printing balancing techniques.</li>
  <li><strong>Landing Gear Enhancement:</strong><br>
     - Plan to redesign and improve the landing gear to enhance stability during takeoff and landing, potentially incorporating shock-absorbing materials.</li>
  <li><strong>Custom Flight Controller Development:</strong><br>
     - Aspire to develop a custom flight controller using Arduino and gyroscope sensors to gain deeper understanding of drone control systems and potentially unlock advanced functionality tailored to specific project requirements.</li>
</ol>


<h2>Conclusion</h2>
<p>Through careful planning and meticulous execution, this DIY drone construction project demonstrates the feasibility of creating a custom aerial platform using a combination of off-the-shelf components and custom-designed elements. By leveraging advanced manufacturing techniques and modern electronics, the resulting drone showcased both functionality and innovation in unmanned aerial vehicle (UAV) design.</p>

{% include youtube.html id="CTB7FhwmU0I" %}

