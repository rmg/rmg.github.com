---
layout: page
title: Ryan's Development Blog
#tagline: Ryan's Development Blog
---
Hi, my name is Ryan Graham and I like to write code. As such, this is my development blog.
{% for post in site.posts limit:3 %}
  <hr />
  <h2><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h2>
  <small>
    {{ post.date | date_to_string }}
    -
    <a href="{{ BASE_PATH }}{{ post.url }}#comments">comments &raquo;</a>
  </small>
  <p class="body">{{ post.content }}</p>
{% endfor %}
