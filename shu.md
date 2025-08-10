---
layout: default
title: Articles Shu
permalink: /shu/
---
# Shu Pu'er Tea

<section>
  {% for post in site.categories.shu %}
    <article>
      <a href="{{ post.url | relative_url }}">
        <!-- {% if post.image[0] %}
          <img src="{{ site.img_path }}{{ post.image[0] }}" alt="{{ post.title }}" class="thumbnail">
        {% elsif post.image %}
          <img src="{{ site.img_path }}{{ post.image }}" alt="{{ post.title }}" class="thumbnail">
        {% endif %} -->
        <h2>{{ post.title }}</h2>
        <p>{{ post.subtitle }}</p>
        <p class="date">{{ post.date | date: "%d %B %Y" }}</p>
      </a>
    </article>
  {% endfor %}
</section>