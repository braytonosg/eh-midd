---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

<div class="home">
  <h1 class="page-heading">{{ page.title }}</h1>

  <div class="project-grid">
    {% for item in site.data.home %}
      {% include project-card.html project=item %}
    {% endfor %}
  </div>
</div>
