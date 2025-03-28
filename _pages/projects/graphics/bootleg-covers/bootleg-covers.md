---
permalink: /projects/graphics/bootleg-covers
layout: splash
title: "Bootleg Covers"
excerpt: "Covers for Concert Tapes/Bootlegs"
feature-path: "/assets/img/graphics/bootleg-covers/artist-img"
header:
  overlay_image: /assets/img/graphics/bootleg-covers/bootleg-covers-feature.jpg
images:
 - folder: bowie
   name: "David Bowie"
 - folder: bruce
   name: "Bruce Springsteen"
 - folder: gd
   name: "Grateful Dead"
 - folder: goose
   name: "Goose"
 - folder: deadco
   name: "Dead & Company"
 - folder: mccartney
   name: "Paul McCartney"
 - folder: orebolo
   name: "Orebolo"
 - folder: queen
   name: "Queen"
 - folder: stones
   name: "The Rolling Stones"
 - folder: billyjoel
   name: "Billy Joel"
 - folder: other
   name: "Other"
---

<figure class="third">
    {% for image in page.images %}
        <a href='{{ page.permalink }}/{{ image.folder }}'>
            <figcaption><h1>{{ image.name }}</h1></figcaption>
            <img src='{{ page.feature-path }}/{{ image.folder }}.jpg'>
        </a>
    {% endfor %}
</figure>
