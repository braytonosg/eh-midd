---
layout: page
title: People
permalink: /people/
---

[Kate Crawford, PhD](../about/)

## Current students

<div class="people-list">
  {% for person in site.data.people.current %}
    {% include person-card.html person=person %}
  {% endfor %}
</div>

## Lab alumni

<ul class="alumni-list">
  {% for person in site.data.people.alumni %}
    <li>
      {{ person.name }}{% if person.detail %} — {{ person.detail }}{% endif %}
    </li>
  {% endfor %}
</ul>
