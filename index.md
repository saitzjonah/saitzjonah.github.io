---
title: "Jonah Saitz"
layout: splash
permalink: /
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/spacecraft.jpg
excerpt: "Mechanical Engineering Portfolio"

intro:
  - excerpt: "Featured Work"

feature_row:
  - image_path: /assets/reaction-wheel/images/kepler-reaction-wheels.jpg
    title: "Reaction Wheel"
    excerpt: "A single-axis PID reaction wheel demonstration inspired by satellite attitude control."
    url: "portfolio/reaction-wheel/"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: /assets/uviva/images/anderson_uviva.png
    title: "UViva"
    excerpt: "A wearable device designed to monitor ultraviolet (UV) exposure and hydration for outdoor workers."
    url: "portfolio/uviva/"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: /assets/spiral.jpg
    title: "CAD Models"
    excerpt: "Objects, mechanisms, and assemblies, designed and ready to print."
    url: "cad-models"
    btn_label: "Read More"
    btn_class: "btn--primary"
---
  {% include feature_row id="intro" type="center" %}
  {% include feature_row %}

