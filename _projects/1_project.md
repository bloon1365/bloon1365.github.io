---
layout: page
title: Robot Arm Motion Profiler
description: A motion profiler for a two degree of freedom robot arm. 
img: assets/img/Robot Arm Motion Profiler/1.png
importance: 1
category: Software
related_publications:
---

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

For a final project a professor challenged us to design a two-dimentional, two degree of freedom robotic arm that would allow for automated machining of precise shapes. Namely two letters of the alphabet must be chosen and placed within the quadrants surrounding the first joint (Figure 1). For these letters a path must be chosen and all kinematics and kinetics of both arms must be graphed. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0"> 
        {% include figure.html path="assets/img/Robot Arm Motion Profiler/1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1. Project Description
</div>

Our criteria were as follows:

 <ol>
  <li>Constant speed during “active” regions (parts where the end effector is in use to make the letters)</li>
  <li>Must start and end operation at a designated home position</li>
  <li>Instant acceleration cannot occur so an acceleration region must be made before each segment of a drawing</li>
  <li>Design of arm must include motor choice that matches requirements of trajectory path chosen and the kinematics and kinetics required (torque)</li>
  <li>A comprehensive explanation of the system/robot design.</li>
</ol> 


To complete the outlined goals, a path must be defined in 2D cartesian space that our robot will follow. To do this a SVG image is decoded and converted to the (X,Y) coordinate space. Through this decoding we find lines and curves to match the input image and define waypoints along this path to mark where the end effector should move to. Instead of hardcoding for a specific task, decoding SVG images allows for utmost flexibility and rapid iteration of designs and greatly improves the effectiveness of the robot and allows us to display any letter with ease as well as any basic image.

To construct a motion profile where we have a constant velocity along curves and a maximum acceleration value we need to know the distance needed to accelerate our end effector to the desired speed before it hits a curve. We decided to use Python and generalize our code to work with any SVG drawing made of lines and cubic Bezier curves.

We decode the SVG, getting equations of lines we want to draw. We can then use simple kinematics to obtain the distance we need to accelerate to the desired speed.

<centre>
$$ {accelerationTime =\frac{maxSpeed}{acceleration}} $$
$$ {accelerationDistance =\frac{1}{2} * acceleration * accelerationTime} $$
</centre>

By taking the derivative of the ends of the curves we can identify the direction we need to be accelerating in. We can then use the accelerationDistance to know how far from the point we have to be. Using this information, we can make a motion profile from these acceleration points to the start of any curve.

Maintaining a constant velocity on a curve is relatively simple task on a straight line, using this formula:

<centre>
$$ {Velocity =\frac{Distance}{Time}} $$
</centre>

When Velocity and time are already known, simply move a set distance per "frame" (set unit time). The problem becomes more complicated when dealing with cubic Bezier curves. Determining the arc length of these curves is very difficult. After trying a variety of methods, I settled on a numerical method of approximating the curves by estimating them as a large number of small straight lines. This method works well but accumulates error that at the end of the curve will cause unacceptable "jumps" in velocity and acceleration values. Because of this the approximation has to be very accurate resulting in ~320000 lines being used to approximate an average sized curve. With this accurate approximation of arc length we can use our formula  to know that we need to travel a certain distance over the curve for a set amount of time.

To connect the ends of the acceleration points together we need a third movement type that will not activate the end effector and also does not need to have a max speed. To achieve the fastest line the end effector must be accelerating for half the time and decelerating for the other half of the time.

<div class="row">
    <div class="col-sm mt-3 mt-md-0"> 
        {% include figure.html path="assets/img/Robot Arm Motion Profiler/2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 2. “ABCD” Path
</div>


Figure ABCD shows an exaggerated view of how our program calculates the trajectory. The red dots are the points we begin accelerating at to achieve the desired velocity at the black lines. The green lines are our moves that connect those red dots.

<div class="row">
    <div class="col-sm mt-3 mt-md-0"> 
        {% include figure.html path="assets/img/Robot Arm Motion Profiler/3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div><div class="caption">
    Figure 3. Tip Acceleration (red) and Velocity (green) Vs Time.
</div>

Figure 8 shows an example of 3 moves. The 2 triangular movements correspond to the green lines in Figure 7 where speed does not matter and the goal is to get to the next acceleration point. This move has ¼ the acceleration to ensure that the speed does not cause a torque value too high for our motors. The trapezoidal movement is before, during and after the line demonstrating constant velocity while on the line and a maximum acceleration that is set in code during the acceleration and deceleration period.
The repository for this project can be found <a href="https://github.com/bloon1365/MSE-222-Project/blob/main/Main.py">here</a>. 

<iframe width="420" height="315"
src="https://www.youtube.com/watch?v=PxCg69aCiuo">
</iframe> 
<iframe width="420" height="315"
src="https://www.youtube.com/watch?v=-mY53fkrlsE">
</iframe> 
