---
layout: default
title: Posts by Year
permalink: /list/
---

### Posts by year

{% assign date = nil %}
{% for post in site.posts %}
  {% assign currentdate = post.date | date: "%Y" %}
  {% if currentdate != date %}
## {{ currentdate }}
    {% assign date = currentdate %}
  {% endif %}
- [{{ post.title }}]({{ post.url | relative_url }})
{% endfor %}