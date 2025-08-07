---
layout: default
title: Articles Sheng
---
# Articles dans la catégorie Sheng

{% for post in site.categories.sheng %}
  <article>
    <a href="{{ post.url | relative_url }}">
      <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" class="thumbnail">
      <h2>{{ post.title }}</h2>
      <p>{{ post.subtitle }}</p>
      <p class="date">{{ post.date | date: "%d %B %Y" }}</p>
    </a>
  </article>
{% endfor %}