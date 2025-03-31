---
title: 'RetroPie Splashscreens'
permalink: /projects/graphics/retropie/splashscreens
dirname: 'splashscreens/'
excerpt: "Splashscreens for RetroPie"
header:
  overlay_image: /assets/img/feature/projects/graphics/splashscreens.jpg
  teaser: /assets/img/feature/projects/graphics/splashscreens.jpg
---

These are all splashscreens I've made from roughly 2014/15 until around 2019. Many of these I had to track down through Imgur and my posts on the RetroPie Forum. Sadly, the project files and assets are long gone, before I knew anything about backing stuff up

{% assign images = site.static_files | where_exp: "image", "image.path contains page.dirname" %}
<div class="image-gallery">
    {% for image in images %}
    <div class="box">
        <a href="{{ image.path }}">
            <img src="{{ image.path }}" alt="{{ image.name }}" class="img-gallery" loading="lazy" />
        </a>
    </div>
    {% endfor %}
</div>