---
layout: page
title: RTC Replacement for new PCB Revision
description: Replacing a Real Time Clock and writing drivers for a new PCB Revision. Work Project
img: assets/img/RTC Replacement/4.jpg
importance: 1
category: 
  - Software
  - Electrical
related_publications:
---

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>


<h2>Project Overview</h2> This project involved updating legacy embedded firmware to support a new hardware revision after a critical component was discontinued. Specifically, a real-time clock (RTC) on the ProHeat product line was replaced with a newer, functionally equivalent device, requiring a new driver implementation and SPI interface updates on the microcontroller.

The objective was to maintain product viability without rewriting large portions of an aging codebase, while ensuring future hardware revisions could be integrated with less friction.

<h2>Technical Scope</h2> 
<ol> 
  <li>
    <strong>New RTC Driver Development:</strong><br> 
  A complete driver was written for the replacement RTC, including initialization, register access, and timekeeping functionality. The implementation was designed to match the expectations of the existing firmware to minimize downstream changes.</li> 
  <li><strong>SPI Interface Integration:</strong><br> 
  The microcontroller’s SPI configuration was updated to support the new device and the latest PCB revision. This included timing, mode selection, and data framing adjustments required for reliable communication.</li> 
  <li><strong>Legacy Codebase Integration:</strong><br> 
  The driver was integrated into a large, aging codebase with limited abstraction and sparse documentation. Care was taken to avoid breaking existing functionality while introducing support for the new hardware revision.</li> 
</ol> 

<h2>Debugging & Validation</h2> 
<ol> 
  <li><strong>Hardware-Level Debugging:</strong><br> 
  Due to uncertainty around the SPI implementation, an oscilloscope was used as a sanity check to validate clock polarity, phase, chip select behavior, and data timing. This ensured the firmware behavior matched the RTC’s datasheet rather than relying solely on software assumptions.</li> 
  <li><strong>Dead-Bug Prototyping:</strong><br> 
  Early validation was performed using a dead-bug setup with the new RTC manually wired into the existing board. This allowed driver bring-up and signal verification before finalized hardware was available.</li> 
</ol> 


<h2>Challenges</h2> 
<p> <strong>Legacy Firmware Constraints.</strong><br> 
The existing firmware was large, tightly coupled, and not designed with frequent hardware changes in mind. Limited abstraction and sparse documentation made driver integration difficult, as small changes could affect unrelated subsystems. Careful isolation and incremental validation were required to avoid regressions. </p>

<p> <strong>Fine-Pitch Dead-Bug Rework.</strong><br> 
Before finalized hardware was available, the replacement RTC was dead-bugged and soldered under a microscope. Individual wires were attached to fine-pitch pads (approximately 0.5&nbsp;mm pitch across a 16-pad package). The connections were fragile and frequently detached during adjustment and probing, making stable bring-up non-trivial. </p> 

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    <figure class="figure">
      {% include figure.html
        path="assets/img/RTC Replacement/2.jpg"
        class="img-fluid rounded z-depth-1" %}
      <figcaption class="figure-caption">
        Figure 1: Probed RTC
      </figcaption>
    </figure>
  </div>
</div>

<p> <strong>SPI Signal Verification.</strong><br> 
Due to both the legacy codebase and the fragile physical setup, updating the SPI interface was difficult. An oscilloscope was used to directly probe the SPI bus and confirm clock polarity, phase, chip-select behavior, and data validity. This step was critical in distinguishing firmware issues from physical connection failures and confirming successful communication with the RTC. </p> 

<p>
Yellow is CS, Cyan is MISO, Purple is MOSI and Blue is Clk
</p>

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    <figure class="figure">
      {% include figure.html
        path="assets/img/RTC Replacement/3.jpg"
        class="img-fluid rounded z-depth-1" %}
      <figcaption class="figure-caption">
        Figure 2: Dead-bug RTC with fine-pitch soldered leads (microscope view)
      </figcaption>
    </figure>
  </div>
</div>

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    <figure class="figure">
      {% include figure.html
        path="assets/img/RTC Replacement/5.jpg"
        class="img-fluid rounded z-depth-1" %}
      <figcaption class="figure-caption">
        Figure 3: SPI Request
      </figcaption>
    </figure>
  </div>
</div>

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    <figure class="figure">
      {% include figure.html
        path="assets/img/RTC Replacement/1.jpg"
        class="img-fluid rounded z-depth-1" %}
      <figcaption class="figure-caption">
        Figure 4: SPI Request and Receive
      </figcaption>
    </figure>
  </div>
</div>

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    <figure class="figure">
      {% include figure.html
        path="assets/img/RTC Replacement/6.jpg"
        class="img-fluid rounded z-depth-1" %}
      <figcaption class="figure-caption">
        Figure 5: RTC sending Hours, Minutes, Seconds, Day of Week, Day, Month and Yea
      </figcaption>
    </figure>
  </div>
</div>


<h2>Results & Impact</h2> 
<p> The updated driver and SPI integration successfully enabled the new hardware revision, allowing the product to continue shipping despite component obsolescence. The work also established a clearer pattern for supporting future hardware changes, reducing the long-term maintenance burden. </p> 
<p> Without this update, the product would have been blocked by supply chain constraints. With it, the hardware transition became a contained firmware change rather than a full redesign. </p> 

<h2>Conclusion</h2> 
<p> This project demonstrated practical embedded development skills under real-world constraints: legacy code, minimal documentation, hardware uncertainty, and business-critical deadlines. By validating behavior at the signal level and carefully integrating new drivers, the system was extended without destabilizing existing functionality. </p> 

