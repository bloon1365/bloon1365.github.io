---
layout: page
title: Bison GPS Tracking Collar
description: Design and prototyping of a wallowing-resistant, self-releasing GPS tracking collar for long-term bison monitoring. Team Project
img: assets/img/BisonTrack/1.png
importance: 1
category:
 - Electrical
 - Mechanical
 - Software
---

<h2>Project Overview</h2>

This project was a year-long capstone focused on designing and prototyping a rugged GPS tracking collar for bison herd monitoring.

Existing commercial collars fail prematurely due to extreme mechanical abuse, environmental exposure, and limited battery life. The goal was to develop a collar capable of surviving multiple years in harsh field conditions while reliably transmitting GPS data via satellite.

The project was sponsored by Wright Collars and conducted as part of MSE 410/411 at Simon Fraser University.


<h2>My Role</h2>

I was responsible for the **electrical and firmware design**, including:

<ul>
  <li>Microcontroller selection and low-power firmware architecture</li>
  <li>Satellite communication integration (ARGOS / Kinéis)</li>
  <li>GPS integration and validation</li>
  <li>Power management and battery life analysis</li>
  <li>PCB design, bring-up, and debugging</li>
</ul>


<h2>System Architecture</h2>

The collar integrates multiple subsystems into a compact, sealed enclosure:

<ul>
  <li>Low-power microcontroller (LPC802)</li>
  <li>GPS module for position acquisition</li>
  <li>ARGOS satellite transmitter for global data relay</li>
  <li>Servo-actuated mechanical drop-off mechanism</li>
  <li>Primary lithium battery pack designed for multi-year life</li>
</ul>

All electronics were mounted on a custom PCB and enclosed within a rugged housing designed to survive impact, mud, water ingress, and extreme temperatures.


<h2>Key Engineering Challenges</h2>

<h3>1. Extreme Mechanical and Environmental Constraints</h3>

The collar had to survive behavior unique to bison: wallowing in mud, rubbing against trees, impacts, and long-term exposure to water, dust, and freezing temperatures.

This drove strict requirements on enclosure sealing, connector elimination, and mechanical robustness. All electronics had to tolerate shock, vibration, and contamination without service access.


<h3>2. Multi-Year Power Budget</h3>

Achieving a multi-year lifespan required aggressive power optimization.

Key challenges included:

<ul>
  <li>Deep-sleep firmware design</li>
  <li>Minimizing GPS acquisition time</li>
  <li>Managing high peak currents during satellite transmission</li>
  <li>Designing battery measurement circuitry without excessive quiescent draw</li>
</ul>

Real-world current measurements revealed issues not visible in simulation, including ADC loading effects that required hardware redesign.


<h3>3. Reliable Satellite Communication</h3>

The system uses the ARGOS satellite network, which trades bandwidth for lower power consumption.

Challenges included:

<ul>
  <li>UART-based communication with the satellite module</li>
  <li>Strict timing and power constraints during transmission windows</li>
  <li>Validating transmission reliability under limited test access</li>
</ul>

Development was performed using evaluation hardware, with provisions added for future integration of production modules.


<h2>Mechanical Drop-Off Integration</h2>

A servo-actuated seatbelt-style drop-off mechanism allows the collar to release automatically at end-of-life or under fault conditions.

The electronics interface had to:

<ul>
  <li>Control the servo with zero idle current draw</li>
  <li>Guarantee release even under high tensile load</li>
  <li>Survive shock and vibration during actuation</li>
</ul>

The initial design:
<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    <figure class="figure">
      {% include figure.html
        path="assets/img/Tracking Collar/12.png"
        class="img-fluid rounded z-depth-1" %}
      <figcaption class="figure-caption">
        Figure 1: Initial Design
      </figcaption>
    </figure>
  </div>
</div>

Final Design:
<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    <figure class="figure">
      {% include figure.html
        path="assets/img/Tracking Collar/4.png"
        class="img-fluid rounded z-depth-1" %}
      <figcaption class="figure-caption">
        Figure 2: Final Design
      </figcaption>
    </figure>
  </div>
</div>
{% include youtube.html id="j7zILJemzcw" %}


Here is an example of a 3D printed prototype functioning:
{% include youtube.html id="j7zILJemzcw" %}

This prototype was tensile tested until failure. At 200lbs the locking pin sheared.

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    <figure class="figure">
      {% include figure.html
        path="assets/img/Tracking Collar/6.jpg"
        class="img-fluid rounded z-depth-1" %}
      <figcaption class="figure-caption">
        Figure 1: Locking Pin Failure
      </figcaption>
    </figure>
  </div>
</div>

This failure was due to the printed enclosure of the locking pins deflecting causing all the force to be concentrated on the end of the locking pin. More fasteners were added to reduce defection in this key location. This test gave us the confidence to go ahead and get an aluminum version made. 



Extensive testing was performed, including tensile loading, debris ingress, and impact testing.


<h2>Difficulties and Lessons Learned</h2>

This project encountered several non-trivial challenges that required iteration across mechanical design, electrical design, and system-level validation. Many of these issues only became apparent once hardware was built and tested under realistic conditions.


<h3>Mechanical Failure of the Drop-Off Mechanism</h3>

Early versions of the drop-off mechanism were 3D printed to allow for rapid iteration and mechanical testing. During tensile testing, we intentionally loaded the mechanism until failure to identify weak points in the design.

This testing revealed a clear failure mode in the printed geometry, where stress concentrated at the locking interface and caused deformation prior to release. While this behavior was undesirable, it provided valuable insight into how forces were distributed through the mechanism.

The results directly informed subsequent design revisions, including geometry changes and improved load paths. A video and still images document both the failure event and the post-failure condition of the part.




<h3>Battery Voltage Sensing and ADC Limitations</h3>

Battery voltage monitoring proved more challenging than initially expected.

To minimize quiescent current draw, the voltage divider resistors were chosen with very large values. While this reduced static power consumption, it introduced an unintended side effect: the ADC input impedance was not high enough to reliably sample the divided voltage.

As a result, the ADC measurement node effectively floated, producing unstable and inaccurate readings that did not reflect the actual battery voltage.

This issue highlighted a key tradeoff in low-power design: minimizing static current must be balanced against the electrical requirements of the measurement circuitry. In hindsight, a buffered measurement, switched divider, or lower-value resistors enabled only during sampling would have been a more robust solution.


<h3>Unexpected Current Consumption</h3>

Measured current consumption differed from initial estimates based on component datasheets and simulations.

While average current draw met the long-term power budget, several transient behaviors significantly impacted energy usage, including wake-up current spikes, GPS acquisition behavior, and satellite transmission overhead.

These effects are summarized in the project poster, which presents measured current draw across different operating modes. This experience reinforced the importance of real-world measurements over purely theoretical power models, especially for systems targeting multi-year lifespans.


<h3>System Validation and Data Visualization</h3>

Beyond hardware functionality, validating the end-to-end system was a major challenge.

Once GPS and satellite transmission were operational, data had to be decoded, stored, and interpreted in a meaningful way. To support this, we developed a simple web-based interface that displays received GPS points on a map.

Seeing the final output — a continuous track of location data visualized geographically — was a critical milestone. It confirmed not only that individual subsystems worked, but that the full pipeline from sensor acquisition to user-facing data presentation was functional.

Images of the final map output and the data visualization interface are included to demonstrate this end result.


<h3>Key Takeaways</h3>

<ul>
  <li>Mechanical testing to failure provides actionable design insight that simulations alone cannot</li>
  <li>Ultra-low-power design requires careful consideration of analog measurement limitations</li>
  <li>Datasheet-based power estimates must be validated with real hardware measurements</li>
  <li>End-to-end validation, including data visualization, is essential for proving system readiness</li>
</ul>





<h2>Results</h2>

The final prototype demonstrated:

<ul>
  <li>Reliable GPS acquisition and satellite transmission</li>
  <li>Stable low-power operation with predictable energy usage</li>
  <li>Successful actuation of the drop-off mechanism under load</li>
  <li>Mechanical resilience to impact, dirt, and water exposure</li>
</ul>

The design met all core functional requirements and established a solid foundation for future production refinement.


<h2>What This Project Demonstrates</h2>

<ul>
  <li>End-to-end embedded system design</li>
  <li>Low-power firmware development under real constraints</li>
  <li>Hardware bring-up and debugging</li>
  <li>Cross-disciplinary integration of mechanical, electrical, and software systems</li>
  <li>Engineering decision-making driven by field realities rather than ideal assumptions</li>
</ul>


<h2>Documentation</h2>

<p>
Full technical documentation is available in the final capstone report and user manual.
</p>
