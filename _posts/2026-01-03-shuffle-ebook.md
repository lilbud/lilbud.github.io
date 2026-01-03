---
title: "E Street Shuffle Archive Part 2"
tags: projects archiving e-street-shuffle
excerpt: "Further plans to archive a disappearing blog."
header:
  actions:
    - label: "Github Repo"
      url: "https://github.com/lilbud/shuffle-archive"
---
Note: Part 1 of this can be found [here](https://lilbud.github.io/2025/12/11/shuffle-archive/). I'd recommend reading it to get caught up.

# Intro
If you're reading this, you most likely found your way here from Ken's final post on his E Street Shuffle blog. Or for some reason you regularly visit my site. Welcome in either case.

This post can be seen as a continuation of my previous post about the impending shutdown of Ken Rosen's E Street Shuffle blog. In that post, I cover the shutdown, as well as my disappointment at the fact that (at time of writing) portions of the site were already disappearing.

At the end of that post, I mentioned my (loose) plans for some kind of offline archive/backup of E Street Shuffle. While yes I had started work on it, the rest was still in the air like the human cannonball from *Wild Billy's Circus Story*.

Now, about a month later, I have a slightly better idea how I'm going about it, which is what this post will cover. To avoid repeating myself too much, I'd recommend reading Part 1, as it will catch you up. But the incredibly short version is that I have both an offline copy of the site, as well as the data of every post on the site. I'll go into detail on each, why each really isn't ideal, and what the plan is going forward.

# Archive Formats

## Format 1: HTTrack
Using HTTrack, an offline copy of the site was created back on December 1st. This copy functions just like the original site, and can even be used and navigated in the same way. There are however a few caveats with this approach.

1. HTTrack is a very unfriendly program to use. The default settings are incredibly slow, limited to downloading one file at a time at near dial-up download speeds. Even with more "ideal" settings, you're still looking at minimum 6-8hrs.
2. A "complete" backup requires around 11GB of storage space, which not everyone has.
3. At time of writing, it is unfortunately too late to create a complete backup. Since early December, around 100 posts have been deleted from the site in conjunction with the "bookshelf collection."

Given the size of the site, it's possible that even a "complete" HTTrack backup might have some broken links/pages. Those errors might not be discovered until after the corresponding posts/pages have already been deleted.

## Format 2: JSON Dump
This method has a good bit more promise, and is what I'm using as the basis going forward with this archive. Using the site's API and a bunch of poorly written Python, every post (including many revisions) have been saved to individual JSON files. Originally I simply saved each post, but adapted my approach upon discovering that posts were being "replaced in place" (meaning it's content was replaced, but the ID/URL remained the same.)

By doing things this way, I am able to preserve not just the content/formatting of each post, but all of its metadata as well. This (in theory) is a more "comprehensive" way of archiving the site, at the cost of being less accessible.

A PostgreSQL database has also been created from these files, with much of the data included. This (in theory) allows for easier querying/searching compared to looking through over 2000 JSON files, but also isn't super accessible.

All of the Python code, the post JSON files, and a dump of the associated PostgreSQL database will be made available on [Github](https://github.com/lilbud/shuffle-archive).

## Why Neither Format is Ideal
While yes, both formats listed above do archive and preserve the site, when it comes to access neither is ideal for about 95% of people reading this. I have to keep my audience in mind here.

The HTTrack backup, while a nice idea, won't work for most people. The storage requirement alone (11+ GB) puts it out of reach for most, whether they download an existing backup or create their own. Hosting this backup might prove tricky in the long run as well.

Additionally, while an offline copy of the site which can be browsed just like the original sounds nice in theory, in practice it is a bit obtuse. Without additional work, the search function doesn't work, so kind of like a library with no catalog or a book without a table of contents/index.

Also by the time you read this, portions of the site have been deleted. So even if you bother to spend the time running HTTrack and creating your own backup, it is too late and any backups will be incomplete. The backup could also have missing links/content, and if those errors aren't found in time (i.e. before the source pages are deleted/rewritten) then that is a problem as well.

The JSON dump takes up less space (~40MB), but as a format it is much less accessible. JSON is a format for data not for reading, and would require additional steps to convert those files into something actually readable. The code to do so will be provided yes, but that is something of a barrier to entry for most, and wouldn't be fair. 

So what now? While yes the site is backed up and will be preserved in some form, without it being accessible and (more importantly) readable it doesn't do anyone any good. An "ideal" backup format would have to be easily accessible, not require a ton of storage space, and also be readable like a book. Maybe an *electronic* book of some kind could be created, ideally one that can adapt to different devices/screens. Oh, and be completely free. That all shouldn't be too much to ask right?

# The E Street Shuffle eBook Project (Name TBD)
In the posts and emails concerning the "bookshelf collection" (BC), which is a series of physical (limited-run) books that are acting as the "official" archive of the site. Ken responded to questions from readers asking if the books will be made available digitally:

> This was easily the most frequently asked question! Nothing else even comes close. I don't have a happy answer, though. I'd love to, and if I knew of a good solution for it, I'd do it for free.
> 
> I know you're probably thinking that if I can print the book, there's probably a PDF source file or something, but there actually isn't. I'm partnering with a developer who's created a proprietary AI-driven platform for converting blogs into beautful books, and it doesn't have the ability to create ebook versions. (It was one of the ﬁrst questions I asked.) If that changes, I'll deﬁnitely let you know...
> 
> So for now, the answer is no, but then again that was my answer about transforming the blog into books until about a month ago, so you never know.
> - Bookshelf Collection Email Newsletter #1 (November 18, 2025).

In the November 28th post titled "Thirty-Seven Days Out", Ken gave a few options for those who've "enjoyed this site’s content and don’t want to lose access to it". Two ebook generator sites were listed but since he hadn't personally used them, they were essentially YMMV. Neither of them is free, both start at $20 and only increase from there with site size and quality. Additionally, much like HTTrack, unless you started this process in November it is too late to create a "complete" book as well over 100 posts have been deleted and countless more have been modified/mangled.

With no plans for official ebooks, I am announcing the "E Street Shuffle eBook Project" (name TBD). This project will work on creating freely available eBooks compiling the site's content. Additionally, I plan to release all of the tools/scripts as well as guides for those who want to do it themselves. This way, the books are available for those who just wish to read them, and the ability to make them is available for those who are interested.

This is a massive undertaking, with the books and the process still being developed and figured out. Unfortunately, while I hoped to have something to show by the time this goes live, that didn't happen. I can however share details on how the books will be broken up, and a bit about the early process in compiling the books.

## The Books
While I originally intended to simply follow the "official" Bookshelf Collection, with the books being broken up by category and/or theme, I'm instead opting to take a slightly different path for a few reasons.

The Bookshelf Collection, at time of writing, is expected to be spread out over a few dozen books. By the end of 2026, it's estimated to be 27 books (12 KoD, 8 RotD, 6 Cover Me). This is entirely due to limitations in physical book size and cost. Sure, there could be one massive book with everything, but it would be the size of and cost as much as a small car.

{% include figure popup=true image_path="/assets/img/blog/2026-01-03-shuffle-ebook/book.png" alt="man reading very tall book" caption="The Complete E Street Shuffle Bookshelf Collection, available for the low low price of $3,200 (plus shipping)." %}

eBooks are not subject to the same limitations as physical books, so page count isn't a concern. However, I still do plan to break the books up into chunks, just not as many as the physicals.

As of now, this is the planned list of books. These are subject to change as development is underway.

### Roll of the Dice: Bruce's Originals
This category focuses on Bruce's original songs, with 587 songs covered to date. I had thought about a book per album, but later decided to just do one book. Each album will get it's own chapter, first with the songs in running order, then the various outtakes from each album and it's sessions. There will also be chapters focusing on Bruce's early years (Castiles to Steel Mill), and also unreleased solo/E Street songs (those not associated with any album). Tracks 2 will be it's own section, not every song was covered so it might be one chapter rather than each lost album getting one.

### Kingdom of Days
I'm split on either doing a book per month, or just one big book with a chapter for each month. The former might be more "organized", but the latter will be easier from a production POV. When I make a decision I'll be sure to let everyone know.

### Cover Me: Bruce's Covers
As with the RotD book, this will also be one big book. The BC is breaking these up by "theme" (so far Encores and One-Offs), but there are only so many "themes" to group by. Because of that, all 987 songs covered as part of the "Cover Me" category will be ordered alphabetically and compiled into a single eBook.

### Meeting Across The River (Collabs with other artists)
Single big book, about 300 posts, ordered alphabetically by song.

### Where The Band Was (Concert Reviews)
This category consists of Ken (and other guest bloggers) recapping Bruce shows they've seen. Ken is including these as part of the Kingdom of Days books, but I feel it would be better as it's own standalone book. The reviews will be ordered by show date.

### Spare Parts (Odds and Ends/Sods)
There are a number of posts/categories on the site which don't really fit with any of the above books, so this book will be for those posts. Those categories are as follows:
- Spare Parts: Posts having to do with Bruce, but not fitting in any of the above categories.
- Uncategorized: The bulk of these are blog updates.
- Hearts of Stone: Only one post covering the work of the little known Bruce Springstone.
- Two Faces: A series of 3 posts written by guest author Katy Crane, a writer/teacher from Alaska.

The size and exact content of each book is still undetermined as there is a ton of work that needs to be done before the books can begin to take shape, which I'll cover in the next section.

# What Work Needs to be Done?
See `notes/fixes.md` and `cleanup.py` for more info

The bulk of this involves going through each post and doing some manual/semi-automated cleanup, as the content of each post is stored as HTML. Some cleanup has been done already (see `notes/fixes.md` in the Github repo), but more work is needed before the posts can be converted properly. The fixes range from fixing encoding issues to replacing parts of links when needed. Each post will then be previewed once formatted to ensure no issues remain.

As a quick note, I found a project named [StandardEbooks](https://standardebooks.org/) which makes public domain books into eBooks. They provide a toolkit, a guide for eBook creation, and a "manual of standards" that they follow to ensure every book (no matter source language/format) is of a consistent style. They're only mentioned because the plan is to apply some of their workflow to this project.

Only once the cleanup is done can the process of compiling the books actually begin. I'll admit, this part gave me trouble as I wasn't entirely sure how I'd go about it. Wasn't until I searched around for similar projects and found [otwarchive](https://github.com/otwcode/otwarchive), they use a tool named `ebook-convert` to turn written works into eBooks. `ebook-convert` is actually part of [Calibre](https://calibre-ebook.com/), an ebook manager program. Like the "StandardEbooks" project above, they're mentioned as a source of inspiration as I develop my project.

# What Will The Final Result Look Like?
The final "archive" will consist of a few things:
- Several eBooks in the ".epub" format. These can be read on computer using Calibre, on Android/iOS phones, and various eReader devices like Kobo and Kindle.
- Each post in the JSON file format.
- A dump of the PostgreSQL database
- All of the associated code required for every step of this project, as well as guides on using it.

Additionally, I might explore other formats like Markdown (which I used for my BTX Article Dump project), and possibly a "static" form of the site. These are not yet decided upon and shouldn't be expected until the archive is "finished"

# When Can The Final Result Be Expected?
I don't know.

While portions of the archive like the JSON files and the database dump are available now, the rest is in the works. I'm not great at estimating time of projects, which is clear if you've followed any of my other projects. They either get finished at rapid pace or take far longer than I anticipated. My "Radio Nowhere Archive" project was supposed to be finished at the end of 2025, I'm still on 2002. 

Because of that, no hard date will be given just yet as I'll inevitably miss it anyway. Updates to the project will be posted here, and also possibly on Bruce forums like GreasyLake. If I had a fancy-schmancy newsletter I'd say sign up, but unfortunately I don't. That might change in the future however, and I'll update if that happens.

# Conclusion
I've seen a few Bruce sites either completely or partially disappear, years or even *decades* of content gone in no time flat. Not all of them were archived, at least not in any complete form. That can't happen to E Street Shuffle, as it's a great resource that shouldn't be lost. While I'm disappointed at the way the site is going out, I fully intend to do something about it.

I want to thank Ken Rosen for creating the E Street Shuffle in the first place. As well as responding over email to my many questions concerning the shutdown/future plans. I also want to thank him for being accepting of my efforts, and even allowing this post to be included in his final ESS post. He just as easily could've tried to shut me down, and I'm thankful he didn't.

Pretty sure this is the longest piece of writing I've done in a hot minute. So if you made it through all that, thanks a lot (seriously!) There was a *ton* of ground to cover, and there were still parts that didn't make the final cut.

If anyone has any questions, you can use the contact form [here](https://www.databruce.com/contact/) to get in touch. I'm also available on GreasyLake, and Discord as well.

Thanks!

Lilbud (January 3, 2026)