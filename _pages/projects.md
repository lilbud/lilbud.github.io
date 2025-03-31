---
title: Projects
excerpt: This page contains my many projects, sorted by vague category below. 
toc: true
permalink: /projects/
---

{% assign posts = site.posts | where_exp:"post", "post.tags contains 'projects'" %}

### Graphics
{% for post in posts %}
  {% if post.tags contains 'graphics' %}
<ul><li><a href="{{ post.url }}">{{ post.title }} <small class="post-date">{{ post.date | date_to_string }}</small></a></li></ul>
  {% endif %}
{% endfor %}

### Music
{% for post in posts %}
  {% if post.tags contains 'music' %}
<ul><li><a href="{{ post.url }}">{{ post.title }} <small class="post-date">{{ post.date | date_to_string }}</small></a></li></ul>
  {% endif %}
{% endfor %}

### Programming
{% for post in posts %}
  {% if post.tags contains 'programming' %}
<ul><li><a href="{{ post.url }}">{{ post.title }} <small class="post-date">{{ post.date | date_to_string }}</small></a></li></ul>
  {% endif %}
{% endfor %}