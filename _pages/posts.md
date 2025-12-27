---
title: "전체 게시글"
permalink: /posts/
layout: single
author_profile: true
sidebar:
  nav: "sidebar-category"
---

{% assign posts = site.posts | sort: "date" | reverse %}
{% for post in posts %}
  {% include archive-single.html type="list" %}
{% endfor %}