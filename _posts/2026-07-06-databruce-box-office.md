---
title: "Databruce now has Box Office Data!"
tags: projects databruce
excerpt: "A quick story about tickets, old magazines, and archives that haven't visually changed since the 2000s"
header:
  actions:
    - label: "Databruce"
      url: "https://databruce.com"
---

The past few weeks have been spent digging through (digital) archives to pull together a new data source for Databruce: box office/ticket sales data for shows from 1976-2026.

When I added this to the roadmap, it was done as an afterthought. As when I did, I wasn't 100% sure if it was going to be possible to accomplish. I simply needed things to fill out the roadmap so it looked a bit more "complete" and to maintain the illusion that I know what I'm doing and have actual "plans" with "thought" put into them when it comes to DB. Because I definitely do.

In all seriousness, I was clueless on a ton regarding this. I knew that the data was published at some point, and that it was somewhere online since it was cited on Wikipedia. Brucebase even mentioned something called "Billboard Magazine" in a few event notes. But what this was and (more importantly) how/where to find it wasn't immediately evident.

# WorldRadioHistory
In my searches I found [WorldRadioHistory.com](https://www.worldradiohistory.com/Archive-All-Music/Billboard-Magazine.htm). An absolutely incredible resource ran by David Gleason, 60+ year veteran of the radio industry and archivist. Might be a stretch but it could very well be the "Library of Alexandria" for the radio/music industry? Seemingly every magazine or book pertaining to that industry is available on the site, *for free* no less. I'll link a [page by Ricoh](https://www.pfu-us.ricoh.com/resources/customer-stories/world-radio-history) which talks about him more, and I highly encourage checking out the site.

David's site has an archive of Billboard Magazine which stretches back to it's founding in the late 19th century. This archive is freely available and searchable, which would (in-theory) cut down on the work needed on my end, or at least cut down how many issues I'd have to sort through.

The site initially returned around 200 results for Bruce in the form of OCRd scans of BB Magazine. Although an additional 50 or so would be needed, as a number of pages didn't OCR as "Bruce" or "Springsteen" and wasn't found by the site search. Some scans even had to be found elsewhere as the scan quality was so poor it was basically unreadable. All total I think nearly 250 magazine issues were used to source all of this data.

# Sources
A few main data sources were used:

- Billboard Magazine
- Pollstar Magazine
- Archives of Billboard's website via Wayback Machine
- TouringData.com.

Billboard (both magazine and website) was the main data source as it was simply the most complete throughout the years. A few gaps during Joad and the Reunion tour were found in Pollstar Magazine (which led to a way too much math). The archives of both cut off before present day (Billboard in 2019, and Pollstar in 2010). Which necessitated the use of "touringdata.com" was used for 2023-2026 data. Although unfortunately they don't track ticket prices.

# Data Extraction
While I had hoped that someone had already compiled an online database of Billboard's box office info, I wasn't able to find one. The magazine scans were the only source online, and their often poor quality meant that any automated tools were out, least for the *extraction* of the data. This would have to be done manually.

Over the past few weeks, I went week by week through Billboard Magazine from 1976 through 2017 to pull together box office data for nearly 1000 Bruce shows. The process was occasionally tedious, though once I got into a flow it went pretty quick. Even found a few box office reports for shows that Wikipedia didn't have listed.

For those shows, it is now known how many attended these shows, what they paid for their tickets, how much Bruce raked in, and even the persons responsible for promoting the show.

There are a few caveats however:

- Box Office data (unfortunately) could not be found for many shows. Pre-1976 is a blindspot. 1981 and 1985 shows outside North America also have very little known data, the latter is a shame because it was him at his biggest and most successful and being able to see the numbers would be neat.
- Show "runs" were only ever reported grouped together, so runs like MSG 2000 only ever listed how much was sold for all 10 shows instead of individually. While a run might've fully sold out, the "per-night" totals could've differed ever so slightly. Rather than do the math and report potentially incorrect data, these were left as-is.

If anyone has any lead on pre-1976 box office info, or any missing show info, please get in touch.

# Conclusion
In the end, I think it was worth it to "liberate" this data from old magazine scans. Far as I'm aware, this data has never been made widely available. Some of the data is listed and cited on Wikipedia, and a few Brucebase pages will occasionally make an offhand mention of Billboard without proper citation (which isn't entirely new for them). There has never been an effort undertaken to compile this data together in this form. It is a valuabe resource I think, and part of my quest to make Databruce the most comprehensive Bruce database out there.
