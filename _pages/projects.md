---
layout: page
title: projects
permalink: /projects/
description: Research projects of the GeoCASS Lab.
nav: true
nav_order: 4
---

<div class="projects">
  <div class="row row-cols-1 row-cols-md-3">
    {% assign sorted_projects = site.projects | sort: "importance" %}
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
</div>
