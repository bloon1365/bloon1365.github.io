---
layout: page
title: Tank Autoloader
description: A conceptual model of a tank autoloader. Team Project
img: assets/img/Tank Autoloader/1.png
importance: 4
category: Mechanical
---

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>


<h2>Designing a Next-Generation Tank Autoloader System</h2>

Modern battlefield conditions demand high-speed, reliable, and efficient weaponry systems. One such critical component is the tank autoloader, which ensures rapid ammunition delivery while maintaining crew safety. My recent project focused on designing a robust and efficient tank autoloader system, addressing several engineering challenges through a modular and systematic approach.  


<h2>Project Goals and Overview</h2> 

The objective was to design an autoloader capable of reliably handling NATO-standard 120mm rounds, each weighing up to 30 kg, and delivering them seamlessly to the firing chamber. The system was divided into five key subsystems:  

<ul>
    <li><strong>Ammo Belt:</strong> A durable chain-driven belt to transport ammunition.</li>
    <li><strong>Casing:</strong> Secure housings for the rounds, ensuring safe handling.</li>
    <li><strong>Motor Drive:</strong> A high-torque system to power the ammo belt.</li>
    <li><strong>Guide Rail and Blast Door:</strong> Protection and alignment mechanisms.</li>
    <li><strong>Pusher:</strong> A telescoping mechanism to seat rounds into the breach.</li>
</ul>
 

<h2>Subsystem Design Highlights</h2> 

<h3>Ammo Belt</h3> 
The ammo belt was designed as a chain-driven conveyor capable of holding up to 16 rounds. Structural analysis determined the optimal chain specifications, ensuring durability and resistance to the substantial forces exerted by the ammunition. A custom sprocket system was integrated to drive the belt effectively.  

<div class="row">
  <div class="col-sm mt-3 mt-md-0">   
    {% include figure.html path="assets/img/Tank Autoloader/8.png" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<h3>Casing</h3> 
Each casing was made from AISI 304 steel, offering strength and resistance to deformation. The cylindrical design included foam lining to minimize vibration and to secure the rounds in place during operation. Structural analysis confirmed the casings could handle the ammunition's weight under extreme conditions.  

<div class="row">
  <div class="col-sm mt-3 mt-md-0">   
    {% include figure.html path="assets/img/Tank Autoloader/7.png" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<h3>Motor Drive</h3> 
A hydraulic motor with a 1:2 torque ratio chain sprocket system was selected to power the system, ensuring smooth operation even under heavy loads. A chain-drive mechanism was chosen over gears for simplicity and ease of maintenance.  

<div class="row">
  <div class="col-sm mt-3 mt-md-0">   
    {% include figure.html path="assets/img/Tank Autoloader/6.png" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<h3>Guide Rail and Blast Door</h3> 
The blast door, made from 30mm steel, provides critical crew protection by isolating volatile ammunition. It operates on PTFE-lined rails to reduce friction. The guide rail aligns the ammunition with the breach, ensuring smooth transfer.  

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Tank Autoloader/4.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Tank Autoloader/5.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<h3>Pusher</h3>  
The pusher utilizes a telescoping mechanism powered a hydraulic motor and uses chains. Finite Element Analysis (FEA) confirmed the design's reliability under operational stresses. This subsystem prioritizes compactness and performance in extreme environments.  

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Tank Autoloader/2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Tank Autoloader/3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

{% include youtube.html id="6J42oQ2BvFQ" %}


<h2>Full System Integration</h2> 

The modular approach allowed for simultaneous development and testing of individual subsystems. Once completed, the components were integrated into a cohesive system. The motor drive powers the ammo belt, positioning rounds for transfer. The blast door and guide rail ensure safe passage, while the pusher movies the round from the belt into the breach.  

<div class="row">
  <div class="col-sm mt-3 mt-md-0">   
    {% include figure.html path="assets/img/Tank Autoloader/1.png" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<h2>Future Improvements</h2>  
While the design meets current requirements, future iterations could include:  
<ul>
    <li>Optimized hydraulic components to reduce weight.</li>
    <li>Modular clamps in the casing for enhanced ammunition stability.</li>
    <li>A smaller pusher design more in line with the force needed to move the shells. This would also allow the blast door to be smaller.</li>
    <li>A smaller motor drive with more common part sizing.</li>

</ul>
The current design is a good first prototype but has some drawbacks that could be mitigated in a redesign. 


<h2>Conclusion</h2>  

This project demonstrated the importance of a structured, modular approach in tackling complex engineering challenges. By integrating advanced design principles and thorough testing, the tank autoloader system offers significant improvements in speed, safety, and reliability for modern armored vehicles.  


<h2>Additional Notes</h2>  

Find the project report PDF attached <a href="/assets/pdf/Tank Autoloader/1.pdf" download>here</a> as well as a <a href="/assets/pdf/Tank Autoloader/BOM.pdf" download>BOM</a>.
The drawings for all manufactured parts are included at the end of the report. It's worth noting that these drawings are used to show rough dimensions of parts and are not in an finalized state that could be sent to a manufacturer.
My specific contributions to this project were:
<ul>
    <li>Organizing what each team member was working on and communicating with the team to make sure the end product was understood throughout development.</li>
    <li>Designing the guide rail and blast door subsystem and running appropriate FEA test to ensure performance.</li>
    <li>Designing the Pusher Subsystem.</li>
    <li>I acted as a resource for team members, offering guidance and sharing expertise to ensure we met our project goals effectively.</li>
</ul>

