---
layout: page
permalink: /publications/
title: publications
description: My publications. This page might be outdated, for the latest records check out my <a href="https://orcid.org/0000-0002-0125-1472"><u>ORCiD</u></a>.
years: [2022, 2023]
nav: true
---

<div class="publications">

{% for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
