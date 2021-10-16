---
layout: page
title: Archive
---

<!-- Search posts -->
{% for post in site.posts %}
  {{ post.date | date_to_string }}
  <span style="font-size:18px;"><a href="{{ site.baseurl }}/{{ post.url }}">{{ post.title }}</a></span>
{% endfor %}