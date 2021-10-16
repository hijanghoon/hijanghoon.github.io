---
layout: page
title: Archive
---

<!-- Search posts -->
{% for post in site.posts %}
  * {{ post.date | date_to_string }} »
  <span style="font-size:18px;"><a href="{{ post.url }}">{{ post.title }}</a></span>
{% endfor %}