---
title: "Announcing the Databruce Article Library"
tags: databruce
excerpt: "A new useful site feature has landed"
---

The Databruce Article Library (name pending) is a collection of articles from various sources online. All archived and made fully text searchable.

Currently, the library stands at around 1,500 articles. These were pulled from a 3 main sources, which I'll get into below. They were converted to markdown and had some formatting fixes applied (some automated, others manual). If needed, I tracked down the original source and used that instead.

I already covered most of the formatting fixes in my [BTX Article Thread Backup](https://lilbud.github.io/2025/04/09/btx-article-thread/) write-up over on my blog. So, go read that for an overview on the tools and methods used.

Below I'll cover each source.

# BTX Article Thread
Note: See [here](https://lilbud.github.io/2025/04/09/btx-article-thread/) for more info. Below will be a brief overview of that post.

In 2023, the Backstreets Ticket Exchange (BTX) forum was set to be shutdown. This was a move that made some happy and others sad.

Before the site was gone forever, I worked on archiving a few of the threads there. The Article Thread was among them, compiling together hundreds of Bruce-related articles from all over the place.

At the time, I simply saved all 88 pages as HTML and dumped them on Github. As I had neither the skilled, or (I assumed) the time, to do much more.

But, as we all know, BTX did not shut down, and is still live today.

In March 2025, I went back through and converted the articles from HTML to Markdown. Splitting them into separate files and fixing formatting when I could. I ended up with around 1,000 articles from that thread.

Fast-forward to today. I had all these `.md` files, but really no way to make use of them. Initially, I created a Google Sheet with all the articles listed and links to them, which *worked* but wasn't ideal. Wanting to compile them into a more usable form, and now having both the ability and place to make them available, I set upon loading them into the Databruce database.

Since each article was in it's own file (mostly), it was a pretty easy process. Using a library known as `python-frontmatter` greatly simplified this process. One article was a collection of bits and pieces, and had to be manually split into articles. This added another 30 to the total, crossing the 1,000 article threshold.

# ShoreFireMedia Press Releases

Without remembering exactly how or when, I came across the ShoreFire Media page for Bruce. This page contained all of his press releases from 2012 until April 2026. On a whim, I archived all of the releases, figuring it was a potentially useful resource to archive.

Following the BTX Thread, this was next up to be added. Similar process, converting from HTML to Markdown using various Python libraries. And just like that, another 60 articles were in the library. I have yet to find any press releases from pre-2012, of which I'm sure there are quite a few. Bruce's official site has an archive going back to 2012, possibly overlapping the ShoreFire releases. This will make a source to look into one day, but not today.

This adds another 90 to the overall total.

# GreasyLake Article Vault

This is the big one. And it requires a bit of backstory to properly explain.

The TL;DR is that all ~500 articles from the inaccessible GL Article Vault are now available again.

Read on for the whole story:

On August 9, 2024, GreasyLake announced that due to an outdated content management system, every part of the site with the exception of "The Circuit" was to be shut down. This was done with zero advance warning, only being known when the announcement banner appeared at the top of the page.

{% include figure popup=true img1="/assets/img/blog/2026-08-28-databruce-articles/gl-announce.png" alt="Post announcing the shutdown of most of GreasyLake" caption="The announcement in full" %}

GL is one of the oldest still-active Bruce fan forums, stretching back all the way to the late 1990s, which is practically unheard of by internet forum standards.

The archive of content available is truly something, and to lose it is a real shame. The site included things like an archive of the early message board, show/setlist notes and reviews, discography info, and (most importantly) a massive collection of Bruce-related articles. Many of which were only ever available on GreasyLake.

Immediately, I reached out and asked if/when this content would be available again. As well as suggesting some avenues for making it available.

The next day, I received a response from Karsten (CosmicKid, site admin). Karsten explained that "the underlying database still exists and maybe at some point I can put it to use again". However an impending site upgrade was needed before it was possible to do so. But, he mentioned having plans to "revive parts of it as an integrated part of the community site." But, no timeline was provided. Furthermore, any possibility of creating a static archive was shut down as it would "take a significant amount of time and effort" and he wasn't sure if it was "worth it considering it probably wouldn't be used all that much."

With this in mind, I first went to archive.org to find as much as I could. While a good bit was archived there, it wasn't everything. Around 170 of the articles were available, as well as some of the Lake Scrolls pages. For now, it would have to do.

Jumping ahead a bit to June of 2025, GL suffered a brief outage when the forum was inaccessible. But, the *original* site was accessible again. Wasting no time, I spun up HTTrack and archived as much of the site as I could with the brief window I had. Shortly after the program was done, the current GL site was restored.

The result was a mostly complete archive of the old GL. I successfully managed to save the rest of the missing articles, as well as the pages for: songs, performances, the news blog and the list of releases. At some point I do plan to make this available, but there are many busted links present that would require some work before it's ready for public consumption.

From this archive, 493 articles were saved and are now once again publicly available. Of these, 32 were "GL Exclusives" and have never been published elsewhere. There are also 25 press releases from 1998-2011.

These articles required significantly more effort to cleanup due to issues in the original formatting. For reasons unknown, all accented characters, quotes, em-dashes, and other special characters were replaced with `?`. This made reading the articles slightly difficult.

None of these have categories at time of writing, however I will be working on adding them soon. Additionally while I was able to fix many of those formatting issues, a few remain that I am unable to fix.

This is where I need to ask for some help.

## A Call for Help

There are 8 articles which suffer from the formatting issue mentioned above. Further complicating things, none of them are in English, but rather a mix of Spanish, German, Norwegian, Swedish, and Dutch.

On the "Articles" page, these can be found under the "Help Wanted" category. Additionally, a list of them with info can be found on this [Google Sheet](https://docs.google.com/spreadsheets/d/12uwQxf1O1yn5ctPGwqbNjRftjDeLKu7Mlh3fS5vROqI/edit?usp=sharing). I managed to find some articles online, but are either paywalled or inaccessible to me.

If you are able to help fix the missing characters, please get in touch via the [site contact form](https://databruce.com/contact) or message me via GL/Discord.

# Searching

Every article in the library is fully text searchable. Meaning articles can be found via content/author. Articles can also be filtered by publication year as well.

I did this because I think having them be searchable makes this a useful resource for research, and just anyone interested in Bruce from the perspective of the many who've written about him over the years.

The general layout and functionality was inspired by the Video Game History Foundation's digital library.

# Conclusion

At time of writing, 1,584 articles are now part of the Article Library. I plan to add more in the future like the GL news blog entries, news items from Bruce's site, and even all of the news items from Backstreets. These are all TBD.

I hope everyone enjoys. If you ever have any comments/questions, feel free to reach out via the site contact form.

Thanks!
Brian (August 28, 2026).
