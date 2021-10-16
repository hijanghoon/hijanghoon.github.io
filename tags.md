---
layout: page
title: Tags
description: An archive of posts sorted by tag.
---

{% capture site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}
<!-- site_tags: {{ site_tags }} -->
{% assign tag_words = site_tags | split:',' | sort %}
<!-- tag_words: {{ tag_words }} -->

<div id="tags">
  <span class="tag-box inline">
  {% for tag in tag_words %}
    <span><a href="{{ tag | cgi_escape }}">{{ tag }} : <span>{{ site.tags[tag] | size }}</span></a></span>
  {% endfor %}
  </span>

  {% for item in (0..site.tags.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ tag_words[item] | strip_newlines }}{% endcapture %}
  <h2 id="{{ this_word | cgi_escape }}">{{ this_word }}</h2>
  <span class="posts">
    {% for post in site.tags[this_word] %}{% if post.title != null %}
    <span itemscope><span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">{{ post.date | date: "%B %d, %Y" }}</time></span><a href="{{ post.url }}">
    {{ post.title }}</a></span>
    {% endif %}{% endfor %}
  </span>
  {% endunless %}{% endfor %}
</div>