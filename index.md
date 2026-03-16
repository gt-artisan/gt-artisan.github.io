---
layout: default
title: "ARTISAN — Georgia Tech"
---

<link rel="stylesheet" href="/assets/css/home.css">

<div class="hero">

# Center for Artificial Intelligence in Science & Engineering

<p>
ARTISAN is a joint center of the College of Computing and the Institute for Data Engineering and Science at Georgia Tech. We build AI-enabled cyberinfrastructure, intelligent platforms, and open systems that accelerate discovery across science and engineering.
</p>

<div class="hero-actions">

[Explore Research](/research){: .btn }

[View Projects](/projects){: .btn .ghost }

</div>

</div>


<div class="section">

## What We Do

ARTISAN brings together researchers, engineers, and domain scientists to develop the infrastructure and methods needed for AI-driven discovery.

</div>


<div class="section">

## Research Areas

<div class="research-grid">

<div class="research-card">

### Cyberinfrastructure & Distributed Systems
Scalable systems supporting scientific workflows and advanced computing.

</div>

<div class="research-card">

### AI for Science & Engineering
AI and machine learning methods tailored for scientific discovery.

</div>

<div class="research-card">

### Interpretable AI
Methods that help researchers understand and trust AI-generated insights.

</div>

</div>

</div>


<div class="section">

## Platforms & Initiatives

<div class="platform-grid">

<div class="platform-card">

### Nexus
A next-generation AI supercomputing initiative for science.

</div>

<div class="platform-card">

### CyberShuttle
Connects researchers' workflows to powerful computing resources.

</div>

<div class="platform-card">

### SciGaP
Science gateway platform supporting research communities.

</div>

<div class="platform-card">

### Apache Custos
Secure identity and access management for science gateways.

</div>

</div>

</div>

<!--
<section class="bg-navy section">
  <div class="container">
    <h1 class="gt-gold" style="margin-bottom:.25rem;">Center for Artificial Intelligence in Science & Engineering</h1>
    <p style="max-width:65ch;color:#E6EDF5;">
      A joint Center between the College of Computing and the Institute for Data Engineering and Science
      dedicated to accelerating science & engineering with AI, cyberinfrastructure, and open platforms.
    </p>
    <a href="{{ '/research' | relative_url }}" class="btn btn--gold">Explore Research</a>
    <a href="{{ '/projects' | relative_url }}" class="btn" style="margin-left:.5rem;">View Projects</a>
  </div>
</section>

{% assign news_list = site.news | default: empty %}
{% if news_list and news_list.size > 0 %}
  {% assign latest_news = news_list | sort: "date" | reverse | slice: 0, 3 %}
  <div class="grid">
  {% for post in latest_news %}
    <article class="card">
      <h3 class="text-navy"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p style="margin:.25rem 0 .5rem 0; color:#666;">{{ post.date | date: "%b %d, %Y" }}</p>
      <p>{{ post.excerpt }}</p>
    </article>
  {% endfor %}
  </div>
{% else %}
  <p>No news yet. Check back soon.</p>
{% endif %}

<section class="section section--alt">
  <div class="container">
    <h2 class="text-navy">Research Areas</h2>
    <div class="grid">
      <div class="card">
        <h3 class="text-navy"><a href="{{ '/research#ci' | relative_url }}">Cyberinfrastructure & Distributed Systems</a></h3>
        <p>Scalable, high-performance systems powering AI and scientific research.</p>
      </div>
      <div class="card">
        <h3 class="text-navy"><a href="{{ '/research#ai-se' | relative_url }}">AI-Driven Solutions for S&E</a></h3>
        <p>Domain-tailored AI/ML for protein modeling, quantum chemistry, climate, neuroscience.</p>
      </div>
      <div class="card">
        <h3 class="text-navy"><a href="{{ '/research#interpretable' | relative_url }}">Interpretable AI for Discovery</a></h3>
        <p>Accurate predictions with insight to advance scientific theories and knowledge.</p>
      </div>
    </div>
  </div>
</section> -->
