---
layout: page
title: Power Supply
description: An ATX computer power supply converted to a desktop power supply.
img: assets/img/Power Supply/2.png
importance: 1
category: 
  - Electrical
related_publications:
---

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

<h2>Project Overview</h2>
The goal of this project is to convert a standard computer power supply into a convenient desktop power supply that provides 3.3V, 5V, and 12V outputs. It will include voltage and current displays, as well as an on/off switch for easy control.

<h2>Parts Selection</h2>
<ol>
  <li><strong>3D Printed Frame:</strong><br>
    A frame was needed that has unique dimensional requirements, it needed to attach to the screw pattern of the PSU, it needed to hold the power switch, the digital readouts and the banana plugs for voltage selection and the output alligator leads.</li>
  <li><strong>Voltage and Current Readout:</strong><br>
    The DSN-VC288 was selected as it works within the voltage range and can support the max current the PSU can supply.</li>
</ol>

<h2>Project Milestones</h2>
<ol>
  <li><strong>Laying Out Electronics:</strong><br>
    Converting a PSU to a bench top power supply is pretty straight forward, all the wires are color coded and using the image below the circuit is pretty simple. Essentially a switch is but between green and GND and the voltage is selected between the respective colors. 
    <div class="row">
      <div class="col-sm mt-3 mt-md-0">   
      {% include figure.html path="assets/img/Power Supply/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
      </div>
    </div>
  </li>
  <li><strong>Printing The Frame:</strong><br>
    The frame is a simple but key part of the project. I found the standard screw pattern online and the dimensions of my digital readout, switch and banana plugs and made the model in SolidWorks.
    <div class="row">   
      <div class="col-sm mt-3 mt-md-0">   
      {% include figure.html path="assets/img/Power Supply/4.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
      </div>
    </div>
    <div class="row">   
      <div class="col-sm mt-3 mt-md-0">   
      {% include figure.html path="assets/img/Power Supply/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
      </div>
    </div>  
  </li>
  <li><strong>Permanent Wiring:</strong><br>
    Now that I knew the design worked and the frame was printed, I assembled my parts into the frame and could begin the permanent wiring. I soldered all connections and used heat shrink so they would be decent quality and I wouldn't have to worry about anything coming apart or shorting</li>
</ol>

<div class="row">   
  <div class="col-sm mt-3 mt-md-0">   
  {% include figure.html path="assets/img/Power Supply/2.png" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<h2>Conclusion</h2>
<p>This was a great project that was my first time 3D printing with my new printer, an Ender3. It also allows me to work on other projects now that I have a power supply with all the voltages I would need for small electronics.</p>

{% include youtube.html id="0mJzliy433I" %}
{% include youtube.html id="oymY2x2WkWY" %}
