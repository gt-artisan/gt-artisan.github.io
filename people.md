---
layout: default
title: "People — ARTISAN"
permalink: /people/
---

<header class="people-page-header">
  <span class="people-page-eyebrow">Our Community</span>
  <h1>People</h1>
  <p>A diverse and interdisciplinary group of faculty, researchers, and collaborators advancing the frontiers of science, AI, and cyberinfrastructure.</p>
</header>

{% assign alphabetical_people = site.data.people | sort: "name" %}
{% assign resident_scientists = alphabetical_people | where: "people_group", "resident-scientists" %}
{% assign resident_engineers = alphabetical_people | where: "people_group", "resident-engineers" %}
{% assign affiliated_scientists = alphabetical_people | where: "people_group", "affiliated-scientists" %}
{% assign collaborators = alphabetical_people | where: "people_group", "collaborators" %}
{% assign students = alphabetical_people | where: "people_group", "students" %}
{% assign alumni = alphabetical_people | where: "people_group", "alumni" %}

<section class="people-group" id="resident-scientists">
  <div class="people-group-heading"><h2>Resident Scientists</h2></div>
  <div class="people-directory">
    {% for person in resident_scientists %}{% include person-profile.html person=person %}{% endfor %}
  </div>
</section>

<section class="people-group" id="resident-engineers">
  <div class="people-group-heading"><h2>Resident Research &amp; Systems Engineers</h2></div>
  <div class="people-directory">
    {% for person in resident_engineers %}{% include person-profile.html person=person %}{% endfor %}
  </div>
</section>

<section class="people-group" id="affiliated-scientists">
  <div class="people-group-heading"><h2>Affiliated Scientists</h2></div>
  <div class="people-directory">
    {% for person in affiliated_scientists %}{% include person-profile.html person=person %}{% endfor %}
  </div>
</section>

<section class="people-group" id="collaborators">
  <div class="people-group-heading"><h2>Collaborators</h2></div>
  <div class="people-directory">
    {% for person in collaborators %}{% include person-profile.html person=person %}{% endfor %}
  </div>
</section>

<section class="people-group" id="students">
  <div class="people-group-heading"><h2>Students</h2></div>
  {% if students.size > 0 %}
  <div class="people-directory">
    {% for person in students %}{% include person-profile.html person=person %}{% endfor %}
  </div>
  {% else %}
  <p class="people-group-empty">Profiles will be added here.</p>
  {% endif %}
</section>

<section class="people-group" id="alumni">
  <div class="people-group-heading"><h2>Alumni</h2></div>
  {% if alumni.size > 0 %}
  <div class="people-directory">
    {% for person in alumni %}{% include person-profile.html person=person %}{% endfor %}
  </div>
  {% else %}
  <p class="people-group-empty">Profiles will be added here.</p>
  {% endif %}
</section>
