---
title: "논문리뷰 / Remote Sensing"
permalink: /categories/논문리뷰/RS/
layout: single
author_profile: true
sidebar:
  nav: "sidebar-category"
---

{% assign posts = site.posts
  | where_exp: "post", "post.categories contains '논문리뷰'"
  | where_exp: "post", "post.tags contains 'Remote Sensing'"
  | sort: "date"
  | reverse
%}

{% for post in posts %}
  {% include archive-single.html type="list" %}
{% endfor %}
