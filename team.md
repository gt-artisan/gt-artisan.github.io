---
title: "ARTISAN Team — Georgia Tech"
---
<link rel="stylesheet" href="/assets/css/team.css">

# ARTISAN Team

The ARTISAN team includes researchers, engineers, and collaborators working on
AI-enabled systems and cyberinfrastructure for science and engineering.

<!-- Old team layout disabled 

<div class="grid">
{% for person in site.data.team %}
  <div class="card">
    <h3 class="text-navy" style="margin-bottom:.25rem;">{{ person.name }}</h3>
    <p style="margin-top:0;">{{ person.title }}</p>
    <p>
    {% if person.scholar %} {{ person.scholar }}</a>{% endif %}
    {% if person.linkedin %} · {{ person.linkedin }}</a>{% endif %}
    </p>
  </div>
{% endfor %}
</div>
-->

<div class="team-container">

{% for person in site.data.team %}

<div class="team-card">

<img src="{{ person.photo }}" class="team-photo">

<div class="team-info">

<h3>{{ person.name }}</h3>

<p class="team-title">{{ person.title }}</p>

<p class="team-focus">
<strong>Research focus:</strong> {{ person.research_focus }}
</p>

<p>{{ person.short_bio }}</p>

<div class="team-projects">
{% for project in person.projects %}
<span class="project-tag">{{ project }}</span>
{% endfor %}
</div>

<div class="team-links">

{% if person.scholar %}
<a href="{{ person.scholar }}">Scholar</a>
{% endif %}

{% if person.linkedin %}
<a href="{{ person.linkedin }}">LinkedIn</a>
{% endif %}

{% if person.github %}
<a href="{{ person.github }}">GitHub</a>
{% endif %}

</div>

</div>
</div>

{% endfor %}

</div>
