---
title: "Bootleg Covers"
tags: projects graphics
permalink: /projects/graphics/bootleg-covers
toc: false
classes: wide
excerpt: "Covers for Concert Tapes"
header:
  overlay_image: /assets/img/blog/2025-03-31-bootlegcovers/header.jpg
  teaser: /assets/img/blog/2025-03-31-bootlegcovers/header.jpg
---
<div class="entries-grid">
    {% for collection in site.bootleg-covers %}
        <div class="grid__item">
            <article class="archive__item" itemscope="" itemtype="https://schema.org/CreativeWork">
                <div class="archive__item-teaser">
                    <img src="{{ collection.header.teaser }}" alt="">
                </div>
                <h2 class="archive__item-title no_toc" itemprop="headline">
                    <a href="{{ collection.permalink }}" rel="permalink">{{ collection.title }}</a>
                </h2>
                <p class="archive__item-excerpt" itemprop="description">{{ collection.excerpt }}</p>
            </article>
        </div>
    {% endfor %}
</div>