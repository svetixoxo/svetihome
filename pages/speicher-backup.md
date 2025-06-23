---
layout: default
permalink: /speicher-backup/
title: '/mnt/cloud'
---

{% assign speicher_posts = "" | split: "" %}
{% for post in site.posts %}
  {% if post.categories contains "speicher" %}
    {% assign speicher_posts = speicher_posts | push: post %}
  {% endif %}
{% endfor %}

{% if speicher_posts.size > 0 %}
  <ul>
  {% for post in speicher_posts %}
    <li>
      {{ post.date | date: "%d.%m.%Y" }}: <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
  </ul>
{% else %}
  <p>Keine Speicher-Artikel gefunden.</p>
{% endif %}
