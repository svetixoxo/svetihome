---
layout: default
permalink: /speicher-backup/
title: "mnt/cloud"
---

{{ nextcloud_posts.size }} Posts gefunden

{% comment %}
Nextcloud Posts filtern
{% endcomment %}
{% assign nextcloud_posts = site.posts | where: "categories", "speicher" %}
