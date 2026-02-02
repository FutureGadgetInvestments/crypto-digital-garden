---
layout: page
title: All Notes
permalink: /notes/
---

Browse all notes in this garden.

## By Status

### Evergreen
{% assign evergreen = site.notes | where: "status", "evergreen" | sort: "title" %}
{% if evergreen.size > 0 %}
<ul>
{% for note in evergreen %}
  <li><a href="{{ note.url | relative_url }}">{{ note.title }}</a></li>
{% endfor %}
</ul>
{% else %}
*No evergreen notes yet.*
{% endif %}

### Budding
{% assign budding = site.notes | where: "status", "budding" | sort: "title" %}
{% if budding.size > 0 %}
<ul>
{% for note in budding %}
  <li><a href="{{ note.url | relative_url }}">{{ note.title }}</a></li>
{% endfor %}
</ul>
{% else %}
*No budding notes yet.*
{% endif %}

### Seedling
{% assign seedling = site.notes | where: "status", "seedling" | sort: "title" %}
{% if seedling.size > 0 %}
<ul>
{% for note in seedling %}
  <li><a href="{{ note.url | relative_url }}">{{ note.title }}</a></li>
{% endfor %}
</ul>
{% else %}
*No seedling notes yet.*
{% endif %}

---

## All Notes (A-Z)

{% assign all_notes = site.notes | sort: "title" %}
<ul class="note-list">
{% for note in all_notes %}
  <li>
    <a href="{{ note.url | relative_url }}">{{ note.title }}</a>
    {% if note.status %}
    <span class="status-badge status-{{ note.status }}">{{ note.status }}</span>
    {% endif %}
  </li>
{% endfor %}
</ul>
