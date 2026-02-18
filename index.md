---
title: "Jonah Saitz"
layout: splash
permalink: /
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/coffee.jpg
excerpt: "Mechanical Engineering Portfolio"

intro:
  - excerpt: "Featured Work"

feature_row:
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
  - image_path: /assets/arduino-valentine/arduino.jpeg
    title: "Side Projects"
    excerpt: "An assortment of entertaining and occasionally useful weekend builds, with instructions."
    url: "side-projects"
    btn_label: "Read More"
    btn_class: "btn--primary"
---
  {% include feature_row id="intro" type="center" %}
  {% include feature_row %}