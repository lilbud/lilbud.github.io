---
title: "Backstreets Magazine Archive"
tags: projects music
excerpt: "An archive of Backstreets Magazine, available digitally for the first time"
header:
  overlay_image: /assets/img/blog/2025-04-06-backstreets-mag-archive/header.jpg
  teaser: /assets/img/blog/2025-04-06-backstreets-mag-archive/preview.jpg
  actions:
    - label: "Internet Archive"
      url: "https://archive.org/search?query=creator%3ABackstreets+Magazine&sort=title"
    - label: "MEGA"
      url: "https://mega.nz/folder/QgB0zbCb#J9tQIU21dDf-cgQKwrvUiA"
    - label: "List of Issues"
      url: "https://docs.google.com/spreadsheets/d/1Rc8c3gvKWHdAo9bx9Fkl6Dg5RlF5ENr5dqpb_C_uBZs/edit?usp=sharing"
---

![](/assets/img/blog/2025-04-06-backstreets-mag-archive/logo.png)

**Project Start:** March 26, 2025<br>**Project End:** April 6, 2025

Torrent file will also available on Jungleland torrents.

## History of Backstreets
It's late 2013. Somewhere in North Carolina, the folks at Backstreets Magazine have just published issue #91, paying tribute to Clarence Clemons who passed away two years prior. Little did anyone know at the time, but this would be the final issue of Backstreets Magazine, ending a 43 year run that started when Charles Cross was handing out the first issue at Bruce's show in Seattle on October 24, 1980. 

Backstreets Magazine is an interesting publication, it was one of the first magazines dedicated to Bruce Springsteen (being beaten to the punch by Thunder Road mag in 1978), and quite possibly the most well known. It acts as a time capsule of sorts, having "live in the moment" reactions to nearly every show and album release from 1980-2013. It is a treasure trove of interviews, reviews, commentary, opinions, and a written record of the relationship Bruce has with his fans.

A treasure trove that was largely inaccessible on the internet...until now.

Thanks to myself and members of the StonePonyLondon forum, the entire run of Backstreets Magazine has been digitized and is now freely available for anyone to read and download.

## Project Intro
I basically stumbled into this project without really intending to.

I have a number of archival Bruce-related projects under my belt. Things like the [BTX Article Thread Backup](https://github.com/lilbud/btx-article-dump), which is a text-based archive of nearly 1,000 articles. Or the [Radio Nowhere Archive](https://archive.org/details/radionowhere), which is an ongoing project working to make as many bootlegs freely available for stream/download.

I also have a list of projects to look into, one of them being an archive of Backstreets Magazine. Although, I figured this would've been an "overtime" project. One where I'd stumble upon issues here and there, and build up the archive over a few weeks or even months.

On March 26, I went to StonePonyLondon, a Bruce forum that has been around for a number of years (pretty sure longer than I have). There was a thread posted by BigD asking if anyone had a scan of Backstreets #11. A member named Garry responded with a scanned copy, which I then took and formatted those JPGs into a PDF. I then asked if there were more copies out there, fully thinking that the response would be no, and that would be it. Surely it couldn't be that easy right?

{% include video id="h9uA45vwdb0" provider="youtube" %}

## It Really Was That Easy
Garry responded the next day, having uploaded scans of 78 issues, over 3/4 of the entire run. I honestly couldn't believe it. In less than 24hrs we went from only one issue being available online to nearly the entire run.

This left 13 issues to find, which I again figured this would take a while, and once again I was almost immediately proven wrong. A member named Hey_Eddie showed up with a scan of issue 44, BigD popped up with 45, 48, 56, and 57, although these issues were later rescanned by Ed.

At this point, I realized that at this pace there was a very real possibility of completing the entire set. 

Over the next few days, Eddie worked on filling in the gaps with brand new scans he did just for this project. If I thanked him once I've done so a dozen times, but I'm thanking him again. He went above and beyond even my wildest expectations.

## The Process
There is a mostly common process that went into organizing all of this, which varies based on the source of the scans. A number of software tools were also used.

All of the issues received from Garry were in the form of JPG images. Which had to be merged into PDF files. I first used Adobe Acrobat, but I found it a pain to use due to frequent freezing/crashing. I switched over to a Python library named `img2pdf`, which does exactly what it says on the tin. This gave me a folder of PDF files to move on to the next step.

For the issues provided by Eddie, these were already PDF files, completely skipping the need for the above step. Eddie used an Epson V600 Photo Scanner to scan his issues. This was done at 300dpi resolution, and resulted in very high quality scans. The Epson software also handled OCR, which takes the text on the scanned pages and turns it into actual searchable text.

Very little work was needed on Eddie's scans, which saved me a good bit of time. The most that had to be done was fixing the orientation of some pages that the Epson software mistakenly rotated.

After I had PDFs of all the issues (from both Garry and Ed), I next used another Python library named `ocrmypdf`. Which uses the same Tesseract OCR process that the Internet Archive does. Ed's scans were already OCRd by the scanner, but I wanted to redo all of the issues with the same tool so they were all mostly consistent.

10 of the issues were scanned as spreads, rather than single pages. Since the other 81 issues were single pages, I asked Eddie to rescan these just to keep everything consistent with each other.

Once the issues were ready, they were then uploaded to both MEGA and Archive.org. I also plan to release a torrent file on Jungleland so stay tuned for that.

I really want to thank Eddie for scanning and even rescanning a number of issues. We had the shared goal of making this as good as it could possibly be. Because of his efforts, these are the highest quality versions of these issues available anywhere on the internet.

## Comparisons
Real quick, I wanted to show a before and after of sorts. Comparing a few early scans to their final versions included in this project. 

First up is issue 47. The original was provided by Garry, and a rescan was done by Eddie. This mostly shows the quality increase that the Epson V600 provides.

<a href="/assets/img/blog/2025-04-06-backstreets-mag-archive/issue47-comparison.jpg">
    <img src="/assets/img/blog/2025-04-06-backstreets-mag-archive/issue47-comparison.jpg" alt="{{ name.last }}" loading="lazy" />
</a>

Next is a quick before and after of issue 73. Which Eddie scanned and then rescanned after dialing in his process.

<a href="/assets/img/blog/2025-04-06-backstreets-mag-archive/issue73-compare.jpg">
    <img src="/assets/img/blog/2025-04-06-backstreets-mag-archive/issue73-compare.jpg" alt="{{ name.last }}" loading="lazy" />
</a>

## User Contributions:
Below I'll list each users contributions:
- Eddie:
    - Issues: 44, 60, 63-65, 73, 77-78, 80, 91
    - Rescans: 45, 47-48, 52, 54, 55-57, 59, 67, 70-71, 74-75, 79
- BigD (His scans were replaced by new scans done by Ed):
    - 44, 45, 56, 57
- Garry:
    - 1-43, 46, 47, 49, 55, 58, 59, 61, 62, 66-72, 74-76, 79, 81-90

## Stats
Lastly, inspired by something Eddie said, I want to provide some of the numbers behind this project.

- Number of Issues: 91 (4 double issues, and 1 collection)
- Total Number of Pages: 3663
- Pages rescanned by Eddie: 1120 (not too far off his guess)

## Thanks
Wanted to wrap this up with some thanks.

First I want to thank Garry, who is responsible for the bulk of the archive at 74 issues.

Next is Eddie, as mentioned he went above and beyond what I expected. He is responsible for 25 out of 91 issues, 15 of those being brand new scans. I really can't thank him enough. Can't imagine how much time it took him to scan and rescan all these issues to get everything "just exactly perfect".

I want to thank BigD, who started the initial thread and got the ball rolling on this project. I doubt he had any idea what his request for a single issue would lead to.

And finally, thanks to Charles R. Cross and everyone involved with Backstreets Magazine over the years. I don't think it can be put into words the impact their magazine has had on the community, even 40+ years later.

## Conclusion
As mentioned, I didn't have any of this in mind. I really thought that it was going to take months of on and off searching to track down these magazines. I had no idea that not only would every single issue be found, but that it would happen so quickly. From BigD's original post, it took less than 2 weeks to have a digital copy of every issue in hand. This is only because of community working to accomplish this. I can't thank all of them enough.