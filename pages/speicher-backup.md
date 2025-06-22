---
layout: default
permalink: /speicher-backup/
title: 'mnt/cloud'
---

<p>Debug: Anzahl aller Posts: {{ site.posts.size }}</p>

{% for post in site.posts %}
  <p>Debug: Post "{{ post.title }}" - Kategorien: {{ post.categories | join: ", " }}</p>
{% endfor %}

{% assign speicher_posts = "" | split: "" %}
{% for post in site.posts %}
  {% if post.categories contains "speicher" %}
    {% assign speicher_posts = speicher_posts | push: post %}
  {% endif %}
{% endfor %}

<p>Debug: Gefundene Speicher-Posts: {{ speicher_posts.size }}</p>

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
