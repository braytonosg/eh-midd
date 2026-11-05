---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: "Environmental Health at Middlebury"
---

<div class="hero">
  <img src="{{ '/assets/img/bg/snow.jpeg' | relative_url }}" alt="Describe the photo here">
</div>

<div class="home">
  <h1 class="page-heading">{{ page.title }}</h1>

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



<!-- 
  {% assign current = site.data.teaching | where: "current", true %}
  {% if current.size > 0 %}
    <h2>Teaching this year</h2>
    <ul>
      {% for course in current %}
        <li>{{ course.code }}: {{ course.title }} ({{ course.term }})</li>
      {% endfor %}
    </ul>
    <p><a href="{{ '/teaching/' | relative_url }}">All courses →</a></p>
  {% endif %} -->

<!--   {% assign current = site.data.projects | where: "current", true %}
  {% if current.size > 0 %}
    <h2>Current research</h2>
    <ul>
      {% for project in current %}
        <li>{{ project.title }} ({{ project.description }})</li>
      {% endfor %}
    </ul>
    <p><a href="{{ '/teaching/' | relative_url }}">All research →</a></p>
  {% endif %}
 -->
<!--   <h2>Current research</h2>
  <div class="project-grid">
    {% for project in site.data.projects limit: 3 %}
      <div class="project-card project-card--top">
        <h4 class="project-card__title">
          {% if project.link %}<a href="{{ project.link }}">{{ project.title }}</a>{% else %}{{ project.title }}{% endif %}
        </h4>
        <div class="project-card__body">
          <p>{{ project.description | strip | truncate: 100 }}</p>
        </div>
      </div>
    {% endfor %} -->
  <!-- <p><a href="{{ '/projects/' | relative_url }}">All projects →</a></p> -->

<!--   <div class="project-grid">
    {% for item in site.data.home %}
      {% include project-card.html project=item %}
    {% endfor %}
  </div> -->
</div>

<script>
  (function () {
    var hero = document.querySelector('.hero');
    var header = document.querySelector('.site-header');
    if (!header) return;
    // Older browsers: just keep the header solid
    if (!hero || !('IntersectionObserver' in window)) {
      header.classList.add('is-solid');
      return;
    }
    // Fires when the hero has scrolled completely behind the header
    new IntersectionObserver(function (entries) {
      header.classList.toggle('is-solid', !entries[0].isIntersecting);
    }, { rootMargin: '-' + header.offsetHeight + 'px 0px 0px 0px' }).observe(hero);
  })();
</script>