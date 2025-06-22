---
layout: default
permalink: /speicher-backup/
title: 'mnt/cloud'
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
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      {% if post.tags.size > 0 %}
        <span class="tags">
        {% for tag in post.tags %}
          <span class="tag">{{ tag }}</span>
        {% endfor %}
        </span>
      {% endif %}
      <small> - {{ post.date | date: "%d.%m.%Y" }}</small>
    </li>
  {% endfor %}
  </ul>
{% else %}
  <p>Keine Speicher-Artikel gefunden.</p>
{% endif %}
