---
layout: default
permalink: /smart-home/
title: '~/smart-home'
---

{% assign smarthome_posts = "" | split: "" %}
{% for post in site.posts %}
  {% if post.categories contains "smart-home" %}
    {% assign smarthome_posts = smarthome_posts | push: post %}
  {% endif %}
{% endfor %}

{% if smarthome_posts.size > 0 %}
  <ul>
  {% for post in smarthome_posts %}
    <li>
      {{ post.date | date: "%d.%m.%Y" }}: <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
  </ul>
{% else %}
  <p>Keine Smart-Home-Artikel gefunden.</p>
{% endif %}
