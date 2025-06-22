---
layout: default
permalink: /speicher-backup/
title: "/mnt/cloud"
---

{% assign nextcloud_posts = site.posts | where_exp: "post", "post.categories contains 'speicher' and post.tags contains 'nextcloud'" %}

{% if nextcloud_posts.size > 0 %}
  <ul>
  {% for post in nextcloud_posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <small> - {{ post.date | date: "%d.%m.%Y" }}</small>
    </li>
  {% endfor %}
  </ul>
{% else %}
  <p>Keine Nextcloud-Artikel gefunden.</p>
{% endif %}

---

{% assign speicher_posts = site.posts | where_exp: "post", "post.categories contains 'speicher'" %}

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
