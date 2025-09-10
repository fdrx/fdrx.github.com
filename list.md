---
layout: default
title: List of posts
permalink: /list/
---
# List of Puerh Teas

<form id="filter-form">
  <label><input type="checkbox" name="sheng" value="sheng" checked> Sheng</label>
  <label><input type="checkbox" name="shu" value="shu" checked> Shu</label>
</form>

<div id="post-list">
  {% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" | sort: "name" | reverse %}
  {% for year_group in posts_by_year %}
    <br>
    <h2 class="dark-cell">{{ year_group.name }}</h2>
    <section>
      {% for post in year_group.items %}
        {% assign categories = post.categories | join: ' ' %}
        <article data-categories="{{ categories }}">
          <a class="dark" href="{{ post.url | relative_url }}">
            <h3>{{ post.title }}</h3>
            <p>{{ post.subtitle }}</p>
            <p class="date">{{ post.date | date: "%d %B %Y" }}</p>
          </a>
        </article>
      {% endfor %}
    </section>
  {% endfor %}
</div>

<script>
  function filterPosts() {
    var shengChecked = document.querySelector('input[name="sheng"]').checked;
    var shuChecked = document.querySelector('input[name="shu"]').checked;
    var articles = document.querySelectorAll('#post-list article');

    articles.forEach(article => {
      var categories = article.getAttribute('data-categories').split(' ');
      var show = (shengChecked && categories.includes('sheng')) || (shuChecked && categories.includes('shu')) || (!shengChecked && !shuChecked);
      article.style.display = show ? 'block' : 'none';
    });
  }

  window.onload = filterPosts;
  document.querySelectorAll('input[type="checkbox"]').forEach(checkbox => {
    checkbox.addEventListener('change', filterPosts);
  });

</script>