---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: "Environmental Health at Middlebury"
---

<div class="hero">
  <img src="{{ '/assets/img/bg/dots.png' | relative_url }}" alt="Describe the photo here">
</div>

<div class="home">
  <div class="home-intro">
    <!-- <h1 class="page-heading">{{ page.title }}</h1> -->
    <img src="{{ '/assets/img/eham.png' | relative_url}}">
    <p>
      Environmental health is a subdiscipline of public health that focuses on the reciprocal relationships between human activity, environmental quality, and the health of people and ecosystems. Environmental health is highly interdisciplinary and draws upon numerous public health, natural science, and social science disciplines including epidemiology, exposure science, toxicology, risk assessment, chemistry, biology, geology, sociology, psychology, and more. Middlebury offers many opportunities to learn about and engage directly with the field of environmental health. 
    </p>
  </div>
  
  <div class="home-columns">
  {% assign current = site.data.teaching | where: "current", true %}
  {% if current.size > 0 %}
  <section class="home-columns__col">
    {% include course-list.html heading="Teaching this year" items=current %}
    <p><a href="{{ '/teaching/' | relative_url }}">All teaching →</a></p>
  </section>
  {% endif %}

  <section class="home-columns__col">
    <h2>Current Research</h2>
    <div class="project-grid">
    {% for project in site.data.projects limit: 3 %}
      <div class="project-card project-card--compact">
        {% if project.images %}
          <img class="project-card__thumb" src="{{ project.images.first | relative_url }}" alt="">
        {% endif %}
        <h4 class="project-card__title">
          {% if project.link %}<a href="{{ project.link }}">{{ project.title }}</a>{% else %}{{ project.title }}{% endif %}
        </h4>
      </div>
    {% endfor %}
    </div>
    <p><a href="{{ '/projects/' | relative_url }}">All research →</a></p>
  </section>
  <section class="home-columns__col">
  <h2>Get involved</h2>
</section>
</div>


