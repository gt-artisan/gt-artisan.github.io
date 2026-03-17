---
layout: default
title: "Scientific Software — ARTISAN"
permalink: /scientific-software/
---

<link rel="stylesheet" href="/assets/css/software.css">

# Scientific Software

ARTISAN develops and supports open software platforms that enable scientific workflows, secure access, data movement, and research applications across distributed computing environments.

<div class="software-grid">
{% for item in site.data.software %}
  <div class="software-card">
    <h3>{{ item.name }}</h3>
    <p>{{ item.desc }}</p>
    <p><a href="{{ item.url }}">Learn more</a></p>
  </div>
{% endfor %}
</div>

<!--
<div class="grid">
{% for s in site.data.software %}
  <article class="card">
    <h3 class="text-navy">{{ s.name }}</h3>
    <p>{{ s.desc }}</p>
    {{ s.url }}</a>
  </article>
{% endfor %}
</div>
-->
