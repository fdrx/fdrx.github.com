---
layout: default
title: List of teas
permalink: /list/
---
# List of Puerh Teas

{% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" | sort: "name" | reverse %}
{% for year_group in posts_by_year %}
  <br>
  <h2 class="dark-cell">{{ year_group.name }}</h2>
  <section>
    {% for post in year_group.items %}
      <article>
        <a class="dark" href="{{ post.url | relative_url }}">
          <h3>{{ post.title }}</h3>
          <p>{{ post.subtitle }}</p>
          <p class="date">{{ post.date | date: "%d %B %Y" }}</p>
        </a>
      </article>
    {% endfor %}
  </section>
{% endfor %}