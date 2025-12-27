---
title: "논문리뷰 / 3D Vision"
permalink: /categories/논문리뷰/3DV/
layout: single
author_profile: true
sidebar:
  nav: "sidebar-category"
---

{% assign posts = site.posts
  | where_exp: "post", "post.categories contains '논문리뷰'"
  | where_exp: "post", "post.tags contains '3D Vision'"
  | sort: "date"
  | reverse
%}

{% for post in posts %}
  {% include archive-single.html type="list" %}
{% endfor %}
