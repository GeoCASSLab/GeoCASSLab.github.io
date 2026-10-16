---
layout: about
title: about
permalink: /
subtitle: Geospatial Cyberinfrastructure & Algorithms for Spatial Science (GeoCASS) Lab
selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false # no blog posts yet; the blog page is hidden from the navbar
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

<div class="mb-4 p-3 rounded text-center" style="background-color: #fff">
  <img src="{{ '/assets/img/geocass-banner.drawio.png' | relative_url }}" alt="GeoCASS: Geospatial Cyberinfrastructure & Algorithms for Spatial Science" class="img-fluid" style="max-height: 120px">
</div>

Welcome to the **Geospatial Cyberinfrastructure & Algorithms for Spatial Science (GeoCASS) Lab** at The University of Texas at Dallas, directed by [Dr. Alexander Michels](/people/), Assistant Professor of GIS in the School of Economic,
Political and Policy Sciences.

We use geospatial data science and cyberGIS to tackle societal challenges. Our research interests include geospatial data science, cyberGIS, spatial accessibility
analysis, and high-performance computing for geographic problems.

<!-- TODO: expand with the lab's mission and any additional research themes. -->

See our [publications](/publications/) and [projects](/projects/), and meet the team on the [people](/people/) page.

**Join us:** we are recruiting 1-2 PhD students for the UTD GIS Program with Fall 2027 enrollment, and we are open to mentoring students of all levels and
backgrounds whose interests align with our research. Competitive PhD applicants typically already have a Master's degree (or equivalent), a background in GIS or a
related field, and some research experience. Reach out using the links below.

## Supported by

{% for funder in site.data.funders %}
{% if funder.logo %}
<a href="{{ funder.url }}"><img src="{{ funder.logo | prepend: '/assets/img/' | relative_url }}" alt="{{ funder.name }}" height="80"></a>
{% endif %}

  <p>
    <a href="{{ funder.url }}">{{ funder.name }}</a>:
    {% for award in funder.awards %}
      {% if award.project %}<a href="{{ award.project | relative_url }}">{{ award.title | split: ":" | first }}</a>{% else %}{{ award.title }}{% endif %}
      (<a href="{{ award.url }}">Award {{ award.number }}</a>){% unless forloop.last %}; {% endunless %}
    {% endfor %}
  </p>
{% endfor %}
