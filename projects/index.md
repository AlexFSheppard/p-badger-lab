---
title: Projects
nav:
  order: 2
  tooltip: Collaborations, grants, and more
---

# {% include icon.html icon="fa-solid fa-wrench" %}Projects

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

## Current

{% include list.html component="card" data="projects" filter="group == 'current'" %}

{% include section.html %}

## Completed

{% include list.html component="card" data="projects" filter="!group" style="small" %}
