---
title: Funding
nav:
  order: 2
  tooltip: Collaborations, grants, and more
---

# {% include icon.html icon="fa-solid fa-wrench" %}Projects

Below is a list of current and recently completed grant funded projects for our lab. 

## Current

{% include list.html component="card" data="projects" filter="group == 'current'" %}

{% include section.html %}

## Completed

{% include list.html component="card" data="projects" filter="!group" style="small" %}
