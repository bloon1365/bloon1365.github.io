---
layout: page
title: GPS Tracking Collar
description: 
img: assets/img/Tracking Collar/1.jpg
importance: 1
category: 
 - Electrical
 - Mechanical
 - Software
---

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

<h2>Project Overview</h2>
<p>
The BisonTrack project is a GPS tracking collar designed to withstand the harsh environmental conditions and behaviors of bison. Developed by Wright Collars and the MSE 410 Capstone team, the collar aims to improve conservation efforts by providing reliable long-term location tracking. It features a robust drop-off mechanism, power-efficient electronics, and a self-releasing system using satellite communication and GPS technologies. The collar is built to operate for up to four years with minimal power consumption, even in extreme temperatures and rugged terrain.
</p>

<div class="row">
  <div class="col-sm mt-3 mt-md-0">   
    {% include figure.html path="assets/img/Tracking Collar/1.jpg" title="Project Image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>


<h2>Electrical</h2>
<p>
All electrical parts were selected according to their price, power consumption and other factors. Decision matrices were made for all the parts and the best option was selected.
</p>


<h3>Parts Selection</h3>
<ol>
  <li><strong>Microcontroller:</strong><br>
    The LPC802 was selected for its low power consumption, availability of UART communication, ADC functionality, and deep sleep mode support.</li>
  <li><strong>Satellite Communication Module:</strong><br>
    The KIM2 module (from the ARGOS/Kinéis network) was chosen for its lower power draw and simpler integration, despite a larger antenna requirement.</li>
  <li><strong>GPS Module:</strong><br>
    The SAM-M10 was chosen for its small form factor, integrated antenna, and low power usage, helping to extend battery life.</li>
  <li><strong>DC-DC Converter:</strong><br>
    The TPS63021DSJT was selected for its efficiency, cost-effectiveness, and compatible pin configuration for stable voltage regulation.</li>
</ol>



<h2>Mechanical</h2>
<p>
When we started on this project, Wright Collars had already developed a strap and housing design so our main task was to design a drop-off mechanism that could withstand the needed forces. 
</p>

<h3>Prototypes</h3>
<p>
Two prototypes were developed to ensure a working design would be achieved at the end of our capstone project. The first one is a pin style drop-off which we based off of competitors designs which is activated by a servo.
</p>
<div class="row">
  <div class="col-sm mt-3 mt-md-0">   
    {% include figure.html path="assets/img/Tracking Collar/2.png" title="Project Image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<p>
We also made a drop-off of our own design that uses a series of pins to decouple the forces of the collar from the servo allowing the mechanism to withstand extreme forces and release with under tension.
</p>
<div class="row">
  <div class="col-sm mt-3 mt-md-0">   
    {% include figure.html path="assets/img/Tracking Collar/3.png" title="Project Image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

{% include youtube.html id="j7zILJemzcw" %}

<p>
We then validated our design by testing the prototype's release under tension and then tested it statically to failure. The test resulted in no major design changes as the force before breaking was more then sufficient for our use case.
</p>


<h2>Project Milestones</h2>
<ol>
  <li><strong>Conceptual Design Phase:</strong><br>
    Initial research, simulations, and design selection for both mechanical and electrical systems were completed.</li>
  <li><strong>Prototype Development:</strong><br>
    Ongoing work includes 3D printed prototypes, servo actuation development, PCB design, and satellite transmission troubleshooting.</li>
  <li><strong>Testing Phase:</strong><br>
    Involves developing jigs for drop-off strength testing and ensuring microcontroller circuit reliability.</li>
  <li><strong>Final Adjustments and Delivery:</strong><br>
    Will include software finalization, data collection implementation, and preparation for final presentation and deployment.</li>
</ol>

<p>
We are currently in the Prototype Development/Testing phase, we are testing our prototypes and creating our final designs for machining and PCB manufacturing. 
</p>


<h2>Additional Improvements and Future Plans</h2>
<ol>
  <li><strong>Miniaturized System:</strong><br>
    If we can shrink our drop-off and electronics enough this collar could also be used on smaller animals suck as wolves.</li>
  <li><strong>Battery Optimization:</strong><br>
    Testing will determine whether to use two or three LSH20 batteries based on real-world energy consumption data.</li>
</ol>

