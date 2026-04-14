---
permalink: /
title: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% assign start = site.site_start_date | date: "%s" %}
{% assign now = "now" | date: "%s" %}
{% assign days = now | minus: start | divided_by: 86400 %}

Site has been running for {{ days }} days 

I am a Master's student at Dalian University of Technology.  
My research focuses on neural interface systems, deep learning, and human-machine interaction.

## Education
- **Master of Science (M.S.)** in Mechanical Engineering, Department of Mechanical Engineering, Dalian University of Technology, China, 2023.09 ~ Present (2026.06)  

- **Bachelor of Engineering (B.E.)** in Mechanical Design, Manufacturing, and Automation, Department of Mechanical Engineering, Dalian University of Technology, China, 2019.09 ~ 2023.06

## Work
<p align="center">
  <img src="/images/github-单元.png" width="40%">
  <br>
  <strong>Electromyography Acquisition Unit Ver.1</strong>
</p>

<p align="center">
  <img src="/images/github-system.png" width="30%">
  <br>
  <strong>High-throughput Electromyography Acquisition System Ver.1</strong>
</p>

## Awards
- Second-Class Scholarship, Bachelor’s Program (Dalian University of Technology), 2021
- Master’s First-Class Scholarship (Dalian University of Technology), 2023  
- Master’s First-Class Scholarship (Dalian University of Technology), 2024  
- Master’s First-Class Scholarship (Dalian University of Technology), 2025
