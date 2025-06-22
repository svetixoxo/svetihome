---
layout: default
permalink: /speicher-backup/
title: "/mnt/cloud"
---

{% assign nextcloud_posts = site.posts | where_exp: "post", "post.categories contains 'speicher' and post.tags contains 'nextcloud'" %}
