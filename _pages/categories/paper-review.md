---
title: "논문리뷰"
permalink: /categories/논문리뷰/
layout: single
author_profile: true
sidebar:
  nav: "sidebar-category"
---

{% assign posts = site.categories['논문리뷰'] | sort: "date" | reverse %}
{% for post in posts %}
  {% include archive-single.html type="list" %}
{% endfor %}