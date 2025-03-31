---
title: "Databruce v2"
excerpt: "A PostgreSQL Database of Bruce Springsteens Performing Career"
tags: writing bruce
toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky: true
header:
  actions:
    - label: "View on Github"
      url: "https://github.com/lilbud/Databruce"
---


> "Welcome back I guess, I'm sure you missed me more than I missed you" - Bruce Campbell (Spider Man 2 video game, 2004)

Note: This is part one of a longer post, covering both the update of Databruce as well as Brucebot.

### Intro and Background

I have a post from September 2023 detailing the initial development of my Databruce project from March 2023 until about the end of August 2023. I'll try to summarize that post below.

In March 2023, a friend posted about a quick scraper they developed in Google Sheets to pull setlists automatically from a website called Brucebase (a sort-of database about Bruce Springsteen). This got me interested in looking into web scraping, not something I'd ever thought about before. A bit later, I had the first incredibly basic version of a scraper written in Python while bored at work.

While this worked well enough, it limited my options going forward. Scraping data from the site could be fairly slow (no public database or API of any kind). Plus, without a place to store the data, every request would mean scraping that page again and again.

Around May/June 2023, I started looking into developing my own database. I hadn't touched SQL since taking an Intro to SQL college course in early 2022. The first version of the database was built on SQLite, which seemed like a good "beginner" database. I set to work figuring out how to not only scrape the data, but also formatting it and saving it in the database. This took a few weeks, and on July 25, 2023, the database was "done". The bot was also converted to use this DB instead of scraping. 

In August 2023, I migrated the Discord bot to Heroku. They only allow PostgreSQL, which meant finding a way to convert the SQLite DB to Postgres. I was still primarily using SQLite locally, and wasn't ready to make the change to Postgres fully. I was still a beginner with SQL, and Postgres was out of my wheelhouse at the time. I stuck with SQLite, and resorted to using various command line tools to push updates to Heroku Postgres.

After this, the database really didn't change a whole ton. It mostly stayed the same while I finished up my last semester of college in Fall 2023. Only big change (going off discord messages and commits, as I'm writing this over a year later) was adding a marker to track song segues (things like Not Fade Away > She's The One).

### We can rebuild it, we have the technology.

In early 2024, I started thinking about redoing the database. One downside to the "figure it out as I went along" approach is that it was a big mess. Mostly with the way I handled scraping and formatting the data. Looking at the pile of spaghetti code held together with duct tape, I thought of better ways to handle both the scraping and formatting. This process begun in Jan/Feb 2024, first starting with finding a better way to scrape the data. 

How web scraping is done is simply by making a request to a URL, then using a library to parse the HTML of that response. Initially I used the `Requests` library to make the request, and a library named `BeautifulSoup` to handle the parsing. I definitely wasn't doing things "the right way" on the first version. One thing I didn't know about was specifying the User-Agent string so that the requests would say "Firefox 6X.XX" instead of "Python-Requests". Many sites would restrict the latter because it is obviously a scraping bot, whereas the former is more than likely a normal user. This came into play when pulling bootleg data from SpringsteenLyrics (foreshadowing?), as the request library was blocked on sight.

In addition, I switched to a new library for the requests named `httpx`. Which in addition to being easier to work with, it taught me about using a "client" to pool the requests and connections together. Otherwise, a new connection is opened for every request to every single page, which as it turns out is a Very Bad Idea. I didn't realize how much of a difference this would make until I started scraping the data for version 2. Originally, updates would take a decent amount of time due to the above reasons. This was cut down to less than a second per page with the pooled connections.

With this new approach to scraping, getting the data was much faster. As well as being much safer with its impact to the various sites that were being scraped. I also found smarter ways to pull the data from each site. I attempted to find ways to pull the data while keeping the number of pages needing to be touched to a minimum. Originally I used the sitemap but this would be quite slow and would require a ton of checking to only grab the proper links. Not to mention having to parse the data which required a ton of work as well.

### Data parsing, or a guide to going insane over commas

If you couldn't tell, I'm making most of this up as I go along. 

Once I was able to scrape the data, it had to be parsed/formatted before being inserted into the database (still SQLite, stay tuned).

The single hardest part to handle formatting for was the table of venues. On the face of it, each venue name is in the format of `name, city, state/country`, simple right?

No

This required more checks than I thought I would need. The first version pretty much just checked for 3 or 4 comma separated components. Which worked, but some things still slipped through. Incorrectly formatted names (missing commas usually), as well as the occasional name that didn't match the format above and necessitated a rewrite of the parsing code.

This part took a few attempts to get right. Not only to catch the various formats of venue names, but fixing the few formatting errors, as well as separating the components properly.

None of the other data gave me as many issues as the venues. Even though version 2 introduced a whole ton more data to the database.

### Types of Data

This image comparing the databases will show the different better than I can explain it.

<!-- [include the two images of tables here] -->

In addition to wanting to redo the scraping/parsing code, I wanted to expand the database a good bit. The original database only tracked all of the data that was necessary for the bot at the time. The two projects are very much connected in that respect. However, I started thinking about new stats I wanted to track and be able to look up easily. Stuff like more advanced setlist stats (opener/closer, show gaps, notes on first/last time played, etc.) Or maybe even notes on all the various snippets like those in Detroit Medley.

Everything from the original database made it over (although after being scraped again and reorganized into something more like a "proper" database.) In addition I added:
- Info on Nugs releases, which I tracked in a spreadsheet years ago and just had to update a bit. (Thanks to mgravitt2 on the GreasyLake forum, who provided the release dates for the 2014-2016 shows.)
- Expanded info on the locations Bruce has played. Counting Cities/States/Countries and even Continents. Plus better organizing the venue data by being able to have a correct list of those locations to reference.
- A list of people onstage at every event, which was already tracked by Brucebase. But it took some work to scrape it correctly accounting for the HTML indenting and lists. This allows me to show the band/group an individual appears with at an event. 
- As mentioned, I redid the setlist table. Now properly tracking sequences and segues, as well as premieres/debuts. Also added is a "next/last" gap column. Counting how many shows since a song was played. This is useful for calculating bustouts.
- I also compiled a list of bootlegs, which will require its own section.

### Just Glad My Boots Are On

This was not something included in the first database. The bot had a "bootleg" command, but this only returned a URL for a site called "SpringsteenLyrics", which has a massive list of bootlegs. I found a way to insert the date in the search URL, and that was it.

I figured if I was to do this right, I would want to have a massive list of bootlegs of my own. So that the bot could list all the bootlegs for a given date, instead of sending a link to a page. I looked into where to source this data, preferably a place that just has a public database or API I could grab the data from.

This doesn't exist, well it didn't exist in the form mentioned above. There are two big sites that track this stuff:

- SpringsteenLyrics.com: most up to date, and mostly organized. Around a few thousand bootlegs.
- The Killing Floor: hasn't been updated since 2019, pretty sure the site hasn't been properly updated since before I was born. Only about 400 bootlegs.
- Bruceinboots.guru: relatively new site, built upon springsteenlyrics data and for the most part is just a frontend to that site (all links point there, no info on this site other than user submitted ratings.) 6k bootlegs.

Originally I went with Bruceinboots. As it was the easiest to grab data from, most of the data is stored in a single table with no pagination (this is good for scraping, but bad design overall.) Although once I got the data, I realized quickly that it was a mess. For some reason, the 'title' column is capped at 41 characters. Cutting off most if not all of the bootleg names. Links are included to springsteenlyrics, but they basically do what I was doing with the bots bootleg command (just pointing to the date query). So, getting any further data would mean cross-referencing splyrics.

I figured it best to just go with splyrics. Their site was a little more complicated to navigate, but it all worked out. They organize bootlegs by type and grouping by every few years. Maybe its an item cap? not exactly sure. This took longer than necessary, going by category and then having to go by a number of pages in each. After much work I was able to pull this info into the database. This data was then *heavily* modified/edited after database insertion. While it was somewhat organized, it was in varying states of one big mess. It is still a ton of data (6,500 bootlegs) and even after removing the duplicate entries, I was still left around 4,500 bootlegs. For the most part I just standardized the info, fixing formatting issues and whatnot. Far too much data to manually sort through.

I eventually found another site (https://springsteendvds.wordpress.com), which gave me a list of bootleg DVDs to add to the database. I also reached out to mjk5510, who provided an updated version of his "Multiple Recorder Project" spreadsheet, which tracks different recordings for the same show. These two sources brought the total up to around 5,000 bootlegs.

### Making That Change Uptown

With all this data somewhat organized, my focus turned back to the database itself. Since its conception, the database was built in SQLite. This worked for a while as it is decently beginner friendly. However, as mentioned the bot moved hosts from Repl.it (SQLite friendly), to Heroku (no SQLite). Heroku only allows the use of PostgreSQL, which meant either finding a way to somehow push the SQLite data to Postgres, or switching over to Postgres.

I stuck with SQLite, as I was still somewhat of a beginner with SQL in general, and generally felt better with SQLite. Plus, around this time (August 2023) I was getting ready for my last semester of college before graduation, and generally wasn't sure of my plans afterwards. I would be busy for the next few months at least, which meant that for the meantime, Databruce would stay SQLite. I really didn't make use of any advanced SQL features, at the time didn't see any benefit to switching full time to Postgres.

There were two main downsides to SQLite as I would discover.

The first being having to rely on workarounds to get SQLite -> Heroku Postgres. There are no Windows based tools to do this. The only tool I know of to accomplish this is pgloader, which is only available on Linux. I got around this by installing Ubuntu through Windows Subsystem For Linux. Of course this now added the step of having to push the SQLite file to github, then pulling it down in Ubuntu and pushing that to Heroku. This was complicated, but it mostly worked. 

The second downside is that automatic updates weren't possible. I tried setting up a Github Actions workflow to do this to no avail. It kept throwing errors about SSL, and Heroku support was entirely unhelpful in this matter. Eventually I just resorted to manually pushing the updates using a bash script in Ubuntu. This would pull the database file, load it into postgres, then push to Heroku. Optimal? no, but it worked

### Postgres

Around July of this year, I decided to switch over to Postgres. First and foremost I could push updates from Windows instead of having to load up Ubuntu in a terminal. Also the expanded features of Postgres would be fun to play around with. Specifically views (which I guess is SQL in general), as well as getting to use Full Text Search (FTS) with pgvector for finding stuff like songs and albums. 

FTS was a game changer. Before I used a simple "LIKE" query, needing to use 2 to check for partial/full match. After a bit I looked into fuzzy searching and was able to do that with python in the bot itself. This was better than "LIKE", but still pretty inaccurate. I had to set the threshold for scoring manually, somewhere around 70. Mainly so it would catch common shorthand like "Incident", "Sandy", or even "Pittsburgh". The downside is that it could be very inaccurate, and lead to all sorts of funny results.

<!-- show screenshots of funny results -->

Moving to Postgres meant being able to use the improved Full Text Search. It still has its quirks (specifically with partial matches, which are easy to fix). But this method is so much better than any of the previous methods.

Postgres also has a ton of features I look forward to digging into. Stuff like the triggers (I think its possible to automatically update song counts on setlist insert.) Maybe even some more of the functions and stuff. It has a ton more potential than SQLite did.

Also the viewer app (Beekeeper Studio) doesn't crash if you click on more than a few rows at once, unlike an SQLite viewer app that shall remain nameless.

### Conclusion

A lot of this project was hacked together based on similar projects I could find. I'm not very original, so these sites were a big help. They're listed below:
- Jerrybase: Grateful Dead/Jerry Garcia database. Helped with formatting stuff like setlist notes.
- El Goose: Database for the "Indie-Groove" band Goose, used to format setlists better.
- Listen to the Music Play by Justin Mason: basically a book version of Jerrybase. Used as reference for stuff like Set Names and event classification.