---
title: Projects
excerpt: This page contains my many projects, sorted by vague category below. 
toc: true
permalink: /projects/
---

# Ongoing Projects

<ul>
{% for project in site.data.projects.ongoing %}
  {% assign matched_post = site.posts | where_exp: "item", "item.path contains project.url" | first %}
  {% if matched_post %}
    {% include post_date.html post_data=matched_post %}
  {% endif %}
{% endfor %}
</ul>

# Finished Projects

## Bruce Projects

<ul>
{% for project in site.data.projects.bruce %}
  {% assign matched_post = site.posts | where_exp: "item", "item.path contains project.url" | first %}
  {% if matched_post %}
    {% include post_date.html post_data=matched_post %}
  {% endif %}
{% endfor %}
</ul>

## Assorted

<ul>
{% for project in site.data.projects.assorted %}
  {% assign matched_post = site.posts | where_exp: "item", "item.path contains project.url" | first %}
  {% if matched_post %}
    {% include post_date.html post_data=matched_post %}
  {% endif %}
{% endfor %}
</ul>

## Graphics

<ul>
{% for project in site.data.projects.graphics %}
  {% assign matched_post = site.posts | where_exp: "item", "item.path contains project.url" | first %}
  {% if matched_post %}
    {% include post_date.html post_data=matched_post %}
  {% endif %}
{% endfor %}
</ul>

## Compilations

<ul>
{% for project in site.data.projects.compilations %}
  {% assign matched_post = site.posts | where_exp: "item", "item.path contains project.url" | first %}
  {% if matched_post %}
    {% include post_date.html post_data=matched_post %}
  {% endif %}
{% endfor %}
</ul>

## Retropie/Emulation Station

<ul>
{% for project in site.data.projects.retropie %}
  {% assign matched_post = site.posts | where_exp: "item", "item.path contains project.url" | first %}
  {% if matched_post %}
    {% include post_date.html post_data=matched_post %}
  {% endif %}
{% endfor %}
</ul>

<!-- {% assign posts = site.posts | where_exp:"post", "post.tags contains 'projects'" %}

### Graphics
<ul>
{% for post in posts %}
  {% if post.tags contains 'graphics' %}
    <li><a href="{{ post.url }}">{{ post.title }} <small class="post-date">{{ post.date | date_to_string }}</small></a></li>
  {% endif %}
{% endfor %}
</ul>

### Music
<ul>
{% for post in posts %}
  {% if post.tags contains 'music' %}
    <li><a href="{{ post.url }}">{{ post.title }} <small class="post-date">{{ post.date | date_to_string }}</small></a></li>
  {% endif %}
{% endfor %}
</ul>

### Programming
<ul>
{% for post in posts %}
  {% if post.tags contains 'programming' %}
    <li><a href="{{ post.url }}">{{ post.title }} <small class="post-date">{{ post.date | date_to_string }}</small></a></li>
  {% endif %}
{% endfor %}
</ul> -->