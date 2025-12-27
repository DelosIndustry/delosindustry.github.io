---
title: "논문리뷰 / 3D Vision"
permalink: /categories/논문리뷰/3DV/
layout: single
author_profile: true
sidebar:
  nav: "sidebar-category"
---

{% assign base = site.categories['논문리뷰'] %}
{% assign posts = base | where_exp: "post", "post.tags contains '3D Vision'" | sort: "date" | reverse %}
{% for post in posts %}
  {% include archive-single.html type="list" %}
{% endfor %}
