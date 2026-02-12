---
title: "Publications — ARTISAN"
---

# Publications

{% comment %}
Assumptions about _data/publications.yml (produced by the BibTeX → YAML Action):
- top-level is a list (array) of objects
- fields: title (string), authors (list OR string), year (string), venue (string, optional)
- optional: doi, url, pdf, arxiv
This template is resilient if authors is a string or list.
{% endcomment %}

{% assign pubs = site.data.publications | default: empty %}

{% if pubs and pubs.size > 0 %}

  {%- comment -%}
    Normalize to a descending, year-grouped presentation.
    We sort by year (string) and reverse; then uniq the year list.
  {%- endcomment -%}
  {% assign pubs_sorted = pubs | sort: "year" | reverse %}
  {% assign years = pubs_sorted | map: "year" | uniq %}

  {% for y in years %}
  ## {{ y }}

  <div class="grid">
    {% for p in pubs_sorted %}
      {% if p.year == y %}
      <article class="card">
