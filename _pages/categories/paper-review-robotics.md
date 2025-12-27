---
title: "논문리뷰 / Robotics / Physical AI"
permalink: /categories/논문리뷰/Robotics/
layout: single
author_profile: true
sidebar:
  nav: "sidebar-category"
---

{% assign base = site.categories['논문리뷰'] %}
{% assign posts = base | where_exp: "post", "post.tags contains 'Robotics'" | sort: "date" | reverse %}
{% for post in posts %}
  {% include archive-single.html type="list" %}
{% endfor %}
