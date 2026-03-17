---
layout: default
title: "Projects — ARTISAN"
permalink: /projects/
---

# Projects

{% for item in site.data.projects %}
<div class="project-card">
<div class="project-info">
<h3>{{ item.name }}</h3>
<p>{{ item.blurb }}</p>
<div class="project-links">
<a href="{{ item.url }}" target="_blank">Website</a>
{% if item.github and item.github != "" %}
<a href="{{ item.github }}" target="_blank">GitHub</a>
{% endif %}
</div>
</div>
</div>
{% endfor %}
