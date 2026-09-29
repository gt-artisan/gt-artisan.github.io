---
layout: default
title: "ARTISAN — Georgia Tech"
---

<div class="hero">
  <div class="hero-inner">
    <div class="hero-copy">
      <span class="hero-eyebrow">Science · AI · Cyberinfrastructure</span>
      <h1 class="hero-heading">
        <span class="hero-tagline">An Integrated Ecosystem for <span class="hero-highlight">AI-Driven Innovation</span></span>
      </h1>
      <p class="hero-description">
        The Center for <span class="artisan-expansion"><strong>ART</strong>ificial
        <strong>I</strong>ntelligence in <strong>S</strong>cience <strong>A</strong>nd
        E<strong>n</strong>gineering</span> is a joint center of the College of Computing and the
        Institute for Data Engineering and Science at Georgia Tech, building AI-enabled
        cyberinfrastructure, intelligent platforms, and open systems that accelerate discovery across
        science and engineering.
      </p>
      <a class="hero-cta" href="#capabilities">Explore our capabilities <span aria-hidden="true">→</span></a>
    </div>
    <div class="hero-visual" role="img" aria-label="Science, artificial intelligence, and cyberinfrastructure intersect at ARTISAN">
      <div class="venn-circle venn-science">
        <span>Science<small>Discovery</small></span>
      </div>
      <div class="venn-circle venn-ai">
        <span>AI<small>Intelligence</small></span>
      </div>
      <div class="venn-circle venn-cyber">
        <span>Cyberinfrastructure<small>Open systems</small></span>
      </div>
      <div class="venn-center">
        <strong>ARTISAN</strong>
        <span>Science · AI<br/>Cyberinfrastructure</span>
      </div>
    </div>
  </div>
</div>

<section class="capability-overview" id="capabilities">
  <div class="capability-overview-inner">
    <div class="capability-overview-heading">
      <span></span>
      <h2>Capabilities at the Intersection</h2>
      <a class="capability-overview-link" href="/research/">Explore <span aria-hidden="true">→</span></a>
    </div>
    <div class="hero-pillars">
      <a class="hero-pillar" href="/research/#advanced-computing" aria-label="Learn more about Advanced Computing">
        <h2>Advanced Computing</h2>
        <p>Next-generation systems enabling local-to-HPC scaling.</p>
      </a>
      <a class="hero-pillar" href="/research/#multidisciplinary-expertise" aria-label="Learn more about Multidisciplinary Expertise">
        <h2>Multidisciplinary Expertise</h2>
        <p>Bringing AI researchers, systems experts, and domain scientists together to solve complex scientific and engineering challenges.</p>
      </a>
      <a class="hero-pillar" href="/research/#ai-data-services" aria-label="Learn more about AI Data and Services">
        <h2>AI Data &amp; Services</h2>
        <p>Connecting scientific data, AI capabilities, and research services to enable reproducible, AI-driven discovery.</p>
      </a>
    </div>
  </div>
</section>

<section class="section home-people-section">
  <div class="home-people-heading">
    <div>
      <span class="section-heading-line"></span>
      <h2>Our People</h2>
    </div>
    <p>A diverse and interdisciplinary group of faculty, researchers, and collaborators advancing the frontiers of science, AI, and cyberinfrastructure.</p>
    <a class="home-people-link" href="/people/">Explore <span aria-hidden="true">→</span></a>
  </div>
  <div class="home-people-grid">
    {% assign ordered_people = site.data.people | sort: "display_order" %}
    {% for person in ordered_people %}
      {% if person.featured_home %}
      <article class="home-person-card">
        {% comment %}
        <div class="home-person-portrait">
          {% if person.photo_available %}
            <img src="{{ person.photo | relative_url }}" alt="Portrait of {{ person.name }}" loading="lazy" />
          {% else %}
            <span aria-hidden="true">{{ person.initials }}</span>
          {% endif %}
        </div>
        {% endcomment %}
        <div class="home-person-copy">
          <h3>{{ person.name }}</h3>
          <p class="home-person-position">{{ person.title }}</p>
          <p class="home-person-research"><strong>Research areas</strong>{{ person.home_detail }}</p>
          <div class="home-person-keywords" aria-label="Research areas">
            {% for keyword in person.science_keywords %}<span>{{ keyword }}</span>{% endfor %}
          </div>
        </div>
      </article>
      {% endif %}
    {% endfor %}
  </div>
</section>

<section class="section science-section">
  <div class="science-section-heading">
    <div>
      <span class="science-heading-line"></span>
      <h2>Science with ARTISAN</h2>
    </div>
    <p>Working with researchers across scientific domains—and welcoming new collaborations where AI and advanced computing can accelerate discovery.</p>
    <a class="science-explore-link" href="/projects/">Explore <span aria-hidden="true">→</span></a>
  </div>
  <div class="science-domain-grid">
    <article class="science-domain science-domain-life">
      <img src="{{ '/assets/images/science/biology-health.png' | relative_url }}" alt="" loading="lazy" />
      <div class="science-domain-label">
        <span>Life Sciences</span>
        <h3>Biology &amp; Health</h3>
      </div>
    </article>
    <article class="science-domain science-domain-climate">
      <img src="{{ '/assets/images/science/climate-environment.png' | relative_url }}" alt="" loading="lazy" />
      <div class="science-domain-label">
        <span>Earth Systems</span>
        <h3>Climate &amp; Environment</h3>
      </div>
    </article>
    <article class="science-domain science-domain-materials">
      <img src="{{ '/assets/images/science/materials-science.png' | relative_url }}" alt="" loading="lazy" />
      <div class="science-domain-label">
        <span>Molecular Discovery</span>
        <h3>Materials Science</h3>
      </div>
    </article>
    <article class="science-domain science-domain-neuro">
      <img src="{{ '/assets/images/science/neuroscience.png' | relative_url }}" alt="" loading="lazy" />
      <div class="science-domain-label">
        <span>Brain &amp; Behavior</span>
        <h3>Neuroscience</h3>
      </div>
    </article>
    <article class="science-domain science-domain-quantum">
      <img src="{{ '/assets/images/science/quantum-chemistry.png' | relative_url }}" alt="" loading="lazy" />
      <div class="science-domain-label">
        <span>Atoms &amp; Molecules</span>
        <h3>Quantum Science &amp; Chemistry</h3>
      </div>
    </article>
    <article class="science-domain science-domain-engineering">
      <img src="{{ '/assets/images/science/engineering-sciences.png' | relative_url }}" alt="" loading="lazy" />
      <div class="science-domain-label">
        <span>Physical Systems</span>
        <h3>Engineering Sciences</h3>
      </div>
    </article>
  </div>
</section>

<section class="section platform-section">
  <div class="platform-section-heading">
    <h2>Platforms &amp; Initiatives</h2>
    <p class="platform-tagline">Building the computing environments, research platforms, and integrated capabilities needed for AI-driven scientific discovery.</p>
  </div>
  <div class="platform-grid">
    <div class="platform-card platform-card-linked">
      <h3>Nexus</h3>
      <p class="platform-card-lead">AI supercomputing built around the way researchers work.</p>
      <p>Nexus combines next-generation AI supercomputing with researcher-focused tools and platforms that make advanced computing easier to use. Researchers can move from interactive development to large-scale AI and computational workloads within an integrated environment designed for open scientific research.</p>
      <a class="platform-link" href="https://portal.nexus.gatech.edu/" target="_blank" rel="noopener noreferrer">Explore <span aria-hidden="true">→</span></a>
    </div>
    <div class="platform-card platform-card-linked">
      <h3>CyberShuttle</h3>
      <p class="platform-card-lead">Connecting the environments where science happens.</p>
      <p>CyberShuttle connects researchers, scientific applications, data, workflows, and advanced computing resources into accessible research environments. It enables scientists to work with familiar tools while moving their research across local, cloud, and high-performance computing environments as their needs evolve.</p>
      <a class="platform-link" href="https://cybershuttle.org/" target="_blank" rel="noopener noreferrer">Explore <span aria-hidden="true">→</span></a>
    </div>
    <div class="platform-card">
      <h3>AI4Science Foundry</h3>
      <p class="platform-card-lead">An end-to-end platform for AI-driven scientific discovery.</p>
      <p>Building on Nexus and CyberShuttle, the AI4Science Foundry brings together advanced computing, scientific data, AI development environments, models, workflows, and research services into an integrated platform for science.</p>
      <p>The Foundry is designed to support the full AI-for-science lifecycle from exploring scientific data and developing models to training at scale, evaluating results, and deploying AI capabilities into scientific workflows and applications.</p>
    </div>
    <div class="platform-card">
      <h3>Nexus AASC</h3>
      <p class="platform-card-lead">From Prototypes to Scalable Science</p>
      <p>The Nexus AI4Science Collaboration pairs research teams with AI, HPC, and research engineering experts to transform promising AI4Science prototypes into scalable, reusable, and reproducible capabilities on Nexus.</p>
    </div>
  </div>
</section>

<section class="section partnership-section">
  <div class="partnership-section-heading">
    <div>
      <span class="section-heading-line"></span>
      <h2>Support &amp; Partnerships</h2>
    </div>
    <p class="partnership-tagline">Advancing research across academia, government, and industry.</p>
    <a class="partnership-explore-link" href="/partners/">Explore <span aria-hidden="true">→</span></a>
  </div>
  <div class="partnership-grid">
    <article class="partnership-card">
      <h3>Funding &amp; Support</h3>
      <div class="partner-logo-grid" aria-label="Funding and support organizations">
        <a class="partner-logo partner-logo-nsf" href="https://www.nsf.gov/" target="_blank" rel="noopener noreferrer" aria-label="U.S. National Science Foundation">
          <img src="/assets/images/partners/nsf.png" alt="U.S. National Science Foundation logo">
        </a>
        <a class="partner-logo partner-logo-wide" href="https://www.nih.gov/" target="_blank" rel="noopener noreferrer" aria-label="National Institutes of Health">
          <img src="/assets/images/partners/nih.png?v=20260928-2" alt="National Institutes of Health logo">
        </a>
        <a class="partner-logo partner-logo-dark" href="https://www.darpa.mil/" target="_blank" rel="noopener noreferrer" aria-label="DARPA">
          <img src="/assets/images/partners/darpa.svg" alt="DARPA logo">
        </a>
      </div>
    </article>
    <article class="partnership-card">
      <h3>Industry Partners</h3>
      <div class="partner-logo-grid" aria-label="Industry partner organizations">
        <a class="partner-logo partner-logo-wide" href="https://www.google.com/" target="_blank" rel="noopener noreferrer" aria-label="Google">
          <img src="/assets/images/partners/google.png" alt="Google logo">
        </a>
        <a class="partner-logo partner-logo-wide partner-logo-nvidia" href="https://www.nvidia.com/" target="_blank" rel="noopener noreferrer" aria-label="NVIDIA">
          <img src="/assets/images/partners/nvidia.svg" alt="NVIDIA logo">
        </a>
      </div>
    </article>
    <article class="partnership-card">
      <h3>Research Collaborators</h3>
      <div class="partner-logo-grid" aria-label="Research collaborator organizations">
        <a class="partner-logo partner-logo-wide" href="https://illinois.edu/" target="_blank" rel="noopener noreferrer" aria-label="University of Illinois Urbana-Champaign">
          <img src="/assets/images/partners/uiuc.svg" alt="University of Illinois Urbana-Champaign logo">
        </a>
        <a class="partner-logo partner-logo-wide" href="https://ucsd.edu/" target="_blank" rel="noopener noreferrer" aria-label="UC San Diego">
          <img src="/assets/images/partners/ucsd.svg" alt="UC San Diego logo">
        </a>
        <a class="partner-logo partner-logo-wide partner-logo-dark" href="https://alleninstitute.org/" target="_blank" rel="noopener noreferrer" aria-label="Allen Institute">
          <img src="/assets/images/partners/allen-institute.svg" alt="Allen Institute logo">
        </a>
      </div>
    </article>
  </div>
</section>
