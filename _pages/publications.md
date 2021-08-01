---
layout: page
permalink: /publications/
title: publications
description: My publications. This page will hopefully be filled as time goes by!
years: [2021]
nav: true
---

<div class="publications">

{% for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
