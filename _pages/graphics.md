---
title: Graphics
toc: false
permalink: /projects/graphics/
classes: wide
---

<div class="entries-grid">
    <div class="grid__item">
        <article class="archive__item" itemscope="" itemtype="https://schema.org/CreativeWork">
            <div class="archive__item-teaser">
                <img src="/assets/img/feature/projects/graphics/bootleg-covers.jpg" alt="">
            </div>
            <h2 class="archive__item-title no_toc" itemprop="headline">
                <a href="/projects/graphics/bootleg-covers" rel="permalink">Bootleg Covers</a>
            </h2>
            <p class="archive__item-excerpt" itemprop="description">Covers for Concert Tapes</p>
        </article>
    </div>
    {% for collection in site.graphics %}
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