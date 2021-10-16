---
layout: page
title: Archive
---

<!-- Search posts -->

{% for post in site.posts %}
  {{ post.date | date_to_string }}
  <span style="font-size:20px;"> [ {{ post.title }} ]({{ site.baseurl }}/{{ post.url }})</span>
{% endfor %}