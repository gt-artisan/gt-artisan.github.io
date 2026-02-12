---
title: "Publications — ARTISAN"
---

# Publications

<p><strong>Debug:</strong> site.data.publications type:
{% if site.data.publications %}
  {% if site.data.publications.first %}
    list (size={{ site.data.publications | size }})
  {% else %}
    map (keys={{ site.data.publications | keys | join: ", " }})
  {% endif %}
{% else %}
  (nil / not loaded)
{% endif %}
</p>

{% comment %}
If it's a map with a key like "entries", we need to loop site.data.publications.entries instead of site.data.publications
{% endcomment %}

{% comment %}
Make the page resilient:
- If _data/publications.yml is missing or empty, show a friendly message.
- Normalize year to string when grouping/sorting to avoid mixed-type issues.
- Handle optional fields: venue, doi, url, pdf, arxiv.
{% endcomment %}

{% assign pubs = site.data.publications | default: empty %}

{% if pubs and pubs.size > 0 %}

  {%- comment -%} Normalize: ensure every item has a string "year_str" {%- endcomment -%}
  {% assign pubs_norm = "" | split: "" %}
  {% for p in pubs %}
    {% assign y = p.year %}
    {% if y %}
      {% assign y_str = y | append: "" %}
    {% else %}
      {% assign y_str = "Unknown" %}
    {% endif %}

    {%- comment -%} Clone object w/ computed year_str (Liquid doesn’t deep-clone; we rebuild a new hash-like drop) {%- endcomment -%}
    {% assign title   = p.title   %}
    {% assign authors = p.authors %}
    {% assign venue   = p.venue   %}
    {% assign doi     = p.doi     %}
    {% assign url     = p.url     %}
    {% assign pdf     = p.pdf     %}
    {% assign arxiv   = p.arxiv   %}
    {% assign type    = p.type    %}
    {% assign id      = p.id      %}

    {% capture one %}
      {
        "id": "{{ id | escape }}",
        "type": "{{ type | escape }}",
        "title": "{{ title | escape }}",
        "year": "{{ y_str | escape }}",
        "venue": "{{ venue | escape }}",
        "doi": "{{ doi | escape }}",
        "url": "{{ url | escape }}",
        "pdf": "{{ pdf | escape }}",
        "arxiv": "{{ arxiv | escape }}",
        "authors": [{% if authors %}{% for a in authors %}"{{ a | escape }}"{% unless forloop.last %}, {% endunless %}{% endfor %}{% endif %}]
      }
    {% endcapture %}
    {% assign pubs_norm = pubs_norm | push: one | uniq %}
  {% endfor %}

  {%- comment -%} Parse back to objects (Liquid trick using split is sufficient to preserve the strings we need) {%- endcomment -%}
  {% assign pubs_sorted = pubs_norm | sort: "year" | reverse %}

  {%- comment -%} Build a year list (descending) {%- endcomment -%}
  {% assign years = pubs_sorted | map: "year" | uniq %}

  {% for y in years %}
  ## {{ y }}
  <ul>
    {% for raw in pubs_sorted %}
      {% assign p = raw %}
      {% if p.year == y %}
        <li style="margin-bottom:.5rem;">
          <strong>{{ p.title }}</strong>
          {% if p.authors and p.authors.size > 0 %}
            <br/><em>{{ p.authors | join: ", " }}</em>
          {% endif %}
          {% if p.venue %} — {{ p.venue }}{% endif %}
          {% if p.doi %} · DOI: {{ p.doi }}</a>{% endif %}
          {% if p.arxiv %} · arXiv: {{ p.arxiv }}</a>{% endif %}
          {% if p.url %} · {{ p.url }}</a>{% endif %}
          {% if p.pdf %} · {{ p.pdf }}</a>{% endif %}
        </li>
      {% endif %}
    {% endfor %}
  </ul>
  {% endfor %}

{% else %}
  <p>No publications listed yet. Add items to <code>_data/publications.bib</code>; the Action will generate <code>_data/publications.yml</code> automatically.</p>
{% endif %}