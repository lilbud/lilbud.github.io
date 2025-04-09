---
title: "Tsuko G Revival Project Contributions"
tags: projects music
excerpt: "My contributions to a community archival project."
header:
  actions:
    - label: "Archive.org"
      url: "https://archive.org/details/tsuko-g-revival-project"
---

Note: This is not my project, just one that I contributed some files to. Click the button above to go to the Archive.org page.

---

![custom logo](/assets/img/blog/2025-04-09-tsuko-g-revival/logo.png)

## Intro
For the unaware, Anes B (aka Tsuko G) is a French musician who came into prominence in the 2010s. His channel, and main claim to fame, was covering various songs from video games and anime on Kazoo. 

I had a much longer version of this written up, but below I'll give just the short version.

Tsuko's channel was most active from 2014 until 2020. As mentioned, his main thing was Kazoo-based covers of songs from video games and anime. Although he delved into Acapella covers and straight-forward covers every now and then. Around 2018-19, he shifted away from the Kazoo covers towards mostly "normal" covers. 

In late 2020, he announced his first actual studio album, *Against the Stream*. This was intended as a sort of "farewell", as he had been doing Youtube nearly full-time solo for 6yrs. The album released on January 1, 2021, and he did indeed take a step back.

At some point in 2021, many videos disappeared from this Youtube channel, and by February 2022, the main Tsuko G. channel was basically gone.

It was around this time that the "Tsuko G. Revival Project" was started.

## The Return
As a quick aside. In late 2024, he announced a comeback, this time under his real name Anes. He also launched a new blockchain music platform called Auda Audio, which was his second attempt following "Metora/Lunaris" in 2021/22. The less said about a blockchain based platform in the year of our Lord 2025, the better. With this comeback, he announced that he wished to leave "Tsuko G" in the past. Not wanting to be known as the "kazoo anime/video game cover guy", which is totally fair and understandable. As part of this "new direction", he requested that no one repost his old content. 

Now let's really talk about the revival project.

## Revival
The project had the goal of finding/preserving as many of Tsuko's videos/covers as possible. Since the Youtube channel was all but deleted, they had to work from various internet archives and reuploads. Many videos were saved and reuploaded by a channel named "the "Tsuko G. Preservation Project/Tsuko [Redacted]". 

As of writing, the archive is up to 210 videos, which is basically everything that was ever on Tsuko's Youtube channel. Almost every official streaming release has also been preserved. Coming from sites like Qobuz/Apple Music. In addition, the tracks that were never released to streaming have been converted from the found video files.

I have to commend the community for such an effort. Not having started until after his channel was deleted, and having to pick up the pieces from there. Even if they managed half of his content it would be impressive. Managing to dig up multiple copies of his stuff from god-only-knows how many places is nothing to sneeze at.

## The Archive
As a breakdown, this is what currently makes up the archive:
- Found Audio:
    - FLAC rips (145)
    - AAC/OPUS video rips (196 of each)
    - M4A files ripped from Apple Music/iTunes (144)
- Found Video:
    - 217 videos dug up from the Internet Archive, or reuploads found on places like BiliBili/Youtube.

## My Involvement
I would like to reiterate that this is not my project. I just contributed to it by tracking down some missing/previously unknown content. 

I was made aware of this project a bit after Tsuko's latest "comeback". In a way, it was sad to see it go this way. Tsuko's channel provided much entertainment during my middle/high school years, although it had been a number of years since I paid much attention to his stuff. 

A bit after finding the project, I downloaded a copy of it and made a list of everything included. Basically everything I remembered was already found in multiple formats, and sometimes multiple copies of each. At the time, my initial goal was just whittling down the collection to a single "best" copy of each video/song. As I didn't need 3 copies of everything, just the best audio to import into my music library, and the best of the video.

The list I made quickly became a local postgres database, as it was easier that way. Everything already in the archive was added, a table for each format. Plus a master "tracks" table to keep track of every individual song.

### Video
I then went through a site named 'Filmot', which is something of a youtube metadata archive. This had a list of every video uploaded to Tsuko's channels, plus the video IDs, which would come in handy later. 

Using this list, I then used two sites to pull both the video metadata and check for copies on the Internet Archive that might've been missed. These sites are [MW Metadata](https://mattw.io/youtube-metadata/) and [Find YouTube Video](https://findyoutubevideo.thetechrobo.ca/). Even if the video itself couldn't be found, the metadata/thumbnail/description was usually archived, and this acts as a record of the video.

Using this method, as well as checking elsewhere on the internet. I managed to find an additional 15 videos that weren't archived:
```
2019 Q+A #3 - 720p
Butterfly (Piano Version) - 360p
Devilman Crybaby (Cover) - 720p
Give Me Rage (OP Gold Theme) - 360p
Great Days (Jojo OP 7) - 360p
Loot Anime Unboxing #2 - Music & Duel (May 2016) - 720p
Loot Anime Unboxing #3 - Blade (December 2016) - 720p
Rolling in the Deep (Kazoo'd) - 720p
Sorry (apology for being late on a video) - 720p
Fading Memories (Lyric Video) - 1080p
Break Free (Lyric Video) - 360p
Tsuko G. Season 4 - 720p
Tsuko G. JapanExpo 2018 Announcement - 720p
Ultimate Wanted (Lyric Video) - 360p
Dogsong (Kazoo'd) - 360p
```
Most of these were only in 360p, but are better than nothing. Rolling in the Deep is (as of writing) still publicly available on Tsuko's original Kazoo'd channel. Fading Memories was found on an unrelated channel for a motion graphics company of sorts. Perhaps who he worked with on it?

I also found upgrades to an additional 37 videos in the archive. Many of them are 720p upgrades to videos that were only found in 480p or lower. Although some are the same resolution as the existing archived version, just slightly higher quality. The one exception being Polaris, which was found in 360p but importantly not having burned in Chinese subtitles.

Many thumbnails were around found in higher resolution, mostly 720 -> 1080p. Some lower quality ones were found as well. Most were only archived in < 360p, so unless he decides to put everything back on Youtube, this is the best that exists.

### Audio
In addition, I also found a number of audio files. Both upgrades to existing, and also some unarchived/corrupted ones. 

I was able to download Kazoo'd Vol. 1 from Apple Music, replacing the existing rip which was all screwed up. I think it was done with a "iTunes downloader" which just pulls from various Youtube videos. So, many tracks were either unrelated videos, or just the original game version of a song.

Kazoo'd Volume 2 was also pulled from Apple Music. This was missing from the archive initially, as it was pulled from streaming nearly worldwide except for Mexico and India for some reason. Even better, it was available in 24/96 hi-res audio which was neat.

Additionally, I pulled 32 singles from Apple Music, almost all of them being 24/96 as well. I skipped the ones that were only 16/44, which is nearly every release pre-Kazoo'd Vol 2, and are already available as FLAC in the archive.

The 24/96 files were converted to FLAC and submitted along with the video upgrades as well. Those should appear in the archive soon.

## One Last Thing
While digging through various archives, I managed to also track down some hi-res art assets. On an archive of his old blog, I found very high resolution versions of his logos. I took these and then traced/recreated them in Adobe Illustrator.

I randomly found the original Kazoo image that he used, and used that to create 4K versions of his thumbnail/cover template. I did the same for Acapella'd, as well as his "horizontal lines" cover that he used later on. All of these were remade in Illustrator, and exported at or near 4K resolution. These assets will allow anyone to make new covers for the missing releases.

## Conclusion
Hopefully this very long ramble was slightly interesting. Up at the top is a link to the archive with all the files, which will also include my upgrades at some point. The art assets I hope to include here as well at some point.