---
layout: default
title: "Publications — ARTISAN"
permalink: /publications/
---

# Publications

{% assign pubs = site.data.publications | default: empty %}
{% if pubs and pubs.size > 0 %}
  {% assign pubs_sorted = pubs | sort: "year" | reverse %}
  {% assign years = pubs_sorted | map: "year" | uniq %}

<div class="pub-filter">
<label for="yearFilter" class="text-navy" style="font-weight:600;">Filter by year:</label>
<select id="yearFilter" onchange="filterYear()"><option value="all">All years</option>{% for y in years %}<option value="{{ y }}">{{ y }}</option>{% endfor %}</select>
</div>

<script>
function filterYear() {
  var sel = document.getElementById('yearFilter').value;
  document.querySelectorAll('.pub-year').forEach(function(h2) {
    var sectionGrid = h2.nextElementSibling;
    var show = (sel === 'all' || h2.textContent.trim() === sel);
    h2.style.display = show ? 'block' : 'none';
    if (sectionGrid) sectionGrid.style.display = show ? 'block' : 'none';
  });
}
</script>

  {% for y in years %}
  <h2 class="pub-year">{{ y }}</h2>

  <div class="pub-list">
    {% for p in pubs_sorted %}
      {% if p.year == y %}
      <article class="pub-card">
        <div class="pub-title-row">
          <div class="pub-title">{{ p.title }}</div>
          {% if p.url %}
            <a class="pub-chevron" href="{{ p.url }}" target="_blank" aria-label="Open paper"><svg viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg></a>
          {% elsif p.doi %}
            <a class="pub-chevron" href="https://doi.org/{{ p.doi }}" target="_blank" aria-label="Open paper"><svg viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg></a>
          {% elsif p.pdf %}
            <a class="pub-chevron" href="{{ p.pdf }}" target="_blank" aria-label="Open paper"><svg viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg></a>
          {% elsif p.arxiv %}
            <a class="pub-chevron" href="https://arxiv.org/abs/{{ p.arxiv }}" target="_blank" aria-label="Open paper"><svg viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg></a>
          {% endif %}
        </div>
        {% if p.authors %}
          <div class="pub-authors">
          {% if p.authors.first %}
            {% for a in p.authors %}<span class="author-pill">{{ a }}</span>{% endfor %}
          {% else %}
            <span class="author-pill">{{ p.authors }}</span>
          {% endif %}
          </div>
        {% endif %}
        <div class="pub-meta">
          {% if p.venue %}{{ p.venue }}{% endif %}
          {% if p.year %} · {{ p.year }}{% endif %}
        </div>
      </article>
      {% endif %}
    {% endfor %}
  </div>

  {% endfor %}
{% else %}
  <p>No publications found.</p>
{% endif %}

<script type="application/ld+json">
{
  "@context":"https://schema.org",
  "@type":"ItemList",
  "itemListElement": [
    {% for p in pubs_sorted %}
    {
      "@type":"ScholarlyArticle",
      "name": {{ p.title | jsonify }},
      {% if p.authors %}
      "author": [{% if p.authors.first %}{% for a in p.authors %}{"@type":"Person","name":{{ a | jsonify }}}{% unless forloop.last %},{% endunless %}{% endfor %}{% else %}{"@type":"Person","name":{{ p.authors | jsonify }}}{% endif %}],
      {% endif %}
      {% if p.venue %}"isPartOf":{"@type":"Periodical","name":{{ p.venue | jsonify }}},{% endif %}
      {% if p.year %}"datePublished":"{{ p.year }}",{% endif %}
      {% if p.doi %}"identifier":"https://doi.org/{{ p.doi }}",{% endif %}
      {% if p.url %}"url": {{ p.url | jsonify }},{% endif %}
      {% if p.pdf %}"encoding":{"@type":"MediaObject","contentUrl": {{ p.pdf | jsonify }} }{% endif %}
    }{% unless forloop.last %},{% endunless %}
    {% endfor %}
  ]
}
</script>
