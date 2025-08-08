---
layout: default
title: Articles Sheng
permalink: /sheng/
---
# Articles dans la catégorie Sheng

{% for post in site.categories.sheng %}
  <article>
    <a href="{{ post.url | relative_url }}">
      {% if post.image[0] %}
        <img src="{{ site.img_path }}{{ post.image[0] }}" alt="{{ post.title }}" class="thumbnail">
      {% else %}
        <img src="{{ site.img_path }}{{ post.image }}" alt="{{ post.title }}" class="thumbnail">
      {% endif %}
      <h2>{{ post.title }}</h2>
      <p>{{ post.subtitle }}</p>
      <p class="date">{{ post.date | date: "%d %B %Y" }}</p>
    </a>
  </article>
{% endfor %}