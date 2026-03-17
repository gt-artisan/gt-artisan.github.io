---
layout: default
title: "Projects — ARTISAN"
---

# Projects
{% for item in site.data.projects %}
### {{ item.name }}

{{ item.blurb }}

[Website]({{ item.url }})
{% if item.github and item.github != "" %}
| [GitHub]({{ item.github }})
{% endif %}

{% endfor %}

<!--
<div class="grid">
{% for item in site.data.projects %}
  <article class="card">
    <h3 class="text-navy">{{ item.name }}</h3>
    <p>{{ item.blurb }}</p>
    {{ item.url }}</a>
  </article>
{% endfor %}
</div> -->
