---
title: Blog
excerpt: "Non-project blog posts"
toc: false
classes: wide
permalink: /blog/
---

{% for post in site.posts %}
  {% if post.tags contains 'writing' %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}
