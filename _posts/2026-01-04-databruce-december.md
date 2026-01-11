---
title: "Databruce 1.12 Update"
tags: projects databruce
excerpt: "All changes to Databruce in December 2025"
header:
  actions:
    - label: "Databruce"
      url: "https://databruce.com"
---
Happy New Year Everyone! Hope it's been a calm and uneventful one for you all so far.

Welcome to another update post covering changes to Databruce that happened throughout the month of December. I wanted to have this post up before the New Year, but if you read this blog you'll know I was [sidetracked](https://lilbud.github.io/2026/01/03/shuffle-ebook/) by something else.

Not a ton of new changes, mostly small fixes/tweaks to the site. Going forward the format for these will be as follows: listing all of the changes, then covering certain ones in detail if I feel the need to.

**Changes/Additions:**
- Added a ["changelog"](https://github.com/lilbud/django-databruce/blob/main/changelog.md) file to the Github repo, which lists changes/updates. To somewhat organize things, I retroactively added "version" markers. Just like the points, they are made up and don't matter. Smaller groups of updates will be a single point increment, while bigger updates will jump to the next tenth point. Is this the "right way" to do it? absolutely not. Does it work for me? for now yes.
- Added a "Remember Me" toggle, which should keep you logged into the site for 2 weeks...hopefully.
- Moved the SearchBuilder to a modal popup. This way it will stay on screen and not be made inaccessible when it is cut off.
- Event Detail page now has a "notes" tab. My plan is to make this the home for any extended notes/reviews pertaining to the show. Feature is modelled after the "news" tab from Speedrun.com, and each "item" will be in a card.
- Added a "First Friday" filter to the Nugs Releases table.
- Nugs Releases now show the time they were released if it was known. Thanks to Kieran Lane who tracked many of these times, with a few recent ones were done by me. Not all have times, but many do.
- Removed "Child Rows" from tables. These had the unintended side effect of massively slowing down screen size changes and page loading. On mobile, only the most important tables will be displayed.
- "Setlist Slots" now have a fixed date/location column, and the positions scroll horizontally.
**Fixes:**
- Fixed Advanced Search not searching properly. Certain filters were missing, and no matter what was typed the result set wouldn't filter correctly.
- Fixed SearchBuilder modal being too narrow on desktop.
- Readded the "Original Artist" column to the Songs table.
- Fixed links in the event tables not being clickable.

## SearchBuilder
SearchBuilder is something of a searching "middle ground". Being more powerful than simple text/regex search, but not quite at the level of a dedicated "advanced search".

At times, it is a finicky PITA, and if it wasn't useful I'd have tossed it. But, lacking any better options, I'm stuck with it and all the quirks it contains. One particular quirk was that it would position wherever it felt like, sometimes going way off screen or even being cut off vertically. 

Last month, I decided to fix this by moving the SearchBuilder to it's own dedicated popup modal. This way, I have full control over positioning/sizing, and it no longer gets cut off. Some quirks still remain, but it's better than it was. It also now fits a bit better visually with the sites overall design.

{% include figure popup=true image_path="/assets/img/blog/2026-01-04-databruce-december/searchbuilder-before.png" alt="" caption="Original SB popup, taken from DataTables docs." %}

{% include figure popup=true image_path="/assets/img/blog/2026-01-04-databruce-december/searchbuilder-after.png" alt="" caption="Much better." %}

## Nugs Releases
{% include figure popup=true image_path="/assets/img/blog/2026-01-04-databruce-december/first-friday.png" alt="" caption="Popup to filter releases" %}

{% include figure popup=true image_path="/assets/img/blog/2026-01-04-databruce-december/nugs-time.png" alt="" caption="Release Time tooltip" %}

A filter has been added to the Nugs table which allows filtering releases based on if they were a "First Friday" release or if they were a "Current Tour" release (High Hopes, River 16, 2023-25).

I might also add a filter for only Christmas releases, those ones are bonuses and are usually released anywhere from the 20th to the 24th of December.

Additionally, if the time of release is known then it now shows when hovering over the release date. The times shown are listed in UTC time, which is 6hrs ahead of EST. Otherwise if the time is 12am, then it isn't properly known.

Thanks again to Kieran who tracked many of these, with additional ones added by me. Not all are known, so keep that in mind.

## No More Child Rows
Child Rows is a feature for small screens, primarily mobile. Not all columns can be shown on a small screen, so this would move those to a collapsible row under the main row. Nice feature, but came at the cost of massively slowing down table loading and screen size changes. For reasons unknown, DataTables deletes the child rows when they aren't needed (screen wide enough), and remakes them when they are needed. I assumed this was a bug with DataTables, but it is simply how it works, even if it seems wasteful.

Because of these problems, I removed the child rows and simply adapted the tables to only show the most important rows on mobile/small screens. If I can find a way to have the child rows, *without* requiring the expensive redraw, I'll revisit this in the future.

<figure class="half">
    <a href="/assets/img/blog/2025-12-03-databruce-update/mobile-table-open.png"><img src="/assets/img/blog/2025-12-03-databruce-update/mobile-table-open.png"></a>
    <a href="/assets/img/blog/{{ page.url|slugify }}/no-child.png"><img src="/assets/img/blog/{{ page.url|slugify }}/no-child.png"></a>
    <figcaption>Before and After</figcaption>
</figure>

## Setlist Slots
Adding to the previous section, Setlist Slot tables now "fix" the Date/Location columns, and the positions scroll horizontally.

{% include figure popup=true image_path="/assets/img/blog/2026-01-04-databruce-december/setlist-slots.png" alt="" caption="" %}

---

That should wrap things up. Like I said, not every new change/feature will also include an in-depth section. Some months, there might just be a bullet point list and that's it. All depends on the changes/additions.

Thanks again for reading, and also for taking a chance on the site. It's a constant work in progress, and while some parts might lack compared to others, it can only improve from here.

Lilbud<br>
January 4, 2026