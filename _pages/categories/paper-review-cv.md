---
title: "논문리뷰 / Computer Vision"
permalink: /categories/논문리뷰/CV/
layout: single
author_profile: true
sidebar:
  nav: "sidebar-category"
---

{% assign posts = site.posts
  | where_exp: "post", "post.categories contains '논문리뷰'"
  | where_exp: "post", "post.tags contains 'Computer Vision'"
  | sort: "date"
  | reverse
%}

{% for post in posts %}
  {% include archive-single.html type="list" %}
{% endfor %}
