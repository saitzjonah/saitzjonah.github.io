---
layout: single
permalink: /projects/uviva-project/
author_profile: true
classes: wide
title: UViva
excerpt: Wearable UV and hydration tracker
header:
  overlay_image: /assets/anderson_uviva.png
  teaser: /assets/anderson_uviva.png
date: 2026-01-30
---

## Abstract

Outdoor workers face significant risks from dehydration and ultraviolet (UV) overexposure, which can lead to heat-related illness and long-term skin damage. This project focuses on developing a wearable device that monitors hydration and UV exposure to promote early awareness of these risks. The design prioritizes affordability, reliability, and ease of use to ensure practicality for workers in construction and similar outdoor environments.

## Introduction

Outdoor workers were chosen as the target group for this project, as they are both an at-risk and often overlooked group. In fact, occupational sun exposure increases the risk of non-melanoma skin cancer (NMSC) by 60% for outdoor workers. This cancer is directly linked to excessive UV exposure. Tracking this exposure over time would provide valuable health data to workers and employers alike.

Additionally, outdoor workers are at an increased risk for heatstroke and kidney stress. Tracking hydration levels in the short-term can help keep workers hydrated and energized, boosting physical and intellectual productivity over the course of the workday. Long-term tracking of hydration could potentially help workers avoid illnesses associated with chronic dehydration.

Numerous UV trackers and hydration sensors have already been brought to market, constituting the precedent work that informed this project. Notably, the Sun-A-Wear UV Tracker is a solar-powered portable sensor that sends UV exposure data to an app in real time. Also, the Hydration Patch is a battery-free, capacitance-based skin hydration sensor that also sends data to an app. Notably, few products on the market effectively combine UV tracking with hydration sensing, which represents an area for continued innovation.

Finally, before detailing the design procedure for the wearable device, it is necessary to comment on skin capacitance as a proxy for hydration. Skin capacitance, though not a precise measure of hydration, is an effective single metric that effectively tracks hydration changes over time. Skin capacitance responds reliably to changes in the skin's dielectric properties. And, perhaps most importantly, it is both cheap and non-invasive, making it a practical choice for a wearable hydration sensor.

## Design

UViva was designed iteratively over the course of a single semester, with the majority of the work occurring in October and November of 2025. In order to simplify the design process, UViva was separated into three subsystems: Structures, Electronics, and UI, each working in tandem.

### Structures

![Iterations](/assets/images/iterations_uviva.png)
<sub>Figure 1</sub>

The most visible aspect of UViva is the wearable itself, meaning that the housing design had to be both functional and attractive. 
Physical measurements were taken of the microcontroller, sensors, and battery to determine size constraints for the housing. The housing was designed in Onshape, with a larger design at first which was subsequently downsized and refined, as seen in Figure 1.

Two additional design constraints were the hole in the top of the wearable device, allowing for sunlight to reach the UV sensor, and a slit in the bottom of the wearable device, where a strip of metal contacts the skin, allowing for hydration data to be recorded.

### Electronics

Given the stated project goals of affordability and practicality, UViva was designed with simple internal electronics.

![Sensors](/assets/images/sensors_uviva.png)
<sub>Figure 2</sub>

* The Seeed Studio XIAO ESP32-C3 was chosen as the microcontroller for UViva due to its small size and Wi-Fi capabilities. For interested readers, the ESP32-C3 Series datasheet is linked [here](/assets/esp32-c3_datasheet.pdf).
* The GUVA-S12SD sensor was chosen as the UV sensor for UViva due to its ubiquity and affordability, despite its limited responsivity and precision. The GUVA-S12SD datasheet is linked [here](/assets/1918guva.pdf).
* No dedicated sensor was used for the capacitance sensor for the present wearable device model, due to space constraints. Instead, a small sheet of aluminum was used to contact the skin and send approximate skin capacitance values to the ESP32-C3.
* Finally, the wearable device used a standard 3.7V, 1200 mAh lithium-ion polymer battery, the datasheet of which is linked [here](/assets/lipo-datasheet.pdf).

### User Interface (UI)

UViva solicited feedback on design and functionality from outdoor workers in the form of a survey. Survey respondents showed interest in the product, and indicated that a wristband was their preferred form factor, and that comfort, durability, and subtlety were their preferred attributes. Design was undertaken with these constraints in mind.

![Website](/assets/images/website_uviva.png)
<sub>Figure 3</sub>

UViva also incorporated a website to track and visualize UV exposure and hydration data, as seen in Figure 3. Data collected by the wearable device can be sent to the website in real time, using the ESP32-C3's Wi-Fi capabilities. Though simple in its present form, this website has numerous use cases and areas for growth. 

As a first use case, the website allows outdoor workers to monitor their own UV exposure and hydration. For outdoor workers on the job, it may be more convenient to access this data on mobile. The present form of the site supports mobile viewing, though in the future, an app may prove more convenient. 

The second, and likely more valuable use case, is an expanded dashboard for tracking company-wide data. Company leadership can use this data to track the well-being of their workforce and inform insurance negotiations.

## Testing

### UV Tracking

The first test of the GUVA-S12SD sensor used a blacklight to establish a baseline. 

![Responsivity](/assets/images/responsivity_uviva.png)
<sub>Figure 4</sub>

As shown in Figure 4, the GUVA-S12SD only responds to ultraviolet wavelengths between 240 - 380 nanometers (nm). 280 - 315 nm, or UVB, is the range of ultraviolet most responsible for sunburn and most linked to skin cancers. Notably, the responsivity curve in Figure 4 peaks between 340 - 360 nm, outside the range of UVB. Thus, it is clear that the GUVA-S12SD is suboptimal, though adequate within the confines of this project. 

The blacklight used for the test emitted waves around 365 nm. These rays were detected by the GUVA-S12SD, albeit weakly, as 365 nm is higher than the GUVA-S12SD's peak responsivity. 

![Measurements](/assets/images/measurements_uviva.png)
<sub>Figure 5</sub>

The second test involved comparing the UV exposure measured by the wearable device to the UV index recorded by local weather stations. The graph in Figure 5 shows significant error, though this is expected due to the imprecision of the GUVA-S12SD, as well as the low-UV conditions of winter in Rhode Island, where these measurements were taken.

### Hydration Sensing

In order to test the capacitive touch pad, a simple user experiment was conducted. First, the user's baseline skin capacitance was established by recording skin capacitance for a short period. Then, the user drank 24 fluid ounces of Gatorade, and skin capacitance data was recorded over the next 30 minutes. 

![Capacitance](/assets/images/capacitance_uviva.png)
<sub>Figure 6</sub>

Figure 6 shows the response of skin capacitance to hydration: an increase in capacitance over the first 15 minutes after drinking, followed by a return to near-baseline. This return to baseline ran counter to the UViva team's hypothesis about the effect of hydration on skin capacitance, and represented a clear area for future study.


## Evaluation

UViva succeeded as a proof of concept under time and budgetary constraints. The wearable device incorporated user survey feedback diligently, by designing a comfortable, durable, and subtle wristband that outdoor workers would be able to wear without annoyance or distraction. Furthermore, the wearable design is snug, avoiding the dangling jewelry restriction set by OSHA in construction and other hazardous outdoor work environments.

The device uses affordable sensors and simple design, making it easy to scale and manufacture in the future. The affordability factor also makes UViva accessible to a wide range of employers, from nationwide construction companies to local landscaping crews.

And finally, the design is ethical, featuring non-invasive sensors that do not take biological samples.

## Societal Considerations

UViva aids the mission of global occupational health, by offering a novel method of preventative care for high-risk outdoor workers. Furthermore, it promotes occupational equity, by supporting consistent sun protection across job sites, regardless of individual awareness or behavior.

UViva also has the potential to lower long-term healthcare costs, as skin cancer treatment for outdoor workers is an expensive yet reducible burden on the healthcare system. Additionally, documented enforcement of safety policies, backed by data, can potentially lower costs for corporate insurance premiums.

## Future design changes

UViva's initial prototype and feedback indicate numerous areas for design changes and improvements. The UI could be improved by adding sunscreen reapplication or hydration reminders. Additional changes include enabling long-term cumulative exposure logging, either onboard or cloud-based, developing a proprietary software dashboard for supervisors to monitor workforce health data, improving hydration data accuracy with a miniaturized bioimpedance sensor, and finally, optimizing and scaling manufacturing processes with a printed circuit board (PCB), design for manufacturability (DFM), and injection molding.

![Render](/assets/finalrender_uviva.png)

## Contributors

* Leah Derenge
* Mary Gueye
* Noah Purrow
* Anderson Todd
* Ruth Villicana