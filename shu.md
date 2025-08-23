---
layout: default
title: Articles Shu
permalink: /shu/
---
# Shu Pu'er Tea

{% assign posts_by_year = site.categories.shu | group_by_exp: "post", "post.date | date: '%Y'" | sort: "name" | reverse %}
{% for year_group in posts_by_year %}
<br>
## {{ year_group.name }}
  <section>
    {% for post in year_group.items %}
      <article>
        <a href="{{ post.url | relative_url }}">
          <h3>{{ post.title }}</h3>
          <p>{{ post.subtitle }}</p>
          <p class="date">{{ post.date | date: "%d %B %Y" }}</p>
        </a>
      </article>
    {% endfor %}
  </section>
{% endfor %}