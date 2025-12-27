---
title: "논문리뷰 / NLP"
permalink: /categories/논문리뷰/NLP/
layout: single
author_profile: true
sidebar:
  nav: "sidebar-category"
---

{% assign posts = site.posts
  | where_exp: "post", "post.categories contains '논문리뷰'"
  | where_exp: "post", "post.tags contains 'NLP'"
  | sort: "date"
  | reverse
%}

{% for post in posts %}
  {% include archive-single.html type="list" %}
{% endfor %}
