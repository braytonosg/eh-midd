---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

<div class="home">
  {% if page.title %}
    <h1 class="page-heading">{{ page.title }}</h1>
  {% endif %}

  {% assign about_page = site.pages | where: "path", "about.md" | first %}
  <div class="post-content">
    {{ about_page.content | markdownify }}
  </div>
</div>
