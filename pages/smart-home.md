---
layout: default
permalink: /smart-home/
title: '~/smart-home'
---

{% assign smart-home_posts = "" | split: "" %}
{% for post in site.posts %}
  {% if post.categories contains "smart-home" %}
    {% assign smart-home_posts = smart-home_posts | push: post %}
  {% endif %}
{% endfor %}

{% if smart-home_posts.size > 0 %}
  <ul>
  {% for post in smart-home_posts %}
    <li>
      {{ post.date | date: "%d.%m.%Y" }}: <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
  </ul>
{% else %}
  <p>Keine Smart-Home-Artikel gefunden.</p>
{% endif %}
