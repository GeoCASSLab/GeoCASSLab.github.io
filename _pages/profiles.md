---
layout: page
permalink: /people/
title: people
description: members of the Geospatial Cyberinfrastructure & Algorithms for Spatial Science (GeoCASS) Lab
nav: true
nav_order: 2
---

{%- comment -%} Roster lives in \_data/people.yml. Groups with no members are skipped. {%- endcomment -%}
{% for group in site.data.people %}
{% if group.members.size > 0 %}

<h2 id="{{ group.id }}" class="mt-4">{{ group.title }}</h2>
<hr>
{% if group.id == 'alumni' %}
<ul>
{% for m in group.members %}
<li>
<strong>{{ m.name }}</strong>
{% if m.degree or m.years %}({{ m.degree }}{% if m.degree and m.years %}, {% endif %}{{ m.years }}){% endif %}
{% if m.now %}&mdash; {{ m.now }}{% endif %}
{% for l in m.links %}
{% if forloop.first %}&middot;{% endif %}
<a href="{{ l.url }}">{{ l.label }}</a>{% unless forloop.last %}, {% endunless %}
{% endfor %}
</li>
{% endfor %}
</ul>
{% else %}
{% for m in group.members %}
<div class="row mb-4">
{% if m.image %}
<div class="col-sm-3 mb-3">
{% assign member_image_path = m.image | prepend: 'assets/img/' %}
{% if group.id == 'director' %}
{% assign member_image_class = 'img-fluid z-depth-1 rounded' %}
{% else %}
{% assign member_image_class = 'img-fluid z-depth-1 rounded-circle' %}
{% endif %}
{% include figure.liquid loading="eager" path=member_image_path class=member_image_class alt=m.name %}
</div>
{% endif %}
<div class="{% if m.image %}col-sm-9{% else %}col-12{% endif %}">
<h3>{{ m.name }}</h3>
{% if m.role %}<p><em>{{ m.role }}</em></p>{% endif %}
{{ m.bio | markdownify }}
<p class="mb-0">
{% if m.address %}{{ m.address }}<br>{% endif %}
{% if m.email %}<a href="mailto:{{ m.email }}">{{ m.email }}</a>{% endif %}
{% for l in m.links %}
{% if forloop.first and m.email %}&middot;{% endif %}
<a href="{{ l.url }}">{{ l.label }}</a>{% unless forloop.last %}, {% endunless %}
{% endfor %}
</p>
</div>
</div>
{% endfor %}
{% endif %}
{% endif %}
{% endfor %}
