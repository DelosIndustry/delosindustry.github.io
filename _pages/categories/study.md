---
title: "공부"
permalink: /categories/공부/
layout: single
author_profile: true
sidebar:
  nav: "sidebar-category"
---

{% assign posts = site.posts
  | where_exp: "post", "post.categories contains '공부'"
  | sort: "date"
  | reverse
%}

{% for post in posts %}
  {% include archive-single.html type="list" %}
{% endfor %}

