---
layout: default
title: People
---

# People

The ARTISAN team includes researchers, engineers, and collaborators working on
AI-enabled systems and cyberinfrastructure for science and engineering.

## Team

<ul class="people-list">
{% for person in site.data.team %}
  <li>
    <strong>{{ person.name }}</strong><br>
    {{ person.title }}

    {% if person.scholar %}
      <br><a href="{{ person.scholar }}">Google Scholar</a>
    {% endif %}

    {% if person.linkedin %}
      · <a href="{{ person.linkedin }}">LinkedIn</a>
    {% endif %}
  </li>
{% endfor %}
</ul>
