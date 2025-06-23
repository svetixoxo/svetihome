---
layout: default
permalink: /infrastruktur/
title: "/sys/infrastruktur"
---

{% assign infrastruktur_posts = "" | split: "" %}
{% for post in site.posts %}
  {% if post.categories contains "infrastruktur" %}
    {% assign infrastruktur_posts = infrastruktur_posts | push: post %}
  {% endif %}
{% endfor %}

{% if infrastruktur_posts.size > 0 %}
  <ul>
  {% for post in infrastruktur_posts %}
    <li>
      {{ post.date | date: "%d.%m.%Y" }}: <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
  </ul>
{% else %}
  <p>Keine Infrastruktur-Artikel gefunden.</p>
{% endif %}
