---
layout: page
title: "Gyűjtemény"
icon: fas fa-leaf
order: 2
---

# Gyűjtemény

Az alábbi listában találod a jelenlegi fák adatlapjait.  
Kattints bármelyik névre a részletes történethez, mérésekhez és munkanaplóhoz.

{% assign trees = site.pages | where: "layout", "tree" | sort: "title" %}

{% if trees.size > 0 %}
<ul>
  {% for tree in trees %}
  <li>
    <a href="{{ tree.url | relative_url }}">{{ tree.title }}</a>
    {% if tree.species %}
      — <em>{{ tree.species.latin }}</em>
      {% if tree.species.cultivar %} '{{ tree.species.cultivar }}'{% endif %}
    {% endif %}
    {% if tree.code %} • <code>{{ tree.code }}</code>{% endif %}
  </li>
  {% endfor %}
</ul>
{% else %}
<p>Még nincs fa a gyűjteményben – kezd az első adatlap létrehozásával! 🌱</p>
{% endif %}
