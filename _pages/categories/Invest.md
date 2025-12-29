---
title: "Invest"
permalink: /categories/Invest/
layout: single
author_profile: true
sidebar:
  nav: "sidebar-category"
---

{% assign posts = site.posts
  | where_exp: "post", "post.categories contains 'Invest'"
  | sort: "date"
  | reverse
%}

{% for post in posts %}
  {% include archive-single.html type="list" %}
{% endfor %}