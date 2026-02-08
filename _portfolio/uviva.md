---
layout: single
permalink: /projects/uviva-project/
author_profile: true
classes: wide
title: UViva
excerpt: Wearable UV and hydration tracker
header:
  overlay_image: /assets/uviva/images/anderson_uviva.png
  teaser: /assets/uviva/images/anderson_uviva.png
date: 2026-01-30
---

## Overview

UViva is a low-cost wearable device that monitors UV exposure and relative hydration for outdoor workers, designed, prototyped, and tested over one semester at Brown University. The project emphasized the tradeoffs between sensing accuracy, cost, comfort, and manufacturability inherent to engineering design.

![Render](/assets/uviva/images/finalrender_uviva.png)

<sub>**Figure 1:** Photograph of UViva final prototype.</sub>

### Metadata
* **Role:** Mechanical / Systems Engineer - focused on sensor integration, mechanical validation, 3D printing, and testing.
* **Timeline:** Fall 2025 (1 semester)
* **Team Size:** 6
* **Tools:** Onshape, ESP32-C3, GUVA-S12SD, HTML/CSS, 3D printing (FDM), soldering iron

<br>

![Iterations](/assets/uviva/images/iterations_uviva.png)

<sub>**Figure 2:** UViva iterations from September-December 2025.</sub>

### My Contributions
* Measured microcontroller and sensors with calipers to determine minimum enclosure dimensions to accommodate components.
* Built breadboard proof-of-concept circuit with ESP32, UV, and hydration sensors.
* Refined enclosure design through 4 CAD iterations, adding features such as metal contacts for hydration sensing and a charging port.
* Integrated UV and hydration sensors into enclosure, positioning sensors to minimize space, prevent interference, and ensure comfortable weight distribution.
* Tested prototype using blacklight, sunlight, and hydration experiments, measuring sensor response against baselines over 10 trials to verify accuracy and repeatability. 

<br>

![Sensors](/assets/uviva/images/sensors_uviva.png)

<sub>**Figure 3:** Electronics used in UViva: ESP32-C3 (left), GUVA-S12SD (top right), lithium-ion polymer battery (bottom right).</sub>

### Challenges
* UV accuracy limitations: The low-cost GUVA-S12SD sensor had poor responsivity in the UV range most associated with skin cancer (280-320 nm), leading to noisy and imprecise readings and an error rate of 37%.
* Hydration proxy uncertainty: Skin capacitance behaved differently than expected, returning to baseline 15 minutes after hydration instead of showing sustained change.
* Environmental noise: Real-world testing (winter, low UV conditions) amplified sensor error compared to expectations.
* Form factor constraints: Space limitations ruled out a dedicated capacitance IC, forcing a less precise improvised solution.

<br>

![Responsivity](/assets/uviva/images/responsivity_uviva.png)

<sub>**Figure 4:** Graph of GUVA-S12SD responsivity given incident wavelength.</sub>

### Solutions
* Compared UV readings against weather station UV indices to calculate measurement error.
* Iterated enclosure design to ensure sensor fit, consistent skin contact for the hydration sensor, and unobstructed UV readings.
* Prioritized affordability, comfort, and manufacturability over lab-grade precision. 
* Designed system modularly to improve ease of future revisions.

<br>

![Measurements](/assets/uviva/images/measurements_uviva.png)

<sub>**Figure 5:** Table and graph of measured UV Indices from GUVA-S12SD versus expected UV Indices from local weather data.</sub>

### Tradeoffs
* Selected inexpensive, widely available sensors to keep the device affordable and scalable.
* Designed slim, subtle enclosure to maximize wearability, instead of a bulkier form factor that may have fit more sensors. 
* Focused on proof-of-concept functionality rather than long-term clinical validation. 
* Designed to be non-invasive, avoiding biological sampling or recording sensitive data.

<br>

![Capacitance](/assets/uviva/images/capacitance_uviva.png)

<sub>**Figure 6:** Graph of skin capacitance output over time after drinking electrolyte beverage.</sub>

### Evaluation 
* Built a functional end-to-end system featuring wearable hardware, embedded electronics, and a live web dashboard.
* Incorporated survey feedback from outdoor workers to prioritize comfort, durability, and subtlety. 
* Sleek wristband form factor avoids dangling jewelry hazards in construction environments, in accordance with OSHA standards. 
* Low-cost components and simple electronics make the system scalable and manufacturable. 
* Non-invasive sensing is ethical, with clear benefit to workers and minimal risk.

<br>

![Website](/assets/uviva/images/website_uviva.png)

<sub>**Figure 7:** UViva web dashboard proof-of-concept.</sub>

### Future Work
* Improve sensing accuracy by replacing aluminum touch pad with a miniaturized bioimpedance sensor, and upgrading to a UV sensor with stronger UVB responsivity. 
* Add smart insights such as hydration and sunscreen reapplication alerts.
* Implement cumulative UV exposure tracking.
* Improve manufacturability by designing a custom PCB, applying DFM principles, and transitioning from 3D printing to injection molding. 

### Contributors
* Leah Derenge
* Mary Gueye
* Noah Purrow
* Anderson Todd
* Ruth Villicana

<br>

For a more rigorous treatment of this project, the full paper is linked [here](/uviva-paper/).