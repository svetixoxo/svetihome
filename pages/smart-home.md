---
layout: default
permalink: /smart-home/
title: '~/smart-home'
---

<h1>Smart Home Debug</h1>

<!-- Alle Posts mit ihren exakten Kategorien anzeigen -->
<h2>Debug: Alle Posts und Kategorien</h2>
<ul>
{% for post in site.posts %}
  <li>
    <strong>{{ post.title }}</strong><br>
    Kategorien (Array): {{ post.categories | inspect }}<br>
    Kategorien (String): "{{ post.categories | join: '", "' }}"<br>
    Datum: {{ post.date | date: "%Y-%m-%d" }}<br>
    ---
  </li>
{% endfor %}
</ul>

<!-- Prüfung verschiedener Varianten -->
<h2>Kategorie-Tests</h2>
{% assign test1 = site.posts | where_exp: "post", "post.categories contains 'smarthome'" %}
{% assign test2 = site.posts | where_exp: "post", "post.categories contains 'smart-home'" %}
{% assign test3 = site.posts | where_exp: "post", "post.categories contains 'Smart Home'" %}

<p>Posts mit Kategorie 'smarthome': {{ test1.size }}</p>
<p>Posts mit Kategorie 'smart-home': {{ test2.size }}</p>
<p>Posts mit Kategorie 'Smart Home': {{ test3.size }}</p>

<!-- Original Logik -->
<h2>Smart Home Posts</h2>
{% assign smarthome_posts = "" | split: "" %}
{% for post in site.posts %}
  {% if post.categories contains "smarthome" %}
    {% assign smarthome_posts = smarthome_posts | push: post %}
  {% endif %}
{% endfor %}

<p>Gefundene Smart Home Posts: {{ smarthome_posts.size }}</p>

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
