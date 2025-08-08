---
layout: default
title: Maps
---
<h1>{{ page.title }}</h1>

{% assign last = site.maps.first %}
<div class="last-post">
  <div class="left">
    <a href="{{ last.url | relative_url }}">
      {% if last.image and last.image[0] %}
        <img src="{{ site.img_path }}{{ last.image[0] }}" alt="{{ last.title }}">
      {% else %}
        <img src="{{ site.img_path }}placeholder.jpg" alt="{{ last.title }}">
      {% endif %}
    </a>
  </div>

  <div class="right">
    <a href="{{ last.url | relative_url }}">
      <h2>{{ last.title }}</h2>
      <p>{{ last.subtitle }}</p>
      <p class="date">{{ last.date | date: "%d %B %Y" }}</p>
    </a>
  </div>
</div>

<section>
  {% for map in site.maps offset:1 limit:9 %}
    <article>
      <a href="{{ map.url | relative_url }}">
        {% if map.image and map.image[0] %}
          <img src="{{ site.img_path }}{{ map.image[0] }}" alt="{{ map.title }}" class="thumbnail">
        {% else %}
          <img src="{{ site.img_path }}placeholder.jpg" alt="{{ map.title }}" class="thumbnail">
        {% endif %}
        <h2>{{ map.title }}</h2>
        <p>{{ map.subtitle }}</p>
        <p class="date">{{ map.date | date: "%d %B %Y" }}</p>
      </a>
    </article>
  {% endfor %}
</section>