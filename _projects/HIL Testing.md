---
layout: page
title: Hardware-In-Loop Testing
description: Hardware-In-Loop testing infrastructure. Work Project
img: 
importance: 1
category: 
  - Software
related_publications:
---

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

<h2>Project Overview</h2> This project involved the design and implementation of a Hardware-in-the-Loop (HIL) testing framework for a marine gyroscopic stabilizer under active development at Dometic Marine. The goal was to create a repeatable, reliable way to validate safety-critical firmware directly on a fully assembled gyro unit, keeping pace with rapid software changes while reducing regressions and manual testing overhead.

The system enables deterministic fault injection, state-machine verification, and system-level validation by manipulating sensor inputs and CAN traffic while observing real firmware behavior on production hardware.

<h2>System Architecture</h2> 
<ol> 
  <li><strong>Hardware-in-the-Loop Test Environment:</strong><br> 
  Firmware is executed on a fully assembled gyroscopic stabilizer rather than a simulated or bench-level setup. This ensures that firmware interacts with real sensors, ECUs, and hardware timing characteristics while still allowing controlled test conditions.</li> 
  <li><strong>CAN-Based Test Control:</strong><br> 
  A CAN-to-USB interface is used to inject sensor values, override internal variables, and force state transitions. This allows precise control of system inputs without modifying firmware or physically manipulating hardware.</li> 
  <li><strong>Automated Test Execution:</strong><br> 
  Tests are written in Python and executed using Pytest. Each test applies deterministic CAN messages, monitors system responses, and verifies expected diagnostic flags, state transitions, and timing behavior.</li> 
  <li><strong>Initialization & Reset Logic:</strong><br> 
  A robust initialization routine ensures every test starts from a known state. This includes ECU resets, clearing diagnostic flags, restoring configuration defaults, and running an automated calibration routine when required.</li> 
</ol> 

<h2>Key Technical Contributions</h2> 
<ol> 
  <li><strong>Deterministic Fault Injection:</strong><br> 
  Sensor values and internal parameters can be forced across diagnostic thresholds to reliably trigger faults such as low battery voltage, sensor invalid states, and safety interlocks. This enables repeatable validation of fault handling logic.</li> 
  <li><strong>State-Machine Verification:</strong><br> Tests confirm correct progression through operational, locked, calibration, and fault states, including timing consistency and recovery behavior once fault conditions are cleared.</li> 
  <li><strong>Test Isolation & Repeatability:</strong><br> 
  Tests are designed to be fully independent. Any interrupted or failed run can be restarted without manual cleanup, preventing false failures caused by residual system state.</li> 
</ol> 

<h2>Results</h2> 
<p> The HIL framework consistently detected deviations in firmware behavior across revisions, including timing changes, altered diagnostic thresholds, and unexpected state transitions. Tests proved reliable across repeated runs and multiple firmware branches, providing a dependable baseline for regression testing. </p> 
<p> Compared to the previous manual workflow, firmware validation became faster, more consistent, and significantly less error-prone. Issues that previously surfaced late in development were caught immediately during HIL testing. </p> 

<h2>Impact</h2> 
<p> This framework closed the gap between rapid firmware development and insufficient manual testing. It reduced regression risk, improved developer confidence in new changes, and established a scalable foundation for future automation. The system is well-suited for integration into a CI pipeline where firmware changes are automatically validated before merging. </p> 

<h2>Conclusion</h2> 
<p> This project delivered a practical, production-relevant HIL testing system for a safety-critical marine product. By enabling repeatable system-level validation on real hardware, it significantly improved firmware reliability and development velocity. The framework mirrors industry best practices used in automotive and robotics environments and provides a strong base for future automated and continuous-integration testing. </p>