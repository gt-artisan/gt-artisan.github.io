---
layout: default
title: "Publications — ARTISAN"
permalink: /publications/
---

<div class="simple-pubs">

<h1>Publications</h1>

{% assign pubs = site.data.publications %}
{% if pubs and pubs.size > 0 %}
  {% assign pubs_sorted = pubs | sort: "year" | reverse %}
  {% assign years = pubs_sorted | map: "year" | uniq %}

  {% for y in years %}
  <h2>{{ y }}</h2>
  <ul class="pub-items">
    {% for p in pubs_sorted %}
      {% if p.year == y %}
      <li>
        {% if p.url %}{% assign link = p.url %}
        {% elsif p.doi %}{% assign link = p.doi | prepend: "https://doi.org/" %}
        {% elsif p.arxiv %}{% assign link = p.arxiv | prepend: "https://arxiv.org/abs/" %}
        {% elsif p.pdf %}{% assign link = p.pdf %}
        {% else %}{% assign link = nil %}{% endif %}

        <span class="pub-item-title">
          {% if link %}<a href="{{ link }}">{{ p.title }}</a>{% else %}{{ p.title }}{% endif %}
        </span>

        {% if p.authors and p.authors.size > 0 %}
        <span class="pub-item-authors">{{ p.authors | join: ", " }}</span>
        {% endif %}

        {% if p.venue %}
        <span class="pub-item-venue">{{ p.venue }}, {{ p.year }}</span>
        {% endif %}
      </li>
      {% endif %}
    {% endfor %}
  </ul>
  {% endfor %}

{% else %}
  <p>No publications found.</p>
{% endif %}

<p class="pub-note">This list is generated from <code>_data/publications.bib</code>. Add an entry there and the page updates on the next build.</p>

</div>
